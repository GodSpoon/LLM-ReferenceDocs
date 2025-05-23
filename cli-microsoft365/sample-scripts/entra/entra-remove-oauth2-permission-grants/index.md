-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - entra
  - oauth2
  - permissions
  - grants
  - admin
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Remove OAuth2 permission grants in a specific enterprise application (or service principal) in Entra ID.

Author: [Tobias Maestrini](https://github.com/tmaestrini)

From an administrator's perspective, managing OAuth2 permission grants that have been assigned to an enterprise application (based on an app registration or a multi-tenant app) can be a challenging task.
Sometimes it is necessary to remove **permissions that are granted to users** – for example when only administrators should define which permissions are granted to an enterprise app.
When a user has been granted permissions to an enterprise application, it can be important to remove these permissions as soon as possible to prevent unauthorized access in API requests.

This script will find and remove all OAuth2 permission grants (delegated permissions) that have been assigned to a specific enterprise application; either by admin consent, user consent, or both.
It first defines the function `Remove-PermissionsGrants` that does the necessary work described above and then calls this function with a parameter to select a specific enterprise app.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  <#
  .SYNOPSIS
    Removes OAuth2 permission grants in a specific enterprise application (or service principal) in Entra ID.

  .DESCRIPTION
    Find and remove all OAuth2 permissions assigned to a specific enterprise application by selecting one of the following removal options: **All permissions** / Permissions granted **by an administrator** / Permissions consented to **by users**.
    This function finds and removes OAuth2 permission grants (delegated permissions) assigned to a specific enterprise application.
    It can filter and remove permissions based on how they were granted: either by admin consent, user consent, or both.

  .PARAMETER AppDisplayName
    The display name of the enterprise application or service princial name in Entra ID from which to remove permission grants.
    This parameter is mandatory.

  .PARAMETER GrantType
    Specifies which type of permission grants to remove. Valid values are:
    - 'ByAdmin': Removes only permissions granted through admin consent (consentType = AllPrincipals)
    - 'ByUser': Removes only permissions granted through user consent (consentType != AllPrincipals)
    - 'All': Removes both admin and user consented permissions
    Default value is: 'ByUser'

  .EXAMPLE
    Remove-PermissionsGrants -AppDisplayName "My App"
    Removes all user-consented permission grants for the enterprise application "My App"

  .EXAMPLE
    Remove-PermissionsGrants -AppDisplayName "My App" -GrantType All
    Removes all permission grants (both admin and user consented) for the enterprise application "My App"

  .EXAMPLE
    Remove-PermissionsGrants -AppDisplayName "My App" -GrantType ByAdmin
    Removes only admin-consented permission grants for the enterprise application "My App"

  .NOTES
    Prerequisites:
    - CLI for Microsoft 365 (m365) must be installed and configured
    - The User must be assigned an appropriate Microsoft Entra role to manage OAuth2 permission grants (at least Application Developer, Cloud Application Administrator, User Administrator)
      (see Microsoft Graph references: https://learn.microsoft.com/en-us/graph/api/oauth2permissiongrant-list?view=graph-rest-1.0&tabs=http and https://learn.microsoft.com/en-us/graph/api/oauth2permissiongrant-delete?view=graph-rest-1.0&tabs=http)
    - The Entra app registration used to sign into the CLI for Microsoft 365 must have an appropriate permission scope to manage permissions of other apps (at least `DelegatedPermissionGrant.ReadWrite.All`)

  .LINK
    https://learn.microsoft.com/azure/active-directory/manage-apps/manage-application-permissions?pivots=ms-powershell
  #>

  function Remove-PermissionsGrants {
    param(
      [Parameter(Mandatory = $true)]
      [string]$AppDisplayName,

      [Parameter(Mandatory = $false)]
      [ValidateSet('ByAdmin', 'ByUser', 'All')] $GrantType = 'ByUser'
    )
    
    Clear-Host
    Write-Host "Removing permission grants for the enterprise app / service principal '$AppDisplayName'"
    Write-Host "Selected grant type: '$GrantType'`n"

    # Get Service Principal that represents the enterprise app / service principal
    try {
      $app = m365 entra enterpriseapp get --displayName $AppDisplayName --output json | ConvertFrom-Json
      if($app.error) {
        throw "Enterprise app '$AppDisplayName' not found"
      }
    }
    catch {
      Write-Host "❌ Terminating: $($_.Exception.Message)" -ForegroundColor Red
      return
    }

    # Filter (delegated) permissions granted with according consent for the given enterprise app or service principal
    $selectedPermissionsGrants = @()
    if ($GrantType -eq 'All') {
      $selectedPermissionsGrants = m365 entra oauth2grant list --spObjectId $app.id --output json | ConvertFrom-Json
    }
    elseif ($GrantType -eq 'ByAdmin') {
      $selectedPermissionsGrants = m365 entra oauth2grant list --spObjectId $app.id --query "[?consentType == 'AllPrincipals']" --output json | ConvertFrom-Json
    }
    else {
      # granted by user
      $selectedPermissionsGrants = m365 entra oauth2grant list --spObjectId $app.id --query "[?consentType != 'AllPrincipals']" --output json | ConvertFrom-Json
    }

    Write-Host "👉 $($selectedPermissionsGrants.Length) definitions found`n"
    
    # Remove the filtered permissions
    $selectedPermissionsGrants | ForEach-Object {
      Write-Host "Removing permission grant (ID) '$($_.id)': " -NoNewline
      m365 entra oauth2grant remove --grantId $_.id --force
      Write-Host "✔ Done" -ForegroundColor Green
      Write-Host "⎿ " $_.scope.trim()
    }

    # Display success message
    if($selectedPermissionsGrants.Length -gt 0) {
      Write-Host "`n✔️ Successfully removed selected permissions" -ForegroundColor Green
    }
  }

  # Set the enterprise app / service principal name for which to remove user consents
  $AppDisplayName = 'My App'
  Remove-PermissionsGrants -AppDisplayName $AppDisplayName
  ```

  </TabItem>
</Tabs>
