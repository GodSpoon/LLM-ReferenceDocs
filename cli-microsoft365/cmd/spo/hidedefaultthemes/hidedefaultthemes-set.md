-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo hidedefaultthemes set

Sets the value of the HideDefaultThemes setting

## Usage

```sh
m365 spo hidedefaultthemes set [options]
```

## Options

```md definition-list
`--hideDefaultThemes <hideDefaultThemes>`
: Set to `true` to hide default themes and to `false` to show them.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Hide default themes and allow users to use organization themes only.

```sh
m365 spo hidedefaultthemes set --hideDefaultThemes true
```

## Response

The command won't return a response on success.

## More information

- SharePoint site theming: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)
