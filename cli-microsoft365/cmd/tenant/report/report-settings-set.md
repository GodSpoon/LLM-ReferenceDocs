-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# tenant report settings set

Update tenant-level settings for Microsoft 365 reports

## Usage

```sh
m365 tenant report settings set [options]
```

## Options

```md definition-list
`-d, --displayConcealedNames <displayConcealedNames>`
: Determines whether all reports conceal user information such as usernames, groups, and sites. If false, all reports show identifiable information.
```

<Global />

## Examples

Configure the tenant to display concealed user information in Microsoft 365 reports

```sh
m365 tenant report settings set --displayConcealedNames true
```

## Response

The command won't return a response on success
