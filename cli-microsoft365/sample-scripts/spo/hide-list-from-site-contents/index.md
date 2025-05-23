-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - lists
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Hide SharePoint list from Site Contents

Author: [David Ramalho](https://sharepoint-tricks.com/hide-sharepoint-list-from-site-contents/)

If you need to hide the SharePoint list from the UI this simple PowerShell script will hide a specific list from the site contents. This will prevent users from easily accessing the list while, for example, you are still setting it up.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $listName = "listName"
  $site = "https://contoso.sharepoint.com/"

  m365 login
  $list = m365 spo list get --webUrl $site -t $listName -o json | ConvertFrom-Json
  m365 spo list set --webUrl $site --id $list.Id --hidden true
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # requires jq: https://stedolan.github.io/jq/

  listName="listName"
  site=https://contoso.sharepoint.com/

  m365 login
  listId=$(m365 spo list get --webUrl $site -t "$listName" -o json | jq ".Id")
  m365 spo list set --webUrl $site --id $listId --hidden true
  ```

  </TabItem>
</Tabs>
