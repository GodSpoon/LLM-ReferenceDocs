-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo applicationcustomizer remove

Removes an application customizer that is added to a site

## Usage

```sh
m365 spo applicationcustomizer remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The url of the site.

`-t, --title [title]`
: The title of the Application Customizer. Specify either `title`, `id` or `clientSideComponentId`.

`-i, --id [id]`
: The id of the Application Customizer. Specify either `title`, `id` or `clientSideComponentId`.

`-c, --clientSideComponentId [clientSideComponentId]`
: The Client Side Component Id (GUID) of the application customizer. Specify either `title`, `id` or `clientSideComponentId`.

`-s, --scope [scope]`
: Scope of the application customizer. Allowed values: `Site`, `Web`, and `All`. Defaults to `All`.

`-f, --force`
: Don't prompt for confirming removal of the application customizer.
```

<Global />

## Remarks

If the command finds multiple application customizers with the specified title or clientSideComponentId, it will prompt you to disambiguate which customizer it should remove, listing the discovered IDs.

This command can be used for removing an application customizer added to a specific site. To remove an application customizer that's installed tenant-wide, view our dedicated [spo tenant applicationcustomizer remove](../tenant/tenant-applicationcustomizer-remove.mdx) command.

## Examples

Remove an application customizer by id.

```sh
m365 spo applicationcustomizer remove --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales
```

Remove an application customizer by title.

```sh
m365 spo applicationcustomizer remove --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```

Remove an application customizer by clientSideComponentId.

```sh
m365 spo applicationcustomizer remove --clientSideComponentId 7096cded-b83d-4eab-96f0-df477ed7c0bc --webUrl https://contoso.sharepoint.com/sites/sales
```

Remove an application customizer by its id without prompting for confirmation.

```sh
m365 spo applicationcustomizer remove --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales --force
```

Remove an application customizer from a site collection by its id without prompting for confirmation.

```sh
m365 spo applicationcustomizer remove --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales --force --scope Site
```

Remove an application customizer from a site by its id without prompting for confirmation.

```sh
m365 spo applicationcustomizer remove --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales --force --scope Web
```

## Remarks

This command can be used for removing an application customizer from a specific site. To remove a tenant-wide installed application customizer, view our dedicated [spo tenant applicationcustomizer remove](../tenant/tenant-applicationcustomizer-remove.mdx) command.

## Response

The command won't return a response on success.
