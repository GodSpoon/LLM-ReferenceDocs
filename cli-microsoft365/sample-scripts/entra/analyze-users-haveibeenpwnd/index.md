-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:  
  - security
  - users
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Analyze users for known data breaches with have I been pwned

Inspired by: [Albert-Jan Schot](https://www.cloudappie.nl/cli-microsoft-haveibeenpwned-status/)

Validate all your users against known breaches with the have I been pwned API. That way you can quickly scan if your users are part of any known breaches.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $apiKey = "<PUTYOURKEYHERE>"
  $m365Status = m365 status --output text

  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  $users = m365 entra user list --properties "displayName,userPrincipalName" | ConvertFrom-Json

  $users | ForEach-Object {
    $user = $_
    $i++
    Write-Host "Check HBIP status for user '$($user.userPrincipalName)' - ($i/$($users.length))"

    $hbipStatus = m365 entra user hibp --userName $user.userPrincipalName --apiKey $apiKey --verbose | ConvertFrom-Json

    if ($hbipStatus -ne "No pwnage found") {
      Write-Host -ForegroundColor Red "Issue with user '$($user.userPrincipalName)'"
      $hbipStatus
    }

    Start-Sleep -Milliseconds 1500
  }
  ```

  </TabItem>
</Tabs>
