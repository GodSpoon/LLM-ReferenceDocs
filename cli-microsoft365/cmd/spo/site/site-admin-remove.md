-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site admin remove

Removes a user or group as site collection administrator

## Usage

```sh
m365 spo site admin remove [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the SharePoint site

`--userId [userId]`
: The ID of the user to remove as a site collection admin

`--userName [userName]`
: The user principal name of the user to remove as a site collection admin

`--groupId [groupId]`
: The ID of the Microsoft Entra ID group to remove as a site collection admin

`--groupName [groupName]`
: The name of the Microsoft Entra ID group to remove as a site collection admin

`--asAdmin`
: If specified, we will use the SharePoint admin center to execute the command

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Remarks

:::info

To use this command with the `--asAdmin` mode, you have to have permissions to access the tenant admin site.

Without this parameter, you have to have site collection admin permissions for the requested site.

:::

## Examples

Removes user as site collection admin

```sh
m365 spo site admin remove --siteUrl https://contoso.sharepoint.com --userId 600713c5-53c6-4f24-b454-3c35e22b2639
```

Removes group as site collection admin without prompting for confirmation as SharePoint Admin

```sh
m365 spo site admin remove --siteUrl https://contoso.sharepoint.com --groupName SP_Administrators --force --asAdmin
```
## Response

The command won't return a response on success.
