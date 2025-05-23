-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site admin add 

Adds a user or group as a site collection administrator

## Usage

```sh
m365 spo site admin add [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the SharePoint site

`--userId [userId]`
: The ID of the user to add as a site collection admin

`--userName [userName]`
: The user principal name of the user to add as a site collection admin

`--groupId [groupId]`
: The ID of the Microsoft Entra ID group to add as a site collection admin

`--groupName [groupName]`
: The name of the Microsoft Entra ID group to add as a site collection admin

`--primary`
: If set, will add the user as primary site collection admin. The old primary site collection admin will be replaced and set as secondary site collection admin

`--asAdmin`
: If specified, we will use the SharePoint admin center to execute the command
```

<Global />

## Remarks

:::info

To use this command with the `--asAdmin` mode, you have to have permissions to access the tenant admin site.

Without this parameter, you have to have site collection admin permissions for the requested site.

:::

## Examples

Add user as primary site collection administrator

```sh
m365 spo site admin add --siteUrl https://contoso.sharepoint.com --userId 600713c5-53c6-4f24-b454-3c35e22b2639 --primary
```

Adds group as secondary site collection administrator as SharePoint admin

```sh
m365 spo site admin add --siteUrl https://contoso.sharepoint.com --groupName SP_Administrators --asAdmin
```
## Response

The command won't return a response on success.
