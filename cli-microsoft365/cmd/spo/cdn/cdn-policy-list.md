-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo cdn policy list

Lists CDN policies settings for the current SharePoint Online tenant

## Usage

```sh
m365 spo cdn policy list [options]
```

## Options

```md definition-list
`-t, --cdnType [cdnType]`
: Type of CDN to manage. Allowed values are: `Public`, `Private`. Default `Public`.
```

<Global />

## Remarks

Using the `-t, --cdnType` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Show the list of policies configured for the Public CDN.

```sh
m365 spo cdn policy list
```

Show the list of policies configured for the Private CDN.

```sh
m365 spo cdn policy list --cdnType Private
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Policy": "IncludeFileExtensions",
      "Value": "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Policy                                Value
  ------------------------------------  -----------------------------------------------------
  IncludeFileExtensions                 CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Policy,Value
  IncludeFileExtensions,"CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo cdn policy list

  Date: 10/2/2023

  Property | Value
  ---------|-------
  Policy | IncludeFileExtensions
  Value | CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON
  ```

  </TabItem>
</Tabs>

## More information

- Use Microsoft 365 CDN with SharePoint Online: [https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide](https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide)
