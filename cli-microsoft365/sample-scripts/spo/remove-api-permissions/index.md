-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - security
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Remove SharePoint API permissions

Author: [Waldek Mastykarz](https://blog.mastykarz.nl/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

When building SharePoint Framework solutions connected to APIs secured with Microsoft Entra ID, you might need to clear the list of granted API permissions.

This script helps you to quickly remove SharePoint API permissions.

<Tabs>
  <TabItem value="JavaScript (Google zx)">

  ```javascript
  #!/usr/bin/env zx
  $.verbose = false;

  console.log('Retrieving granted API permissions...');
  const apiPermissions = JSON.parse(await $`m365 serviceprincipal sp grant list -o json`);

  for (let i = 0; i < apiPermissions.length; i++) {
    const permission = apiPermissions[i];
    console.log(`Removing permission ${permission.Resource}/${permission.Scope} (${permission.ObjectId})...`);
    try {
      await $`m365 spo serviceprincipal grant revoke --id ${permission.ObjectId}`
      console.log(chalk.green('DONE'));
    }
    catch (err) {
      console.error(err.stderr);
    }
  }
  ```

  </TabItem>
</Tabs>

Using [CLI for Microsoft 365](https://aka.ms/cli-m365), the script first retrieves the list of granted API permissions. Then, it iterates through them and removes (revokes) each one of them using CLI for Microsoft 365. After running this script, your list of SharePoint API permissions will be empty.

This script uses [CLI for Microsoft 365](https://aka.ms/cli-m365) and [Google zx](https://github.com/google/zx).

To run the script, save it to a file with the `.mjs` extension. Next, run the script either by calling `zx remove-apipermissions.mjs` or `./remove-apipermissions.mjs` after making the script executable using `chmod +x ./remove-apipermissions.mjs;`
