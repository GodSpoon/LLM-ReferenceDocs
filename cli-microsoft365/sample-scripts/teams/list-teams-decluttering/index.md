-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - decluttering
  - insights
  - usage
  - governance
  - teams
---

import Tabs from "@theme/Tabs";
import TabItem from "@theme/TabItem";

# Lists information on decluttering teams

Author: [Tobias Maestrini](https://github.com/tmaestrini)

Get insights about the teams in your tenant. Please keep in mind that you see only the teams that you have access to.
For a full overview and a complete decluttering experience, the calling user needs to have admin rights in SPO and Teams.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $ErrorActionPreference = "Stop"

  function Start-Routine {
    # START ROUTINE
    [CmdletBinding()]
    param (
      [Parameter(Mandatory = $false)]
      [Switch] $KeepConnectionsAlive
    )

    try {
      Initialize-Params
      Initialize-ExportPath
      Get-AllTeams
      Set-TeamsGovernanceData
      Write-Host "Routine terminated" -ForegroundColor Green
      if (!$KeepConnectionsAlive.IsPresent) {
        m365 logout
      }
    }
    catch {
      Write-Error $_.Exception.Message
    }
  }

  function Initialize-Params {
    Write-Host "Generating usage reports from your Teams environment"

    # define globals
    $Global:AllTeamsInOrg = $null
    $Global:Path = $null
    $Global:TeamList = @()

    Write-Output "Connecting to M365 tenant: please follow the instructions."
    Write-output "IMPORTANT: You'll need to have SharePoint- and Teams-Admin permissions!"
    if ((m365 status --output text) -eq "Logged out") {
      m365 login
    }
  }

  function Get-AllTeams {
    Write-Host "Getting all teams in this tenant" -ForegroundColor Yellow
    Write-Host "This may take a while..."

    try {
      $Global:AllTeamsInOrg = m365 teams team list | ConvertFrom-Json
    }
    catch {
      throw $_.Exception.Message
    }
  }

  function Set-TeamsGovernanceData {
    $ErrorActionPreference = 'SilentlyContinue'
    $selectedTeams = $Global:AllTeamsInOrg
    if ($IsWindows -or ($env:OS -like "*Windows*")) {
      Write-Host "Select all teams for which you want to create a detailed report."
      $Global:AllTeamsInOrg = $selectedTeams | Out-GridView -Title "Select teams for your report" -PassThru
    }

    $i = 1
    Foreach ($Team in $Global:AllTeamsInOrg) {
      $SPOSite, $TeamUsers, $TeamOwners, $TeamMembers, $TeamGuests, $TeamChannels = $null

      Write-Progress -Activity "Getting infos for team" -PercentComplete (100 * $i / $Global:AllTeamsInOrg.Length) -Status "$($Team.DisplayName)"
      $TeamGroup = m365 entra m365group get --id $Team.id --includeSiteUrl | ConvertFrom-Json
      if ($TeamGroup.siteUrl) {
        $SPOSite = m365 spo site get --url $TeamGroup.siteUrl | ConvertFrom-Json
        $SPOSite = m365 spo site list --filter "Url -eq '$($TeamGroup.siteUrl)'" | ConvertFrom-Json
        $TeamUsers = m365 teams user list --teamId $Team.id | ConvertFrom-Json
        $TeamOwners = $TeamUsers | Where-Object userType -EQ "Owner"
        $TeamMembers = $TeamUsers | Where-Object userType -EQ "Member"
        $TeamGuests = $TeamUsers | Where-Object userType -EQ "Guest"
        $TeamChannels = m365 teams channel list --teamId $Team.id | ConvertFrom-Json | Sort-Object DisplayName
      }

      $teamToExport = [PSCustomObject]@{
        "Team Name"          = $Team.displayName
        ID                   = $Team.id
        "Access Type"        = $TeamGroup.visibility ?? 'n/a'
        "# Channels"         = $TeamChannels ? $TeamChannels.Length : ''
        "Channels"           = $TeamChannels ? ($TeamChannels | ForEach-Object { "{0} ({1})" -f $_.displayName, (Get-Culture).TextInfo.ToTitleCase($_.membershipType) }) -join ', ' : ''

        "# Owners"           = $TeamOwners ? $TeamOwners.Length : '---'
        Owners               = $TeamOwners ? ($TeamOwners | ForEach-Object { "{0} ({1})" -f $_.displayName, $_.userPrincipalName }) -join ', ' : '---'
        "# Members"          = $TeamMembers ? $TeamMembers.Length : '---'
        Members              = $TeamMembers ? ($TeamMembers | ForEach-Object { "{0} ({1})" -f $_.displayName, $_.userPrincipalName }) -join ', ' : '---'
        "# Guests"           = $TeamGuests ? $TeamGuests.Length : '---'
        Guests               = $TeamGuests ? ($TeamGuests | ForEach-Object { "{0} ({1})" -f $_.displayName, $_.userPrincipalName }) -join ', ' : '---'

        "SharePoint URL"     = $TeamGroup.siteUrl ?? 'not permitted'
        "Storage Used"       = ($TeamGroup.siteUrl) ? ("{0:N2} GB" -f ($SPOSite.StorageUsage / 1024)) : ''
        "Storage Limit"      = ($TeamGroup.siteUrl) ? ("{0:N2} GB" -f ($SPOSite.StorageMaximumLevel / 1024)) : ''
        "Storage Used Quota" = ($TeamGroup.siteUrl) ? ("{0:P2}" -f ($SPOSite.StorageUsage / $SPOSite.StorageMaximumLevel)) : ''
        "Last Action (Date)" = ($TeamGroup.siteUrl) ? $SPOSite.LastContentModifiedDate : ''
      }
      Write-DataRowToCSV -dataRowObject $teamToExport
      $Global:TeamList += $teamToExport
      $i++
    }
    Write-Progress -Activity "Getting infos" -Status "completed" -Completed
    $ErrorActionPreference = "Stop"
  }

  function Initialize-ExportPath {
    $Path = Read-Host "Set the path where you want to export the data as csv file"
    $TestPath = test-path -path $Path
    $tStamp = (Get-Date).ToString("yyyyMMddHHmmss")
    if ($TestPath -ne $true) {
      New-Item -ItemType directory -Path $Path | Out-Null
      Write-Host "Creating file in $($Path): TeamsDataReport-{current date}.csv" -ForegroundColor Yellow
    }
    else {
      Write-Host "File created in $($Path): 'TeamsDataReport-$($tStamp).csv'."
      Write-Host "`nAll data will be exported to $($Path): TeamsDataReport-$($tStamp).csv. Do not edit this file during the scan."
    }
    $Global:Path = "$($Path)\TeamsDataReport-$($tStamp).csv"
  }

  function Write-DataRowToCSV {
    [CmdletBinding()]
    param (
      [Parameter(Mandatory = $true)]
      [PSCustomObject]
      $DataRowObject
    )
    $DataRowObject | Export-Csv $Global:Path -NoTypeInformation -Delimiter ";" -Append -Encoding utf8
  }

  Start-Routine -KeepConnectionsAlive
  ```

  </TabItem>
</Tabs>
