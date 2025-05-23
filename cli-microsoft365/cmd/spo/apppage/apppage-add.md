-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo apppage add

Creates a single-part app page

## Usage

```sh
m365 spo apppage add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the page should be created.

`-t, --title <title>`
: The title of the page to be created.

`-d, --webPartData <webPartData>`
: JSON string of the web part to put on the page.

`--addToQuickLaunch`
: Set, to add the page to the quick launch.
```

<Global />

## Remarks

If you want to add the single-part app page to quick launch, use the addToQuickLaunch flag.

## Examples

Create a single-part app page in the specified site, webpart data is stored in the `$webPartData` variable

```sh
m365 spo apppage add --title "Contoso" --webUrl "https://contoso.sharepoint.com" --webPartData $webPartData --addToQuickLaunch
```


## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "value": "SitePages/Contoso.aspx"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  value: SitePages/Contoso.aspx
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  value
  SitePages/Contoso.aspx
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo apppage add --title "Contoso" --webUrl "https://contoso.sharepoint.com/sites/sales" --webPartData "{"id": "62ca
  c389-787f-495d-beca-e11786162ef4", "instanceId": "9c6edb6e-199a-4a30-a3b6-73466a68187b", "title": "Full App Page Countdo
  wn Timer", "description": "This web part is used to allow a site admin to count down/up to an important event.", "dataVe
  rsion": "1.0", "properties": { "showButton": false, "countDate": "Mon May 13 2019 14:00:00 GMT+0100", "title": "My count
  down", "description": "", "countDirection": "COUNT_DOWN", "dateDisplay": "DAY_HOUR_MINUTE_SECOND", "buttonText": ""}}"

  Date: 10/2/2023

  Property | Value
  ---------|-------
  value | SitePages/Contoso.aspx
  ```

  </TabItem>
</Tabs>
