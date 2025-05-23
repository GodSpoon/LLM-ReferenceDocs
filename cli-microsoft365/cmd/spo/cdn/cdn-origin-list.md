-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo cdn origin list

List CDN origins settings for the current SharePoint Online tenant

## Usage

```sh
m365 spo cdn origin list [options]
```

## Options

```md definition-list
`-t, --type [type]`
: Type of CDN to manage. Allowed values are: `Public`, `Private`. Default `Public`.
```

<Global />

## Remarks

Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Show the list of origins configured for the Public CDN.

```sh
m365 spo cdn origin list
```

Show the list of origins configured for the Private CDN.

```sh
m365 spo cdn origin list --type Private
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    "*/MASTERPAGE",
    "*/STYLE LIBRARY",
    "*/CLIENTSIDEASSETS"
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  */MASTERPAGE
  */STYLE LIBRARY
  */CLIENTSIDEASSETS
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  */MASTERPAGE
  */STYLE LIBRARY
  */CLIENTSIDEASSETS
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  */MASTERPAGE
  */STYLE LIBRARY
  */CLIENTSIDEASSETS
  ```

  </TabItem>
</Tabs>

## More information

- Use Microsoft 365 CDN with SharePoint Online: [https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide](https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide)
