-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo page control get

Gets information about the specific control on a modern page

## Usage

```sh
m365 spo page control get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the control to retrieve information for.

`-n, --pageName <pageName>`
: Name of the page where the control is located.

`-u, --webUrl <webUrl>`
: URL of the site where the page to retrieve is located.
```

<Global />

## Remarks

If the specified `pageName` doesn't refer to an existing modern page, you will get a `File doesn't exists` error.

## Examples

Get information about the control with ID _3ede60d3-dc2c-438b-b5bf-cc40bb2351e1_ placed on a modern page with name _home.aspx_

```sh
m365 spo page control get --id 3ede60d3-dc2c-438b-b5bf-cc40bb2351e1 --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx
```


## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "7558d804-0334-49ca-b14a-53870cf6caae",
    "type": "Client-side web part",
    "title": "Bing Maps",
    "controlType": 3,
    "order": 1,
    "controlData": {
      "controlType": 3,
      "displayMode": 2,
      "id": "7558d804-0334-49ca-b14a-53870cf6caae",
      "position": {
        "controlIndex": 1,
        "sectionIndex": 1,
        "zoneIndex": 1,
        "sectionFactor": 12,
        "layoutIndex": 1
      },
      "webPartId": "e377ea37-9047-43b9-8cdb-a761be2f8e09",
      "emphasis": {},
      "webPartData": {
        "dataVersion": "1.0",
        "description": "Display a location on a map using Bing Maps.",
        "id": "e377ea37-9047-43b9-8cdb-a761be2f8e09",
        "instanceId": "7558d804-0334-49ca-b14a-53870cf6caae",
        "properties": {
          "pushPins": [],
          "maxNumberOfPushPins": 1,
          "shouldShowPushPinTitle": true,
          "zoomLevel": 12,
          "mapType": "road"
        },
        "title": "Bing Maps",
        "serverProcessedContent": {
          "htmlStrings": {},
          "searchablePlainTexts": {},
          "imageSources": {},
          "links": {}
        }
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  controlData: {"controlType":3,"displayMode":2,"id":"7558d804-0334-49ca-b14a-53870cf6caae","position":{"controlIndex":1,"sectionIndex":1,"zoneIndex":1,"sectionFactor":12,"layoutIndex":1},"webPartId":"e377ea37-9047-43b9-8cdb-a761be2f8e09","emphasis":{},"webPartData":{"dataVersion":"1.0","description":"Display a location on a map using Bing Maps.","id":"e377ea37-9047-43b9-8cdb-a761be2f8e09","instanceId":"7558d804-0334-49ca-b14a-53870cf6caae","properties":{"pushPins":[],"maxNumberOfPushPins":1,"shouldShowPushPinTitle":true,"zoomLevel":12,"mapType":"road"},"title":"Bing Maps","serverProcessedContent":{"htmlStrings":{},"searchablePlainTexts":{},"imageSources":{},"links":{}}}}
  controlType: 3
  id         : 7558d804-0334-49ca-b14a-53870cf6caae
  order      : 1
  title      : Bing Maps
  type       : Client-side web part
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,type,title,controlType,order,controlData
  7558d804-0334-49ca-b14a-53870cf6caae,Client-side web part,Bing Maps,3,1,"{""controlType"":3,""displayMode"":2,""id"":""7558d804-0334-49ca-b14a-53870cf6caae"",""position"":{""controlIndex"":1,""sectionIndex"":1,""zoneIndex"":1,""sectionFactor"":12,""layoutIndex"":1},""webPartId"":""e377ea37-9047-43b9-8cdb-a761be2f8e09"",""emphasis"":{},""webPartData"":{""dataVersion"":""1.0"",""description"":""Display a location on a map using Bing Maps."",""id"":""e377ea37-9047-43b9-8cdb-a761be2f8e09"",""instanceId"":""7558d804-0334-49ca-b14a-53870cf6caae"",""properties"":{""pushPins"":[],""maxNumberOfPushPins"":1,""shouldShowPushPinTitle"":true,""zoomLevel"":12,""mapType"":""road""},""title"":""Bing Maps"",""serverProcessedContent"":{""htmlStrings"":{},""searchablePlainTexts"":{},""imageSources"":{},""links"":{}}}}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo page control get --id "f85f8dfa-9052-4be8-8954-8cdafe811b97" --webUrl "https://contoso.sharepoint.com/sites/team-a" --pageName "home.aspx"

  Date: 5/1/2023

  ## Bing Maps (f85f8dfa-9052-4be8-8954-8cdafe811b97)

  Property | Value
  ---------|-------
  id | f85f8dfa-9052-4be8-8954-8cdafe811b97
  type | Client-side web part
  title | Bing Maps
  controlType | 3
  order | 1
  ```

  </TabItem>
</Tabs>
