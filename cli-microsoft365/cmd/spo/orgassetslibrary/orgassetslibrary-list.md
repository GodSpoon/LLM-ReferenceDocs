-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo orgassetslibrary list

List all libraries that are assigned as asset library

## Usage

```sh
m365 spo orgassetslibrary list [options]
```

## Options

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

List all libraries that are assigned as asset library

```sh
m365 spo orgassetslibrary list
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Url": "/",
    "Libraries": [
      {
        "DisplayName": "Site Assets",
        "LibraryUrl": "SiteAssets",
        "ListId": "/Guid(0a327c3f-ba82-4b19-bfa1-628405539420)/",
        "ThumbnailUrl": null
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Libraries: [{"DisplayName":"Site Assets","LibraryUrl":"SiteAssets","ListId":"/Guid(0a327c3f-ba82-4b19-bfa1-628405539420)/","ThumbnailUrl":null}]
  Url      : /
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Url,Libraries
  /,"[{""DisplayName"":""Site Assets"",""LibraryUrl"":""SiteAssets"",""ListId"":""/Guid(0a327c3f-ba82-4b19-bfa1-628405539420)/"",""ThumbnailUrl"":null}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo orgassetslibrary list 

  Date: 5/1/2023

  ## /

  Property | Value
  ---------|-------
  Url | /
  ```

  </TabItem>
</Tabs>

### Response when no library is assigned as asset library

<Tabs>
  <TabItem value="Text">

  ```text
  No libraries in Organization Assets
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  No libraries in Organization Assets
  ```

  </TabItem>
</Tabs>
