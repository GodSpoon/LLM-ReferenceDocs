-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli consent

Consent additional permissions for the Microsoft Entra application used by the CLI for Microsoft 365

## Usage

```sh
m365 cli consent [options]
```

## Options

```md definition-list
`-s, --service <service>`
: Service for which to consent permissions. Allowed values: `VivaEngage`.
```

<Global />

## Remarks

Using the `cli consent` command you can consent additional permissions for the Microsoft Entra application used by the CLI for Microsoft 365. This is for example necessary to use Viva Engage commands, which require the Viva Engage API permission that isn't granted to the CLI by default.

After executing the command, the CLI for Microsoft 365 will present you with a URL that you need to open in the web browser in order to consent the permissions for the selected Microsoft 365 service.

To simplify things, rather than wondering which permissions you should grant for which CLI commands, this command allows you to easily grant all the necessary permissions for using commands for the specified Microsoft 365 service, like Viva Engage.

## Examples

Consent permissions to the Viva Engage API

```sh
m365 cli consent --service VivaEngage
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "To consent permissions for executing VivaEngage commands, navigate in your web browser to https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=31359c7f-bd7e-475c-86db-fdb8c937548e&response_type=code&scope=https%3A%2F%2Fapi.yammer.com%2Fuser_impersonation"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  To consent permissions for executing VivaEngage commands, navigate in your web browser to https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=31359c7f-bd7e-475c-86db-fdb8c937548e&response_type=code&scope=https%3A%2F%2Fapi.yammer.com%2Fuser_impersonation
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  To consent permissions for executing VivaEngage commands, navigate in your web browser to https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=31359c7f-bd7e-475c-86db-fdb8c937548e&response_type=code&scope=https%3A%2F%2Fapi.yammer.com%2Fuser_impersonation
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  To consent permissions for executing VivaEngage commands, navigate in your web browser to https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=31359c7f-bd7e-475c-86db-fdb8c937548e&response_type=code&scope=https%3A%2F%2Fapi.yammer.com%2Fuser_impersonation
  ```

  </TabItem>
</Tabs>
