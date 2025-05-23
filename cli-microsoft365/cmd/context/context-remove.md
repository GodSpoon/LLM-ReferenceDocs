-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# context remove

Removes the CLI for Microsoft 365 context in the current working folder

## Usage

```sh
m365 context remove [options]
```

## Options

```md definition-list
`-f, --force`
: Don't prompt for confirmation to remove the context
```

<Global />

## Examples

Removes the CLI for Microsoft 365 context in the current working folder

```sh
m365 context remove
```

Removes the CLI for Microsoft 365 context in the current working folder and does not prompt for confirmation before deleting.

```sh
m365 context remove --force
```

## Response

The command won't return a response on success.
