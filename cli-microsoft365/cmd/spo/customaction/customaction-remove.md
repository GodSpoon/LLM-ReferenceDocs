-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo customaction remove

Removes specified custom action from site or site collection

## Usage

```sh
m365 spo customaction remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: Id (GUID) of the custom action to remove. Specify either `id` or `title`.

`-t, --title [title]`
: Title of the user custom action to retrieve information for. Specify either `id` or `title`.

`-u, --webUrl <webUrl>`
: Url of the site or site collection to remove the custom action from.

`-s, --scope [scope]`
: Scope of the custom action. Allowed values `Site`, `Web`, `All`. Default `All`.

`-f, --force`
: Don't prompt for confirming removal of a user custom action.
```

<Global />

## Remarks

If the command finds multiple user custom actions with the specified title, it will prompt you to disambiguate which user custom action it should use, listing the discovered IDs.

## Examples

Removes user custom action with given ID located in the specified site or site collection.

```sh
m365 spo customaction remove --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --webUrl https://contoso.sharepoint.com/sites/test
```

Removes user custom action with given Title located in the specified site or site collection.

```sh
m365 spo customaction remove --title "YourAppCustomizer" --webUrl https://contoso.sharepoint.com/sites/test
```

Removes user custom action with given ID located in the specified site or site collection. Skips the confirmation prompt message.

```sh
m365 spo customaction remove --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --webUrl https://contoso.sharepoint.com/sites/test --force
```

Removes user custom action with given Title located in the specified site or site collection. Skips the confirmation prompt message.

```sh
m365 spo customaction remove --title "YourAppCustomizer" --webUrl https://contoso.sharepoint.com/sites/test --force
```

Removes user custom action with given ID located in the specified site collection.

```sh
m365 spo customaction remove --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --webUrl https://contoso.sharepoint.com/sites/test --scope Site
```

Removes user custom action with given Title located in site collection _https://contoso.sharepoint.com/sites/test_

```sh
m365 spo customaction remove --title "YourAppCustomizer" --webUrl https://contoso.sharepoint.com/sites/test --scope Site
```

Removes user custom action with given ID located in the specified site.

```sh
m365 spo customaction remove --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --webUrl https://contoso.sharepoint.com/sites/test --scope Web
```

Removes user custom action with given Title located in the specified site.

```sh
m365 spo customaction remove --title "YourAppCustomizer" --webUrl https://contoso.sharepoint.com/sites/test --scope Web
```

## Response

The command won't return a response on success.

## More information

- UserCustomAction REST API resources: [https://msdn.microsoft.com/en-us/library/office/dn531432.aspx#bk_UserCustomAction](https://msdn.microsoft.com/en-us/library/office/dn531432.aspx#bk_UserCustomAction)
