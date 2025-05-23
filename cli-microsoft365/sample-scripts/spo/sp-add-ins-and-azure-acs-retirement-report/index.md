-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - reports
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Retrieves the retirement report of SharePoint Add-Ins and Azure ACS.

Author: [Michał Kornet](https://michalkornet.com/)

This script is designed to extract information about retirement-related components from a selected tenant. It covers key elements such as event receivers, SharePoint Add-Ins, Azure Access Control Service (ACS), and installed SharePoint Add-Ins

## Script Usage

The script supports two authentication methods or the current logged-in method of M365 CLI.

1. GetRetirementStatus -AuthenticationMethod "DeviceCode"

To use this method, log in using the DeviceCode authentication method of M365 CLI.

2. GetRetirementStatus -AuthenticationMethod "Certificate" -CertificatePath "C:\Path\To\Certificate.pfx" -CertificatePassword "YourPassword" -TenantId "YourTenantId" -AppId "YourAppId"

For this method, you need to create a certificate and a new Entra App.

To create a new app with the required permissions, use the following command:

```sh
m365 entra app add --name 'RetirementReportApp' --apisApplication 'https://graph.microsoft.com/Application.Read.All,https://graph.microsoft.com/Sites.Read.All,https://microsoft.sharepoint-df.com/Sites.Manage.All' --certificateFile "C:\Path\To\Certificate.cer" --certificateDisplayName 'Certificate' --grantAdminConsent 
```

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
<#
.SYNOPSIS
    Retrieve Retirement Report for SharePoint Add-Ins and Azure ACS.
.DESCRIPTION
    This script retrieves the retirement report of SharePoint Add-Ins and Azure ACS.
    If not already authenticated, the function will attempt to log in using the specified authentication method.
    Authentication can be done using a devicecode or a certificate.

.PARAMETER AuthenticationMethod
    Specifies the authentication method to be used. Valid values are "DeviceCode" or "Certificate".
    Default value is "DeviceCode".

.PARAMETER CertificatePath
    Specifies the path to the certificate file used for authentication when AuthenticationMethod is set to "Certificate".

.PARAMETER CertificatePassword
    Specifies the password for the certificate file when AuthenticationMethod is set to "Certificate".

.PARAMETER TenantId
    Specifies the Tenant ID to be used for authentication when AuthenticationMethod is set to "Certificate".

.PARAMETER AppId (Client ID)
    Specifies the App ID (Client ID) to be used for authentication when AuthenticationMethod is set to "Certificate".

.OUTPUTS
    The script generates the following output files:
    - EventReceivers.csv - contains the list of event receivers
    - AzureACSList.csv - contains the list of Azure ACS apps
    - SharePointInstalledAddInsList.csv - contains the list of SharePoint installed add-ins
    - SharePointAddInsList.csv - contains the list of SharePoint add-ins

.NOTES
    Using the certificate authentication method requires the following steps:
    Creation of Entra App with the following permissions:
        Microsoft Graph
            - Application.Read.All
            - Sites.Read.All
        SharePoint
            - Sites.Manage.All

.EXAMPLE
    PS C:\> GetRetirementStatus -AuthenticationMethod "DeviceCode"
    This example retrieves retirement status information using devicecode authentication (Please note that a current user may not have access to all sites).

.EXAMPLE
    PS C:\> GetRetirementStatus -AuthenticationMethod "Certificate" -CertificatePath "C:\Path\To\Certificate.pfx" -CertificatePassword "YourPassword" -TenantId "YourTenantId" -AppId "YourAppId"
    This example retrieves retirement status information using certificate authentication.
#>
function GetRetirementStatus {
  param
  (
    [Parameter(Mandatory = $false, HelpMessage = "Authentication Method")][ValidateSet("DeviceCode", "Certificate")] $AuthenticationMethod = "DeviceCode",
    [Parameter(Mandatory = $false, HelpMessage = "Certificate Path")][string] $CertificatePath,
    [Parameter(Mandatory = $false, HelpMessage = "Certificate Password")][string] $CertificatePassword,
    [Parameter(Mandatory = $false, HelpMessage = "Tenant Id")][string] $TenantId,
    [Parameter(Mandatory = $false, HelpMessage = "App Id (Client ID)")][string] $AppId 
  )

  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged out") {
    # Connection to Microsoft 365
    if ($AuthenticationMethod -eq "DeviceCode") {
      Write-Host "Logging in using DeviceCode authentication"
      m365 login
    }
    else {
      Write-Host "Logging in using Certificate authentication"
      m365 login --authType certificate --certificateFile $CertificatePath --appId $AppId --tenant $TenantId --password $CertificatePassword
    }
  }
  else {
    Write-Host "Already logged in"
    Write-Host "Status: $m365Status"
  }

  function IsAppInList {
    param (
      [string]$AppTitle,
      [array]$AppList
    )

    return $AppList.Title -contains $AppTitle
  }

  function GetLegacyEntraApps {
    try {
      $ResultList = @()
      #get all Entra apps with Legacy service principal type
      $EntraApps = m365 entra sp list --query "[?servicePrincipalType =='Legacy']" --output json | ConvertFrom-Json

      foreach ($EntraApp in $EntraApps) {
        $ResultList += New-Object PSObject -Property @{
          Id                   = $EntraApp.id
          AppName              = $EntraApp.displayName
          AppId                = $EntraApp.appId
          ServicePrincipalType = $EntraApp.servicePrincipalType
          Created              = $EntraApp.createdDateTime?.ToLongDateString()
        }
      }
      return $ResultList
    }
    catch {
      Write-Error "Error retrieving legacy Entra apps: $_"
      return @()
    }
  }

  function GetEventReceiversDataToOutputList {
    param (
      [array] $EventReceivers,
      [string] $Location,
      [string] $LocationUrl
    )
    try {
      $ResultList = @()

      foreach ($EventReceiver in $EventReceivers) {
        $ResultList += New-Object PSObject -Property @{
          EventType               = $EventReceiver.EventType
          ReceiverUrl             = $EventReceiver.ReceiverUrl
          ReceiverAssembly        = $EventReceiver.ReceiverAssembly
          ReceiverClass           = $EventReceiver.ReceiverClass
          ReceiverName            = $EventReceiver.ReceiverName
          ReceiverId              = $EventReceiver.ReceiverId
          ReceiverSequenceNumber  = $EventReceiver.SequenceNumber
          ReceiverSynchronization = $EventReceiver.Synchronization
          LocationType            = $Location
          LocationUrl             = $LocationUrl
        }
      }
      return $ResultList
    }
    catch {
      Write-Error "Error assigning Event Receivers data: $_"
      return @()
    }
  }

  function GetEventReceiversDataForWeb {
    param (
      [string] $WebUrl
    )
    try {
      $EventReceivers = @()
      $EventReceiversOnWeb = m365 spo eventreceiver list --webUrl $WebUrl --query "[?!contains(ReceiverAssembly,'Microsoft.')]" --output json | ConvertFrom-Json
      $EventReceivers += GetEventReceiversDataToOutputList -EventReceivers $EventReceiversOnWeb -Location "Web" -LocationUrl $WebUrl

      $Lists = m365 spo list list --webUrl $WebUrl --output json | ConvertFrom-Json

      foreach ($List in $Lists) {
        $EventReveiversOnList = m365 spo eventreceiver list --webUrl $WebUrl --listId $List.Id --query "[?!contains(ReceiverAssembly,'Microsoft.')]" --output json | ConvertFrom-Json
        $EventReceivers += GetEventReceiversDataToOutputList -EventReceivers $EventReveiversOnList -Location "List" -LocationUrl $List.RootFolder.ServerRelativeUrl
      }
      return $EventReceivers
    }
    catch {
      Write-Error "Error getting Event Receivers data for Web: $_"
      return @()
    }
  }

  function GetAppsInstancesForSite {
    param (
      [string] $SiteUrl,
      [array] $AppCatalogApps
    )

    try {
      $ResultList = @()
      $AppsOnSite = m365 spo app instance list --siteUrl $SiteUrl --output json | ConvertFrom-Json

      foreach ($AppOnSite in $AppsOnSite) {
        if (!(IsAppInList -AppTitle $AppOnSite.Title -AppList $AppCatalogApps)) { continue }
  
        $ResultList += New-Object PSObject -Property @{
          Id           = $AppOnSite.AppId
          ProductId    = $AppOnSite.ProductId
          AppName      = $AppOnSite.Title
          LastModified = $EXAMPLE_SECRET_VALUE_PLACEHOLDER()
          Location     = $SiteUrl
        }
      }
      return $ResultList
    }
    catch {
      Write-Error "Error getting App Instances data for Site: $_"
      return @()
    }
  }

  function GetSharePointAddinsOutputList {
    param(
      [array]$AppCatalogApps
    ) 
    try {
      $ResultList = @()

      foreach ($AppCatalogApp in $AppCatalogApps) {
        $ResultList += New-Object PSObject -Property @{
          AppName           = $AppCatalogApp.Name
          ServerRelativeUrl = $AppCatalogApp.ServerRelativeUrl
          TimeCreated       = $EXAMPLE_SECRET_VALUE_PLACEHOLDER()
          TimeLastModified  = $EXAMPLE_SECRET_VALUE_PLACEHOLDER()
          Title             = $AppCatalogApp.Title
          Version           = $AppCatalogApp.UIVersionLabel
        }
      }
      return $ResultList
    }
    catch {
      Write-Error "Error assigning Apps files data: $_"
      return @()
    }
  }

  $CurrentPath = $PSScriptRoot
  $EventReceiversPath = Join-Path -Path $CurrentPath -ChildPath "EventReceivers.csv"
  $AzureAcsListPath = Join-Path -Path $CurrentPath -ChildPath "AzureACSList.csv"
  $SharePointInstalledAddInsListPath = Join-Path -Path $CurrentPath -ChildPath "SharePointInstalledAddInsList.csv"
  $SharePointAddInsListPath = Join-Path -Path $CurrentPath -ChildPath "SharePointAddInsList.csv"

  #initialize arrays
  $SharePointInstalledAddInsList = @()
  $EventReceiversList = @()
  $SharePointAddInsList = @()
  $AzureAcsList = GetLegacyEntraApps

  #get all sites
  $Sites = m365 spo site list --output json | ConvertFrom-Json

  #get tenant App Catalog url
  $AppCatalogTenantUrl = m365 spo tenant appcatalogurl get
  #get all files in tenant App Catalog

  $AppCatalogApps = m365 spo file list --webUrl $AppCatalogTenantUrl.Replace('"', '') --folderUrl "AppCatalog" --query "[?contains(Name,'.app')]" --output json | ConvertFrom-Json

  #get all site App Catalogs
  $SiteAppCatalogs = m365 spo site appcatalog list --output json | ConvertFrom-Json

  #get all files in all site App Catalogs
  foreach ($SiteAppCatalog in $SiteAppCatalogs) {
    $AppCatalogApps += m365 spo file list --webUrl $SiteAppCatalog.AbsoluteUrl --folderUrl "AppCatalog" --query "[?contains(Name,'.app')]" --output json | ConvertFrom-Json
  }

  #assign Add-ins list to the output array
  $SharePointAddInsList = GetSharePointAddinsOutputList -AppCatalogApps $AppCatalogApps

  try {
    $SiteCount = $Sites.Count

    foreach ($Site in $Sites) {
      $Siteindex = $Sites.IndexOf($Site) + 1
      Write-Host "Processing $Siteindex/$SiteCount : $($Site.Url)"

      #get all legacy apps installed on the site
      $SharePointInstalledAddInsList += GetAppsInstancesForSite -SiteUrl $Site.Url -AppCatalogApps $AppCatalogApps
      #get all event receivers on the site
      $EventReceiversOnSite = m365 spo eventreceiver list --webUrl $Site.Url --scope site --query "[?!contains(ReceiverAssembly,'Microsoft.')]" --output json | ConvertFrom-Json
      #assign site event receivers list to the output array
      $EventReceiversList += GetEventReceiversDataToOutputList -EventReceivers $EventReceiversOnSite -Location "Site" -LocationUrl $Site.Url
      #get all root web/lists event receivers 
      $EventReceiversList += GetEventReceiversDataForWeb -WebUrl $Site.Url
      #get all webs in the site
      $Webs = m365 spo web list --url $Site.Url --output json | ConvertFrom-Json
      foreach ($Web in $Webs) {
        #get all event receivers on the web/lists
        $EventReceiversList += GetEventReceiversDataForWeb -WebUrl $Web.Url
      }
    }
  }
  catch {
    Write-Host "Error: $_ - $($Site.Url)"
    continue
  }

  #export data to csv files
  $EventReceiversList | Export-Csv -Path $EventReceiversPath -NoTypeInformation
  $AzureAcsList | Export-Csv -Path $AzureAcsListPath -NoTypeInformation
  $SharePointInstalledAddInsList | Export-Csv -Path $SharePointInstalledAddInsListPath -NoTypeInformation
  $SharePointAddInsList | Export-Csv -Path $SharePointAddInsListPath -NoTypeInformation

  m365 logout
  Write-Host "Finished"
}

# choose the preferred method for authentication.
GetRetirementStatus

  ```

  </TabItem>
</Tabs>
