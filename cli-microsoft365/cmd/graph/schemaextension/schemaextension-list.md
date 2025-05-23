-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph schemaextension list

Get a list of schemaExtension objects created in the current tenant, that can be InDevelopment, Available, or Deprecated.

## Usage

```sh
m365 graph schemaextension list [options]
```

## Options

```md definition-list
`-s, --status [status]`
: The status to filter on. Available values are Available, InDevelopment, Deprecated

`--owner [owner]`
: The id of the owner to filter on

`-p, --pageSize [pageSize]`
: Number of objects to return

`-n, --pageNumber [pageNumber]`
: Page number to return if pageSize is specified (first page is indexed as value of 0)
```

<Global />

## Remarks

pageNumber is specified as a 0-based index. A value of 2 returns the third page of items. 

## Examples

Get a list of schemaExtension objects created in the current tenant, that can be InDevelopment, Available, or Deprecated.

```sh
m365 graph schemaextension list 
```

Get a list of schemaExtension objects created in the current tenant, with the specified owner.

```sh
m365 graph schemaextension list --owner 617720dc-85fc-45d7-a187-cee75eaf239e
```

Get a list of schemaExtension objects created in the current tenant, with the specified owner and return the third page of results of 10.

```sh
m365 graph schemaextension list --owner 617720dc-85fc-45d7-a187-cee75eaf239e --pageNumber 2 --pageSize 10
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "adatumisv_exo2",
      "description": "sample description",
      "targetTypes": [
        "Message"
      ],
      "status": "Available",
      "owner": "617720dc-85fc-45d7-a187-cee75eaf239e",
      "properties": [
        {
          "name": "p1",
          "type": "String"
        },
        {
          "name": "p2",
          "type": "String"
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id              description         targetTypes  status     owner                                 properties                                                                                                                  
  --------------  ------------------  -----------  ---------  ------------------------------------  --------------------------------------------------------------
  adatumisv_exo2  sample description  Message      Available  617720dc-85fc-45d7-a187-cee75eaf239e  [{"name":"p1","type":"String"},{"name":"p2","type":"String"}]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,description,status,owner,properties
  adatumisv_exo2,sample description,Available,617720dc-85fc-45d7-a187-cee75eaf239e,"[{""name"":""p1"",""type"":""String""},{""name"":""p2"",""type"":""String""}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph schemaextension list

  Date: 2023-05-22

  ## adatumisv_exo2

  Property | Value
  ---------|-------
  id | adatumisv\_exo2
  description | sample description
  status | Available
  owner | 617720dc-85fc-45d7-a187-cee75eaf239e
  ```

  </TabItem>
</Tabs>

## More information

[https://developer.microsoft.com/en-us/graph/docs/api-reference/v1.0/api/schemaextension_list](https://developer.microsoft.com/en-us/graph/docs/api-reference/v1.0/api/schemaextension_list)
