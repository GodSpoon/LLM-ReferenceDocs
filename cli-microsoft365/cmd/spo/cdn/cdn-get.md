-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo cdn get

View current status of the specified Microsoft 365 CDN

## Usage

```sh
m365 spo cdn get [options]
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

Show if the Public CDN is currently enabled or not.

```sh
m365 spo cdn get
```

Show if the Private CDN is currently enabled or not.

```sh
m365 spo cdn get --type Private
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  true
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  true
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  true
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  true
  ```

  </TabItem>
</Tabs>

## More information

- Use Microsoft 365 CDN with SharePoint Online: [https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide](https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide)
