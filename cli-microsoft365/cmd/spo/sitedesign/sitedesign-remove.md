-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo sitedesign remove

Removes the specified site design

## Usage

```sh
m365 spo sitedesign remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: Site design ID

`-f, --force`
: Don't prompt for confirming removing the site design
```

<Global />

## Remarks

If the specified `id` doesn't refer to an existing site design, you will get a `File not found` error.

## Examples

Remove site design with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_. Will prompt for confirmation before removing the design

```sh
m365 spo sitedesign remove --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a
```

Remove site design with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_ without prompting for confirmation

```sh
m365 spo sitedesign remove --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
