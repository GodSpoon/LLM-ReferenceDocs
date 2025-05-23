-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo propertybag get

Gets the value of the specified property from the property bag

## Usage

```sh
m365 spo propertybag get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site from which the property bag value should be retrieved.

`-k, --key <key>`
: Key of the property for which the value should be retrieved. Case-sensitive.

`--folder [folder]`
: Site-relative URL of the folder from which to retrieve property bag value. Case-sensitive.
```

<Global />

## Examples

Returns the value of the property from the property bag located in the given site

```sh
m365 spo propertybag get --webUrl https://contoso.sharepoint.com/sites/test --key key1
```

Returns the value of the property from the property bag located in root folder of the given site

```sh
m365 spo propertybag get --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder /
```

Returns the value of the property from the property bag located in document library of the given site

```sh
m365 spo propertybag get --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder '/Shared Documents'
```

Returns the value of the property from the property bag located in folder in a document library located in the given site

```sh
m365 spo propertybag get --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder '/Shared Documents/MyFolder'
```

Returns the value of the property from the property bag located in a list in the given site

```sh
m365 spo propertybag get --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder /Lists/MyList
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "Approved Rejected Pending\ Review"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Approved Rejected Pending\ Review
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Approved Rejected Pending\ Review
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Approved Rejected Pending\ Review
  ```

  </TabItem>
</Tabs>
