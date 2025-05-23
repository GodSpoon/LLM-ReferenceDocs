-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo cdn origin add

Adds CDN origin to the current SharePoint Online tenant

## Usage

```sh
m365 spo cdn origin add [options]
```

## Options

```md definition-list
`-t, --type [type]`
: Type of CDN to manage. Allowed values are: `Public`, `Private`. Default `Public`.

`-r, --origin <origin>`
: Origin to add to the current CDN configuration.
```

<Global />

## Remarks

Using the `-t, --type` option you can choose whether you want to manage the settings of the Public (default) or Private CDN. If you don't use the option, the command will use the Public CDN.

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::
    
## Examples

Add _*/CDN_ to the list of origins of the Public CDN.

```sh
m365 spo cdn origin add --type Public --origin */CDN
```

## Response

The command won't return a response on success.

## More information

- Use Microsoft 365 CDN with SharePoint Online: [https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide](https://learn.microsoft.com/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide)
