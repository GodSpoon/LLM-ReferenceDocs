-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# connection set

Rename the specified connection

## Usage

```sh
m365 connection set [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the connection to update.

`--newName <newName>`
: The new name of the connection.
```

<Global />

## Remarks

The value for `--name` can be found by running [m365 connection list](connection-list.mdx). You can update the name of a connection to any value to make switching connections easier. 

## Examples

Update an existing connection

```sh
m365 connection set --name '0bb7cb89-7fae-4775-a01a-c372cc167371' --newName 'myworkaccount'
```

## Response

The command won't return a response on success.
