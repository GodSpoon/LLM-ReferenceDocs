-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra groupsetting remove

Removes the particular group setting

## Usage

```sh
m365 entra groupsetting remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the group setting to remove

`-f, --force`
: Don't prompt for confirming removing the group setting
```

<Global />

## Remarks

If the specified _id_ doesn't refer to an existing group setting, you will get a `Resource does not exist` error.

## Examples

Remove group setting with id _28beab62-7540-4db1-a23f-29a6018a3848_. Will prompt for confirmation before removing the group setting

```sh
m365 entra groupsetting remove --id 28beab62-7540-4db1-a23f-29a6018a3848
```

Remove group setting with id _28beab62-7540-4db1-a23f-29a6018a3848_ without prompting for confirmation

```sh
m365 entra groupsetting remove --id 28beab62-7540-4db1-a23f-29a6018a3848 --force
```

## Response

The command won't return a response on success.
