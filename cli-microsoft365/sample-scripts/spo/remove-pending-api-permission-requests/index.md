-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - cleanup
  - security
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Remove pending SharePoint API permission requests

Author: [Waldek Mastykarz](https://blog.mastykarz.nl/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

When building SharePoint Framework solutions connected to APIs secured with Microsoft Entra ID, you'll easily end up with many pending permission requests.

This script helps you to quickly remove pending SharePoint API permission requests.

<Tabs>
  <TabItem value="JavaScript (Google zx)">

  ```javascript
  #!/usr/bin/env zx
  $.verbose = false;

  console.log('Retrieving permission requests...');
  const permissionRequests = JSON.parse(await $`m365 spo serviceprincipal permissionrequest list -o json`);

  for (let i = 0; i < permissionRequests.length; i++) {
    const request = permissionRequests[i];
    console.log(`Removing request ${request.Resource}/${request.Scope} (${request.Id})...`);
    try {
      await $`m365 spo serviceprincipal permissionrequest deny --id ${request.Id}`
      console.log(chalk.green('DONE'));
    }
    catch (err) {
      console.error(err.stderr);
    }
  }
  ```

  </TabItem>
</Tabs>

Using [CLI for Microsoft 365](https://aka.ms/cli-m365), the script first retrieves the list of pending SharePoint API permission requests. Then, it iterates through the requests and removes (denies) each one of them using CLI for Microsoft 365. After running this script, your list of pending SharePoint API permission requests will be empty.

This script uses [CLI for Microsoft 365](https://aka.ms/cli-m365) and [Google zx](https://github.com/google/zx).

To run the script, save it to a file with the `.mjs` extension. Next, run the script either by calling `zx remove-permissionrequests.mjs` or `./remove-permissionrequests.mjs` after making the script executable using `chmod +x ./remove-permissionrequests.mjs;`
