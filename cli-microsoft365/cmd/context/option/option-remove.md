-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# context option remove

Removes an already available name from local context file.

## Usage

```sh
m365 context option remove [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the option which will be deleted from the context

`-f, --force`
: Don't prompt for confirming removing the option
```

<Global />

## Examples

Removes an already available name from the local context file

```sh
m365 context option remove --name "listName"
```

Removes an already available name from the local context file without confirmation

```sh
m365 context option remove --name "listName" --force
```

## Response

The command won't return a response on success.
