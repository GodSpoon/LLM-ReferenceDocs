-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo sitescript remove

Removes the specified site script

## Usage

```sh
m365 spo sitescript remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: Site script ID

`-f, --force`
: Don't prompt for confirming removing the site script
```

<Global />

## Remarks

If the specified `id` doesn't refer to an existing site script, you will get a `File not found` error.

## Examples

Remove site script with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_. Will prompt for confirmation before removing the script

```sh
m365 spo sitescript remove --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a
```

Remove site script with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_ without prompting for confirmation

```sh
m365 spo sitescript remove --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
