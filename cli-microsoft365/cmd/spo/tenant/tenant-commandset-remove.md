-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo tenant commandset remove

Removes a ListView Command Set that is installed tenant-wide

## Usage

```sh
m365 spo tenant commandset remove [options]
```

## Options

```md definition-list
`-t, --title [title]`
: The title of the ListView Command Set. Specify either `title`, `id`, or `clientSideComponentId`.

`-i, --id [id]`
: The id of the ListView Command Set. Specify either `title`, `id`, or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the ListView Command Set. Specify either `title`, `id`, or `clientSideComponentId`.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

This command can be used for removing a ListView Command Set that's installed tenant-wide. To remove a ListView Command Set from a specific site, view our dedicated [spo commandset remove](../commandset/commandset-remove.mdx) command.

## Examples

Removes an ListView Command Set by title.

```sh
m365 spo tenant commandset remove --title "Some command set"
```

Removes a ListView Command Set by id.

```sh
m365 spo tenant commandset remove --id 3
```

Removes a ListView Command Set by clientSideComponentId.

```sh
m365 spo tenant commandset remove --clientSideComponentId 7096cded-b83d-4eab-96f0-df477ed7c0bc
```

## Response

The command won't return a response on success.
