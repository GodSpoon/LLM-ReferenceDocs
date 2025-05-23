-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo site groupify

Connects site collection to an Microsoft 365 Group

## Usage

```sh
m365 spo site groupify [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site collection being connected to new Microsoft 365 Group

`-a, --alias <alias>`
: The email alias for the new Microsoft 365 Group that will be created

`-n, --displayName <displayName>`
: The name of the new Microsoft 365 Group that will be created

`-d, --description [description]`
: The group’s description

`-c, --classification [classification]`
: The classification value, if classifications are set for the organization. If no value is provided, the default classification will be set, if one is configured

`--isPublic`
: Determines the Microsoft 365 Group’s privacy setting. If set, the group will be public, otherwise it will be private

`--keepOldHomepage`
: For sites that already have a modern page set as homepage, set this option, to keep it as the homepage
```

<Global />

## Remarks

:::warning

This command is based on a SharePoint API that is currently in preview and is subject to change once the API reached general availability.

:::

When connecting site collection to an Microsoft 365 Group, SharePoint will create a new group using the specified information. If a group with the same name already exists, you will get a `The group alias already exists.` error.

## Examples

Connect site collection to an Microsoft 365 Group

```sh
m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A'
```

Connect site collection to an Microsoft 365 Group and make the group public

```sh
m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A' --isPublic
```

Connect site collection to an Microsoft 365 Group and set the group classification

```sh
m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A' --classification HBI
```

Connect site collection to an Microsoft 365 Group and keep the old home page

```sh
m365 spo site groupify --url https://contoso.sharepoin.com/sites/team-a --alias team-a --displayName 'Team A' --keepOldHomepage
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "DocumentsUrl": null,
    "ErrorMessage": null,
    "GroupId": "a82ece01-09bd-4585-8247-7a0b72c97377",
    "SiteStatus": 2,
    "SiteUrl": "https://contoso.sharepoint.com/sites/team-a"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  DocumentsUrl: null
  ErrorMessage: null
  GroupId     : c962d943-c452-4930-9574-2440c8f29a15
  SiteStatus  : 2
  SiteUrl     : https://contoso.sharepoint.com/sites/team-a
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  GroupId,SiteStatus,SiteUrl
  615897ce-8112-4c5b-8ff6-14f8862a88fe,2,https://contoso.sharepoint.com/sites/team-a
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo site groupify --url "https://contoso.sharepoint.com/sites/team-a" --alias "team-a" --displayName "team-a"

  Date: 2023-06-21

  Property | Value
  ---------|-------
  GroupId | 1db24833-3784-49fe-b683-1f913888774d
  SiteStatus | 2
  SiteUrl | https://contoso.sharepoint.com/sites/team-a
  ```

  </TabItem>
</Tabs>

## More information

- Overview of the "Log in to new Microsoft 365 group" feature: [https://learn.microsoft.com/sharepoint/dev/features/groupify/groupify-overview](https://learn.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)
