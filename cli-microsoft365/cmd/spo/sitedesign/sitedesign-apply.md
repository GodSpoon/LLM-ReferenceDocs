-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign apply

Applies a site design to an existing site collection

## Usage

```sh
m365 spo sitedesign apply [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the site design to apply

`-u, --webUrl <webUrl>`
: The URL of the site to apply the site design to

`--asTask`
: Apply site design as task. Required for large site designs
```

<Global />

## Examples

Apply the site design with ID 9b142c22-037f-4a7f-9017-e9d8c0e34b98 to the site collection https://contoso.sharepoint.com/sites/project-x

```sh
m365 spo sitedesign apply --id 9b142c22-037f-4a7f-9017-e9d8c0e34b98 --webUrl https://contoso.sharepoint.com/sites/project-x
```

Apply large site design to the specified site

```sh
m365 spo sitedesign apply --id 9b142c22-037f-4a7f-9017-e9d8c0e34b98 --webUrl https://contoso.sharepoint.com/sites/project-x --asTask
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ErrorCode": 0,
      "Outcome": "0",
      "OutcomeText": null,
      "Target": null,
      "TargetId": null,
      "Title": "Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ErrorCode  : 0
  Outcome    : 0
  OutcomeText: null
  Target     : null
  TargetId   : null
  Title      : Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ErrorCode,Outcome,Title
  0,0,Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign apply --id "00281728-3bc1-41d3-92b6-8fc493dcf4cc" --webUrl "https://contoso.sharepoint.com/teams/spoteam1"

  Date: 2023-06-22

  ## Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f

  Property | Value
  ---------|-------
  ErrorCode | 0
  Outcome | 0
  Title | Activate feature f151bb39-7c3b-414f-bb36-6bf18872052f
  ```

  </TabItem>
</Tabs>

### `asTask` response

When we make use of the option `asTask`, the response will differ. 

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ID": "781e7556-4489-42bc-aa94-1decf6a395d6",
    "LogonName": "i:0#.f|membership|john@contoso.onmicrosoft.com",
    "SiteDesignID": "00281728-3bc1-41d3-92b6-8fc493dcf4cc",
    "SiteDesignStore": 0,
    "SiteID": "5fc2ea61-7204-41be-9d05-d44f017f958b",
    "WebID": "1c6a5768-89b1-4a68-8c85-9f8db4609bcf"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ID             : 781e7556-4489-42bc-aa94-1decf6a395d6
  LogonName      : i:0#.f|membership|john@contoso.onmicrosoft.com
  SiteDesignID   : 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  SiteDesignStore: 0
  SiteID         : 5fc2ea61-7204-41be-9d05-d44f017f958b
  WebID          : 1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ID,LogonName,SiteDesignID,SiteDesignStore,SiteID,WebID
  781e7556-4489-42bc-aa94-1decf6a395d6,i:0#.f|membership|john@contoso.onmicrosoft.com,00281728-3bc1-41d3-92b6-8fc493dcf4cc,0,5fc2ea61-7204-41be-9d05-d44f017f958b,1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign apply --id "00281728-3bc1-41d3-92b6-8fc493dcf4cc" --webUrl "https://contoso.sharepoint.com/teams/spoteam1" --asTask "true"

  Date: 2023-06-22

  ## 781e7556-4489-42bc-aa94-1decf6a395d6

  Property | Value
  ---------|-------
  ID | 781e7556-4489-42bc-aa94-1decf6a395d6
  LogonName | i:0#.f\|membership\|john@contoso.onmicrosoft.com
  SiteDesignID | 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  SiteDesignStore | 0
  SiteID | 5fc2ea61-7204-41be-9d05-d44f017f958b
  WebID | 1c6a5768-89b1-4a68-8c85-9f8db4609bcf
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
