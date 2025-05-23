-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra siteclassification disable

Disables site classification

## Usage

```sh
m365 entra siteclassification disable [options]
```

## Options

```md definition-list
`-f, --force`
: Don't prompt for confirming disabling site classification.
```

<Global />

## Examples

Disable site classification.

```sh
m365 entra siteclassification disable
```

Disable site classification without confirmation.

```sh
m365 entra siteclassification disable --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint "modern" sites classification: [https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification](https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)
