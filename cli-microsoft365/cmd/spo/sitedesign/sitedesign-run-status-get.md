-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign run status get

Gets information about the site scripts executed for the specified site design

## Usage

```sh
m365 spo sitedesign run status get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site for which to get the information

`-i, --runId <runId>`
: ID of the site design applied to the site as retrieved using `spo sitedesign run list`
```

<Global />

## Remarks

For text output mode, displays the name of the action, site script and the outcome of the action. For JSON output mode, displays all available information.

## Examples

List information about site scripts executed for the specified site design

```sh
m365 spo sitedesign run status get --webUrl https://contoso.sharepoint.com/sites/team-a --runId b4411557-308b-4545-a3c4-55297d5cd8c8
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ActionIndex": 0,
      "ActionKey": "00000000-0000-0000-0000-000000000000",
      "ActionTitle": "Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f",
      "LastModified": "1687422166000",
      "OrdinalIndex": 0,
      "OutcomeCode": 0,
      "OutcomeText": null,
      "SiteScriptID": "0c88bed7-943b-42aa-8fef-8fb69eebe3fe",
      "SiteScriptIndex": 0,
      "SiteScriptTitle": "Contoso"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ActionIndex    : 0
  ActionKey      : 00000000-0000-0000-0000-000000000000
  ActionTitle    : Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f
  LastModified   : 1687422166000
  OrdinalIndex   : 0
  OutcomeCode    : 0
  OutcomeText    : null
  SiteScriptID   : 0c88bed7-943b-42aa-8fef-8fb69eebe3fe
  SiteScriptIndex: 0
  SiteScriptTitle: Contoso
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ActionIndex,ActionKey,ActionTitle,LastModified,OrdinalIndex,OutcomeCode,SiteScriptID,SiteScriptIndex,SiteScriptTitle
  0,00000000-0000-0000-0000-000000000000,Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f,1687422166000,0,0,0c88bed7-943b-42aa-8fef-8fb69eebe3fe,0,Contoso
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign run status get --webUrl "https://contoso.sharepoint.com/teams/team1" --runId "8d41a2b7-ffb9-487c-994a-d25cf1b74f6a"

  Date: 2023-06-22

  Property | Value
  ---------|-------
  ActionIndex | 0
  ActionKey | 00000000-0000-0000-0000-000000000000
  ActionTitle | Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f
  LastModified | 1687422166000
  OrdinalIndex | 0
  OutcomeCode | 0
  SiteScriptID | 0c88bed7-943b-42aa-8fef-8fb69eebe3fe
  SiteScriptIndex | 0
  SiteScriptTitle | Contoso
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
