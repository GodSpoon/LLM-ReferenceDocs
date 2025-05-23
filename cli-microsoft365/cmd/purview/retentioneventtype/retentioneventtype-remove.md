-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# purview retentioneventtype remove

Delete a retention event type

## Usage

```sh
m365 purview retentioneventtype remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The Id of the retention event type.

`-f, --force`
: Don't prompt for confirmation to remove the retention event type.
```

<Global />

## Remarks

:::warning

This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Delete a retention event type by id

```sh
m365 purview retentioneventtype remove --id c37d695e-d581-4ae9-82a0-9364eba4291e
```

## Response

The command won't return a response on success.

## More information

This command is part of a series of commands that have to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created. [Read more about event-based retention here](https://learn.microsoft.com/microsoft-365/compliance/event-driven-retention?view=o365-worldwide)
