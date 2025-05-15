-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - provisioning
  - sites
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Add App Catalog to SharePoint site

Author: [David Ramalho](https://sharepoint-tricks.com/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

When you just want to deploy certain SharePoint solution to a specific site, it's required to create an app catalog for that site. The below script will create it for the site. In the article referenced above you can check where you can use App catalog for the site instead of global app catalog.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $site = "https://contoso.sharepoint.com/sites/site"
  m365 login
  m365 spo site appcatalog add --siteUrl $site
  Write-output "App Catalog Created on " $site
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  site=https://tricks365.sharepoint.com/sites/site

  m365 login
  m365 spo site appcatalog add --siteUrl $site
  echo "App Catalog Created on $site"
  ```

  </TabItem>
</Tabs>
