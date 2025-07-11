-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli app reconsent

Reconsent all permission scopes used in CLI for Microsoft 365

## Usage

```sh
m365 cli app reconsent [options]
```

## Options

<Global />

## Remarks

This command will add all missing scopes used in CLI for Microsoft 365 to your current app registration. It will only add missing scopes and won't remove any scopes that are already present in the app registration.

## Examples

Consent all permission scopes used in CLI for Microsoft 365 to the current app registration

```sh
m365 cli app reconsent
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "To consent to the new scopes for your Microsoft Entra application registration, please navigate to the following URL: https://login.microsoftonline.com/f72203fd-b0a0-472d-85eb-079a117a80de/adminconsent?client_id=62b981af-59d3-4d25-8baf-6cc067a03102"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  To consent to the new scopes for your Microsoft Entra application registration, please navigate to the following URL: https://login.microsoftonline.com/f72203fd-b0a0-472d-85eb-079a117a80de/adminconsent?client_id=62b981af-59d3-4d25-8baf-6cc067a03102
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  To consent to the new scopes for your Microsoft Entra application registration, please navigate to the following URL: https://login.microsoftonline.com/f72203fd-b0a0-472d-85eb-079a117a80de/adminconsent?client_id=62b981af-59d3-4d25-8baf-6cc067a03102
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  To consent to the new scopes for your Microsoft Entra application registration, please navigate to the following URL: https://login.microsoftonline.com/f72203fd-b0a0-472d-85eb-079a117a80de/adminconsent?client_id=62b981af-59d3-4d25-8baf-6cc067a03102
  ```

  </TabItem>
</Tabs>
