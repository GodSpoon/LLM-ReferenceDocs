-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo tenant site rename

Renames the URL and title of a site collection

## Usage

```sh
m365 spo tenant site rename [options]
```

## Options

```md definition-list
`-u, --url <url>`
: The URL of the site to rename

`--newUrl <newUrl>`
: New URL for the site collection

`--newTitle [newTitle]`
: New title for the site

`--suppressMarketplaceAppCheck`
: Suppress marketplace app check

`--suppressWorkflow2013Check`
: Suppress 2013 workflow check

`--wait`
: Wait for the job to complete
```

<Global />

## Remarks

Renaming site collections is by default asynchronous and depending on the current state of Microsoft 365, might take up to few minutes. If you're building a script with steps that require the operation to complete fully, you should use the `--wait` flag. When using this flag, the `spo tenant site rename` command  will keep running until it receives confirmation from Microsoft 365 that the site rename operation has completed.

:::info

To use this command you must have permissions to access the tenant admin site.

:::
    
## Examples

Starts the rename of the site collection with name "samplesite" to "renamed" without modifying the title

```sh
m365 spo tenant site rename --url http://contoso.sharepoint.com/samplesite --newUrl http://contoso.sharepoint.com/renamed
```

Starts the rename of the site collection with name "samplesite" to "renamed" modifying the title of the site to "New Title"

```sh
m365 spo tenant site rename --url http://contoso.sharepoint.com/samplesite --newUrl http://contoso.sharepoint.com/renamed --newTitle "New Title"
```

Renames the specified site collection and waits for the operation to complete

```sh
m365 spo tenant site rename --url http://contoso.sharepoint.com/samplesite --newUrl http://contoso.sharepoint.com/renamed --newTitle "New Title" --wait
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "odata.metadata": "https://contoso-admin.sharepoint.com/_api/$metadata#SP.ApiData.SiteRenameJobEntityDatas/@Element",
    "odata.type": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "odata.id": "https://contoso-admin.sharepoint.com/_api/onboardingservicesbeta/siterenamejobs",
    "odata.editLink": "onboardingservicesbeta/siterenamejobs",
    "Option": 0,
    "Reserve": null,
    "OperationId": "00000000-0000-0000-0000-000000000000",
    "SkipGestures": "",
    "SourceSiteUrl": "https://contoso.sharepoint.com/sites/team1",
    "TargetSiteTitle": null,
    "TargetSiteUrl": "https://contoso.sharepoint.com/sites/team2",
    "ErrorCode": 0,
    "ErrorDescription": null,
    "JobId": "ec3c9add-8b39-4355-b3c7-22f81331f897",
    "JobState": "NotStarted",
    "ParentId": "00000000-0000-0000-0000-000000000000",
    "SiteId": "ffdab06c-3df6-4e60-a46a-fc8a51f32be3",
    "TriggeredBy": "john@contoso.onmicrosoft.com"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ErrorCode       : 0
  ErrorDescription: null
  JobId           : fc326673-83c4-4fbc-bd7b-e561ec30de83
  JobState        : NotStarted
  OperationId     : 00000000-0000-0000-0000-000000000000
  Option          : 0
  ParentId        : 00000000-0000-0000-0000-000000000000
  Reserve         : null
  SiteId          : 754383f6-cf1e-4e55-8761-e1d2c4f5319b
  SkipGestures    :
  SourceSiteUrl   : https://contoso.sharepoint.com/sites/team1
  TargetSiteTitle : null
  TargetSiteUrl   : https://contoso.sharepoint.com/sites/team2
  TriggeredBy     : john@contoso.onmicrosoft.com
  odata.editLink  : onboardingservicesbeta/siterenamejobs
  odata.id        : https://contoso-admin.sharepoint.com/_api/onboardingservicesbeta/siterenamejobs
  odata.metadata  : https://contoso-admin.sharepoint.com/_api/$metadata#SP.ApiData.SiteRenameJobEntityDatas/@Element
  odata.type      : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  odata.metadata,odata.type,odata.id,odata.editLink,Option,OperationId,SkipGestures,SourceSiteUrl,TargetSiteUrl,ErrorCode,JobId,JobState,ParentId,SiteId,TriggeredBy
  https://contoso-admin.sharepoint.com/_api/$metadata#SP.ApiData.SiteRenameJobEntityDatas/@Element,EXAMPLE_SECRET_VALUE_PLACEHOLDER,https://contoso-admin.sharepoint.com/_api/onboardingservicesbeta/siterenamejobs,onboardingservicesbeta/siterenamejobs,0,00000000-0000-0000-0000-000000000000,,https://contoso.sharepoint.com/sites/team1,https://contoso.sharepoint.com/sites/team2,0,5ff99cdd-0a71-41e4-9ffa-055cd1462fe8,NotStarted,00000000-0000-0000-0000-000000000000,2f7623fb-cae9-40de-b0f4-59b0bc545982,john@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo tenant site rename --url "https://contoso.sharepoint.com/sites/team1" --newUrl "https://contoso.sharepoint.com/sites/team2"

  Date: 2023-06-21

  Property | Value
  ---------|-------
  odata.metadata | https://contoso-admin.sharepoint.com/\_api/$metadata#SP.ApiData.SiteRenameJobEntityDatas/@Element
  odata.type | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  odata.id | https://contoso-admin.sharepoint.com/\_api/onboardingservicesbeta/siterenamejobs
  odata.editLink | onboardingservicesbeta/siterenamejobs
  Option | 0
  OperationId | 00000000-0000-0000-0000-000000000000
  SkipGestures |
  SourceSiteUrl | https://contoso.sharepoint.com/sites/team1
  TargetSiteUrl | https://contoso.sharepoint.com/sites/team2
  ErrorCode | 0
  JobId | 9857a6ba-d1ae-481f-96eb-3a3172659502
  JobState | NotStarted
  ParentId | 00000000-0000-0000-0000-000000000000
  SiteId | c0dd6f7a-5998-49a4-847f-c2b5d247d5e2
  TriggeredBy | john@contoso.onmicrosoft.com
  ```

  </TabItem>
</Tabs>
