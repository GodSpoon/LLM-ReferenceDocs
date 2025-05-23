-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo propertybag list

Gets property bag values

## Usage

```sh
m365 spo propertybag list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site from which the property bag value should be retrieved.

`--folder [folder]`
: Site-relative URL of the folder from which to retrieve property bag value. Case-sensitive.
```

<Global />

## Examples

Return property bag values located in the given site

```sh
m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test
```

Return property bag values located in the given site root folder

```sh
m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder /
```

Return property bag values located in the given site document library

```sh
m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder '/Shared Documents'
```

Return property bag values located in folder in the given site document library

```sh
m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder '/Shared Documents/MyFolder'
```

Return property bag values located in the given site list

```sh
m365 spo propertybag list --webUrl https://contoso.sharepoint.com/sites/test --folder /Lists/MyList
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "key": "vti_approvallevels",
      "value": "Approved Rejected Pending\ Review"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  key                   value                                                                             
  --------------------  -----------------------------------
  vti_approvallevels     Approved Rejected Pending\ Review
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  key,value
  vti_approvallevels,Approved Rejected Pending\ Review
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo propertybag list --webUrl "https://contoso.sharepoint.com/sites/test"

  Date: 5/6/2023

  Property | Value
  ---------|-------
  key | vti_approvallevels
  value | Approved Rejected Pending\ Review
  ```

  </TabItem>
</Tabs>
