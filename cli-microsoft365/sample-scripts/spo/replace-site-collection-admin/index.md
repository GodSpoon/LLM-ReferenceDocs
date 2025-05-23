-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - security
  - users  
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Replace site collection admin with another user

Author: [Patrick Lamber](https://www.nubo.eu/Replace-Site-Collection-Admin-Using-CLI/)
Inspired By: [Salaudeen Rajack](https://www.sharepointdiary.com/2015/08/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

The script removes a user from a site collection and adds a new one as site collection admin.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $userToAdd = "<upnOfUserToAdd>"
  $userToRemove = "<upnOfUserToRemove>"
  $webUrl = "<spoUrl>"

  $m365Status = m365 status --output text
  Write-Host $m365Status
  if ($m365Status -eq "Logged Out") {
    # Connection to Microsoft 365
    m365 login
  }

  m365 spo user remove --webUrl $webUrl --loginName "i:0#.f|membership|$userToRemove" --force
  m365 spo site set --url $webUrl --owners $userToAdd
  ```

  </TabItem>
</Tabs>
