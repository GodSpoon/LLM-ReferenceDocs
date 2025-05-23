-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra siteclassification enable

Enables site classification configuration

## Usage

```sh
m365 entra siteclassification enable [options]
```

## Options

```md definition-list
`-c, --classifications <classifications>`
: Comma-separated list of classifications to enable in the tenant.

`-d, --defaultClassification <defaultClassification>`
: Classification to use by default.

`-u, --usageGuidelinesUrl [usageGuidelinesUrl]`
: URL with usage guidelines for members.

`-g, --guestUsageGuidelinesUrl [guestUsageGuidelinesUrl]`
: URL with usage guidelines for guests.
```

<Global />

## Examples

Enable site classification.

```sh
m365 entra siteclassification enable --classifications "High, Medium, Low" --defaultClassification "Medium"
```

Enable site classification with a usage guidelines URL.

```sh
m365 entra siteclassification enable --classifications "High, Medium, Low" --defaultClassification "Medium" --usageGuidelinesUrl "http://aka.ms/pnp"
```

Enable site classification with usage guidelines URLs for guests and members.

```sh
m365 entra siteclassification enable --classifications "High, Medium, Low" --defaultClassification "Medium" --usageGuidelinesUrl "http://aka.ms/pnp" --guestUsageGuidelinesUrl "http://aka.ms/pnp"
```

## Response

The command won't return a response on success.

## More information

- SharePoint "modern" sites classification: [https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification](https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)
