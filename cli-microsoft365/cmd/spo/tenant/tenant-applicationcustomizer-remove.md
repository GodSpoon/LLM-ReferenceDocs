-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo tenant applicationcustomizer remove

Removes an application customizer that is installed tenant-wide

## Usage

```sh
m365 spo tenant applicationcustomizer remove [options]
```

## Options

```md definition-list
`-t, --title [title]`
: The title of the Application Customizer. Specify either `title`, `id`, or `clientSideComponentId`.

`-i, --id [id]`
: The id of the Application Customizer. Specify either `title`, `id`, or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the application customizer. Specify either `title`, `id`, or `clientSideComponentId`.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

This command can be used for removing an application customizer that's installed tenant-wide. To remove an application customizer from a specific site, view our dedicated [spo applicationcustomizer remove](../applicationcustomizer/applicationcustomizer-remove.mdx) command.

## Examples

Removes an application customizer by title.

```sh
m365 spo tenant applicationcustomizer remove --title "Some customizer"
```

Removes an application customizer by id.

```sh
m365 spo tenant applicationcustomizer remove --id 3
```

Removes an application customizer by clientSideComponentId.

```sh
m365 spo tenant applicationcustomizer remove --clientSideComponentId "7096cded-b83d-4eab-96f0-df477ed7c0bc"
```

## Response

The command won't return a response on success.
