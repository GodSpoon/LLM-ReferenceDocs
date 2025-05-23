-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
﻿import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# search

Uses the Microsoft Search to query Microsoft 365 data

## Usage

```sh
m365 search [options]
```

## Options

```md definition-list
`-q, --queryText [queryText]`
: Query to be executed in Keyword Query Language (KQL) format.

`-s, --scopes <scopes>`
: Comma-separated list of scopes for the search request. Allowed values are `chatMessage`, `message`, `event`, `drive`, `driveItem`, `list`, `listItem`, `site`, `bookmark`, `acronym`, or `person`.

`--startIndex [startIndex]`
: Set the number that indicates the 0-based starting point to list search results on the page. The default value is 0.

`--pageSize [pageSize]`
: Set the number that indicates the number of results to be returned for a page. The default is 25 results. The maximum is 500 results.

`--allResults`
: Set to get all search results from all pages.

`--resultsOnly`
: Set to get only the results form the query response.

`--enableTopResults`
: Use to get the first three messages in the response are sorted by relevance. Use this option only when scopes is set to message type.

`--select [select]`
: Comma-separated list of properties to return in the search results.

`--sortBy [sortBy]`
: Comma-separated list of properties to sort search results.

`--enableSpellingSuggestion`
: Set to get the suggested spelling correction information for typos in the user query.

`--enableSpellingModification`
: Set to get the search results for the corrected query when there are no results for the original query with typos, and get the corresponding correction information.
```

<Global />

## Remarks

