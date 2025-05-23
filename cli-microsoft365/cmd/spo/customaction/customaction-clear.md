-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo customaction clear

Deletes all custom actions from site or site collection

## Usage

```sh
m365 spo customaction clear [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Url of the site or site collection to clear the custom actions from.

`-s, --scope [scope]`
: Scope of the custom action. Allowed values `Site`, `Web`, `All`. Default `All`.

`-f, --force`
: Don't prompt for confirming removing all custom actions.
```

<Global />

## Examples

Clears all user custom actions for both site and site collection. Skips the confirmation prompt message.

```sh
m365 spo customaction clear --webUrl https://contoso.sharepoint.com/sites/test --force
```

Clears all user custom actions for the specified site. 

```sh
m365 spo customaction clear --webUrl https://contoso.sharepoint.com/sites/test --scope Web
```

Clears all user custom actions for the specified site collection.

```sh
m365 spo customaction clear --webUrl https://contoso.sharepoint.com/sites/test --scope Site
```

## Response

The command won't return a response on success.
