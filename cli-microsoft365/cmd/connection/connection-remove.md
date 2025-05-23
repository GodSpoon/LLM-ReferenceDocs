-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# connection remove

Remove the specified connection

## Usage

```sh
m365 connection remove [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the connection to remove.

`-f, --force`
: Don't prompt for confirmation to remove the connection.
```

<Global />

## Remarks

The value for `--name` can be found by running [m365 connection list](connection-list.mdx). 

## Examples

Remove an existing connection

```sh
m365 connection remove --name '0bb7cb89-7fae-4775-a01a-c372cc167371'
```

Remove an existing connection without prompting for confirmation

```sh
m365 connection remove --name '0bb7cb89-7fae-4775-a01a-c372cc167371' --force
```

## Response

The command won't return a response on success.
