-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra siteclassification set

Updates site classification configuration

## Usage

```sh
m365 entra siteclassification set [options]
```

## Options

```md definition-list
`-c, --classifications [classifications]`
: Comma-separated list of classifications.

`-d, --defaultClassification [defaultClassification]`
: Classification to use by default.

`-u, --usageGuidelinesUrl [usageGuidelinesUrl]`
: URL with usage guidelines for members.

`-g, --guestUsageGuidelinesUrl [guestUsageGuidelinesUrl]`
: URL with usage guidelines for guests.
```

<Global />


## Examples

Update Microsoft 365 Tenant site classification configuration.

```sh
m365 entra siteclassification set --classifications "High, Medium, Low" --defaultClassification "Medium"
```

Update only the default classification.

```sh
m365 entra siteclassification set --defaultClassification "Low"
```

Update site classification with a usage guidelines URL.

```sh
m365 entra siteclassification set --usageGuidelinesUrl "http://aka.ms/pnp"
```

Update site classification with usage guidelines URLs for guests and members.

```sh
m365 entra siteclassification set --usageGuidelinesUrl "http://aka.ms/pnp" --guestUsageGuidelinesUrl "http://aka.ms/pnp"
```

## Response

The command won't return a response on success.

## More information

- SharePoint "modern" sites classification: [https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification](https://learn.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)
