-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo cdn policy set

Sets CDN policy value for the current SharePoint Online tenant

## Usage

```sh
m365 spo cdn policy set [options]
```

## Options

```md definition-list
`-t, --cdnType [cdnType]`
: Type of CDN to manage. Allowed values are: `Public`, `Private`. Default `Public`.

`-p, --policy <policy>`
: CDN policy to configure. Allowed values are: `IncludeFileExtensions`, `ExcludeRestrictedSiteClassifications`.

`-v, --value <value>`
: Value for the policy to configure.
```

<Global />

## Remarks

Using the `-t, --cdnType` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Set the list of extensions supported by the Public CDN

```sh
m365 spo cdn policy set --cdnType Public --policy IncludeFileExtensions --value CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON
```

## Response

The command won't return a response on success.

## More information

- Use Microsoft 365 CDN with SharePoint Online: [https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide](https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide)
