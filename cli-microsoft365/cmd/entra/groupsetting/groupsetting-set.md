-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra groupsetting set

Updates the particular group setting

## Usage

```sh
m365 entra groupsetting set [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the group setting to update
```

<Global />

## Remarks

To update a group setting, you have to specify the ID of the group setting. You can retrieve the ID of the group setting using the [entra groupsetting list](./groupsetting-list.mdx) command.

To update values for the different properties specified in the group setting, include additional options that match the property in the group setting. For example `--ClassificationList 'HBI, MBI, LBI, GDPR'` will set the list of classifications to use on modern SharePoint sites.

If you don't specify a value for the particular property, it will remain unchanged. To find out which properties are available for the particular group setting, use the [entra groupsetting get](./groupsetting-get.mdx) command.

If the specified id doesn't reference a valid group setting, you will get a _Resource 'xyz' does not exist or one of its queried reference-property objects are not present._ error.

## Examples

Configure classification for modern SharePoint sites

```sh
m365 entra groupsetting set --id c391b57d-5783-4c53-9236-cefb5c6ef323 --UsageGuidelinesUrl https://contoso.sharepoint.com/sites/compliance --ClassificationList 'HBI, MBI, LBI, GDPR' --DefaultClassification MBI
```

## Response

The command won't return a response on success.