The `queryText` option supports [Keyword Query Language](https://learn.microsoft.com/graph/api/resources/search-api-overview#keyword-query-language-kql-support) (KQL).

The `sortBy` option allows to specify the order. By default, the order is ascending. If you want to apply descending order, add `:desc` to the property name, like `createdDateTime:desc`.

## Examples

Queries messages in the current user mailbox that contain the string "contoso" in any part of the message (the sender name, subject, message body, or any attachments). The query returns the first 100 results.

```sh
m365 search --scopes 'message' --queryText 'contoso' --pageSize 100
```

Queries list items and sites that contain the string "accountt" and requests a spelling modification for the query.

```sh
m365 search --scopes 'listItem, site' --queryText 'accountt' --enableSpellingSuggestion --enableSpellingModification
```

Search for file report.xlsl in specific folder of user personal OneDrive

```sh
m365 search --scopes 'driveItem' --queryText 'filename:report.xlsl AND path:\"https://contoso-my.sharepoint.com/personal/john.doe_contoso_com/Documents/Reports/2024\"'
```

Search for all sites

```sh
m365 search --scopes 'site' --queryText 'site:\"https://contoso-my.sharepoint.com/personal/*\"'
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "searchTerms": [
      "openapi"
    ],
    "hitsContainers": [
      {
        "hits": [
          {
            "hitId": "012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC",
            "rank": 1,
            "summary": "<ddd/><c0>OpenAPI</c0> Specification v3.1.0 | Introduction, Definitions, & More https://spec.openapis.org<ddd/><c0>OpenAPI</c0> Specification v3.1.0 Version 3.1.0 Published 15 February 2021 Latest editor's <ddd/>",
            "resource": {
              "@odata.type": "#microsoft.graph.driveItem",
              "size": 2980854,
              "fileSystemInfo": {
                "createdDateTime": "2023-11-18T20:26:55Z",
                "lastModifiedDateTime": "2023-11-18T10:10:10Z"
              },
              "listItem": {
                "@odata.type": "#microsoft.graph.listItem",
                "fields": {},
                "id": "5a85c2cd-4b8c-487b-8d01-5368795edf50"
              },
              "id": "012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC",
              "createdBy": {
                "user": {
                  "displayName": "John Doe",
                  "email": "john.doe@contoso.onmicrosoft.com"
                }
              },
              "createdDateTime": "2023-11-18T20:26:55Z",
              "lastModifiedBy": {
                "user": {
                  "displayName": "John Doe",
                  "email": "john.doe@contoso.onmicrosoft.com"
                }
              },
              "lastModifiedDateTime": "2023-11-18T10:10:10Z",
              "name": "OpenAPI_spec.pdf",
              "parentReference": {
                "driveId": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
                "id": "01LDCVMA6EMNPM3RRBTVFLSNVCPEJCKWQL",
                "sharepointIds": {
                  "listId": "abc52111-d6ab-ab12-cd34-de85ab63ab41",
                  "listItemId": "5",
                  "listItemUniqueId": "5a85c2cd-4b8c-487b-8d01-5368795edf50"
                },
                "siteId": "contoso.sharepoint.com,f21ef38f-4de7-7da9-0301-9c4cfe485e53,574a2bbe-e791-75cc-1234-5a0b4cbd3def"
              },
              "webUrl": "https://contoso.sharepoint.com/sites/knowledgebase/Shared Documents/OpenAPI_spec.pdf"
            }
          }
        ],
        "total": 1,
        "moreResultsAvailable": false
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  hitsContainers: [{"hits":[{"hitId":"012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC","rank":1,"summary":"<ddd/><c0>OpenAPI</c0> Specification v3.1.0 | Introduction, Definitions, & More https://spec.openapis.org<ddd/><c0>OpenAPI</c0> Specification v3.1.0 Version 3.1.0 Published 15 February 2021 Latest editor's <ddd/>","resource":{"@odata.type":"#microsoft.graph.driveItem","size":2980854,"fileSystemInfo":{"createdDateTime":"2023-11-18T20:26:55Z","lastModifiedDateTime":"2023-11-18T10:10:10Z"},"listItem":{"@odata.type":"#microsoft.graph.listItem","fields":{},"id":"5a85c2cd-4b8c-487b-8d01-5368795edf50"},"id":"012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC","createdBy":{"user":{"displayName":"John Doe","email":"john.doe@contoso.onmicrosoft.com"}},"createdDateTime":"2023-11-18T20:26:55Z","lastModifiedBy":{"user":{"displayName":"John Doe","email":"john.doe@contoso.onmicrosoft.com"}},"lastModifiedDateTime":"2023-11-18T10:10:10Z","name":"OpenAPI_spec.pdf","parentReference":{"driveId":"b!EXAMPLE_SECRET_VALUE_PLACEHOLDER","id":"01LDCVMA6EMNPM3RRBTVFLSNVCPEJCKWQL","sharepointIds":{"listId":"abc52111-d6ab-ab12-cd34-de85ab63ab41","listItemId":"5","listItemUniqueId":"5a85c2cd-4b8c-487b-8d01-5368795edf50"},"siteId":"contoso.sharepoint.com,f21ef38f-4de7-7da9-0301-9c4cfe485e53,574a2bbe-e791-75cc-1234-5a0b4cbd3def"},"webUrl":"https://contoso.sharepoint.com/sites/knowledgebase/Shared Documents/OpenAPI_spec.pdf"}}],"total":1,"moreResultsAvailable":false}]
  searchTerms   : ["openapi"]
  ```

  </TabItem>
</Tabs>

### With `resultsOnly` response

When we make use of the option `resultsOnly` the response will differ.

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "hitId": "012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC",
      "rank": 1,
      "summary": "<ddd/><c0>OpenAPI</c0> Specification v3.1.0 | Introduction, Definitions, & More https://spec.openapis.org<ddd/><c0>OpenAPI</c0> Specification v3.1.0 Version 3.1.0 Published 15 February 2021 Latest editor's <ddd/>",
      "resource": {
        "@odata.type": "#microsoft.graph.driveItem",
        "size": 2980854,
        "fileSystemInfo": {
          "createdDateTime": "2023-11-18T20:26:55Z",
          "lastModifiedDateTime": "2023-11-18T10:10:10Z"
        },
        "listItem": {
          "@odata.type": "#microsoft.graph.listItem",
          "fields": {},
          "id": "5a85c2cd-4b8c-487b-8d01-5368795edf50"
        },
        "id": "012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC",
        "createdBy": {
          "user": {
            "displayName": "John Doe",
            "email": "john.doe@contoso.onmicrosoft.com"
          }
        },
        "createdDateTime": "2023-11-18T20:26:55Z",
        "lastModifiedBy": {
          "user": {
            "displayName": "John Doe",
            "email": "john.doe@contoso.onmicrosoft.com"
          }
        },
        "lastModifiedDateTime": "2023-11-18T10:10:10Z",
        "name": "OpenAPI_spec.pdf",
        "parentReference": {
          "driveId": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "id": "01LDCVMA6EMNPM3RRBTVFLSNVCPEJCKWQL",
          "sharepointIds": {
            "listId": "abc52111-d6ab-ab12-cd34-de85ab63ab41",
            "listItemId": "5",
            "listItemUniqueId": "5a85c2cd-4b8c-487b-8d01-5368795edf50"
          },
          "siteId": "contoso.sharepoint.com,f21ef38f-4de7-7da9-0301-9c4cfe485e53,574a2bbe-e791-75cc-1234-5a0b4cbd3def"
        },
        "webUrl": "https://contoso.sharepoint.com/sites/knowledgebase/Shared Documents/OpenAPI_spec.pdf"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  hitId   : 012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC
  rank    : 1
  resource: {"@odata.type":"#microsoft.graph.driveItem","size":2980854,"fileSystemInfo":{"createdDateTime":"2023-11-18T20:26:55Z","lastModifiedDateTime":"2023-11-18T10:10:10Z"},"listItem":{"@odata.type":"#microsoft.graph.listItem","fields":{},"id":"5a85c2cd-4b8c-487b-8d01-5368795edf50"},"id":"012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC","createdBy":{"user":{"displayName":"John Doe","email":"john.doe@contoso.onmicrosoft.com"}},"createdDateTime":"2023-11-18T20:26:55Z","lastModifiedBy":{"user":{"displayName":"John Doe","email":"john.doe@contoso.onmicrosoft.com"}},"lastModifiedDateTime":"2023-11-18T10:10:10Z","name":"OpenAPI_spec.pdf","parentReference":{"driveId":"b!EXAMPLE_SECRET_VALUE_PLACEHOLDER","id":"01LDCVMA6EMNPM3RRBTVFLSNVCPEJCKWQL","sharepointIds":{"listId":"abc52111-d6ab-ab12-cd34-de85ab63ab41","listItemId":"5","listItemUniqueId":"5a85c2cd-4b8c-487b-8d01-5368795edf50"},"siteId":"contoso.sharepoint.com,f21ef38f-4de7-7da9-0301-9c4cfe485e53,574a2bbe-e791-75cc-1234-5a0b4cbd3def"},"webUrl":"https://contoso.sharepoint.com/sites/knowledgebase/Shared Documents/OpenAPI_spec.pdf"}
  summary : <ddd/><c0>OpenAPI</c0> Specification v3.1.0 | Introduction, Definitions, & More https://spec.openapis.org<ddd/><c0>OpenAPI</c0> Specification v3.1.0 Version 3.1.0 Published 15 February 2021 Latest editor's <ddd/>
  ```

  </TabItem>
  <TabItem value="CSV">

  ```md
  hitId,rank,summary
  012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC,1,"<ddd/><c0>OpenAPI</c0> Specification v3.1.0 | Introduction, Definitions, & More https://spec.openapis.org<ddd/><c0>OpenAPI</c0> Specification v3.1.0 Version 3.1.0 Published 15 February 2021 Latest editor's <ddd/>"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # search --scopes "driveItem" --queryString "OpenAPI" --resultsOnly "true"

  Date: 3/3/2024

  Property | Value
  ---------|-------
  hitId | 012Q4A6LPNNYLDCVMEI2KCVAKTNBV5XVDC
  rank | 1
  summary | <ddd/><c0>OpenAPI</c0> Specification v3.1.0 \| Introduction, Definitions, & More https://spec.openapis.org<ddd/><c0>OpenAPI</c0> Specification v3.1.0 Version 3.1.0 Published 15 February 2021 Latest editor's <ddd/>
  ```

  </TabItem>
</Tabs>

## More information

- Use the Microsoft Search API to query data: https://learn.microsoft.com/graph/api/resources/search-api-overview
