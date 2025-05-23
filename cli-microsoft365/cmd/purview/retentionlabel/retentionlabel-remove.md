-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# purview retentionlabel remove

Delete a retention label

## Usage

```sh
m365 purview retentionlabel remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The Id of the retention label.

`-f, --force`
: Don't prompt for confirming to remove the label.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Delete a retention label

```sh
m365 purview retentionlabel remove --id 'e554d69c-0992-4f9b-8a66-fca3c4d9c531'
```

## Response

The command won't return a response on success.
