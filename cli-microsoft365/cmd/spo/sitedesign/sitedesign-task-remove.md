-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo sitedesign task remove

Removes the specified site design scheduled for execution

## Usage

```sh
m365 spo sitedesign task remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the site design task to remove

`-f, --force`
: Don't prompt for confirming removing the site design task
```

<Global />

## Examples

Removes the specified site design task with id _6ec3ca5b-d04b-4381-b169-61378556d76e_ scheduled for execution without prompting confirmation

```sh
m365 spo sitedesign task remove --id 6ec3ca5b-d04b-4381-b169-61378556d76e --force
```

Removes the specified site design task with id _6ec3ca5b-d04b-4381-b169-61378556d76e_ scheduled for execution with prompt for confirmation before removing

```sh
m365 spo sitedesign task remove --id 6ec3ca5b-d04b-4381-b169-61378556d76e
```

## Response

The command won't return a response on success.

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
