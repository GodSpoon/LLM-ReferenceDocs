-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# context option set

Allows to add a new name for the option and value to the local context file.

## Usage

```sh
m365 context option set [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The option name for which we will define the value

`-v, --value <value>`
: Default value for the option
```

<Global />

## Examples

Define a new default value for name listName in the context

```sh
m365 context option set --name 'listName' --value 'testList'
```

## Response

The command won't return a response on success.
