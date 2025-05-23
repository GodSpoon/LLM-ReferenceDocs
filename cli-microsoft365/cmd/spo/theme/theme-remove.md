-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo theme remove

Removes existing theme

## Usage

```sh
m365 spo theme remove [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the theme to remove

`-f, --force`
: Do not prompt for confirmation before removing theme
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Remove theme. Will prompt for confirmation before removing the theme

```sh
m365 spo theme remove --name Contoso-Blue
```

Remove theme without prompting for confirmation

```sh
m365 spo theme remove --name Contoso-Blue --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint site theming: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)
