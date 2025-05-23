-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo term set add

Adds taxonomy term set

## Usage

```sh
m365 spo term set add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the term set to add.

`-u, --webUrl [webUrl]`
: If specified, allows you to add a term set to the tenant term store as well as the sitecollection specific term store. Defaults to the tenant admin site.

`--termGroupId [termGroupId]`
: ID of the term group in which to create the term set. Specify `termGroupId` or `termGroupName` but not both.

`--termGroupName [termGroupName]`
: Name of the term group in which to create the term set. Specify `termGroupId` or `termGroupName` but not both.

`-i, --id [id]`
: ID of the term set to add.

`-d, --description [description]`
: Description of the term set to add.

`--customProperties [customProperties]`
: JSON string with key-value pairs representing custom properties to set on the term set.
```

<Global />

## Remarks

:::warning[Escaping JSON in PowerShell]

When using the `--customProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

:::info

To use this command without the `--webUrl` option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. You need to be a site visitor or more. It allows you to add a term set to a term group in the tenant term store if you are listed as a term store administrator. It allows you to add a term set to a term group in the sitecollection term store if you are a site owner.

## Examples

Add taxonomy term set to the term group specified by ID.

```sh
m365 spo term set add --name PnP-Organizations --termGroupId 0e8f395e-ff58-4d45-9ff7-e331ab728beb
```

Add taxonomy term set to the specified sitecollection's term group specified by ID.

```sh
m365 spo term set add --name PnP-Organizations --termGroupId 0e8f395e-ff58-4d45-9ff7-e331ab728beb --webUrl https://contoso.sharepoint.com/sites/project-x
```

Add taxonomy term set to the term group specified by name. Create the term set with the specified ID.

```sh
m365 spo term set add --name PnP-Organizations --termGroupName PnPTermSets --id aa70ede6-83d1-466d-8d95-30d29e9bbd7c
```

Add taxonomy term set and set its description.

```sh
m365 spo term set add --name PnP-Organizations --termGroupId 0e8f395e-ff58-4d45-9ff7-e331ab728beb --description 'Contains a list of organizations'
```

Add taxonomy term set and set its custom properties.

```sh
m365 spo term set add --name PnP-Organizations --termGroupId 0e8f395e-ff58-4d45-9ff7-e331ab728beb --customProperties '{"Property":"Value"}'
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CreatedDate": "2023-05-14T10:28:31.041Z",
    "Id": "c28cfcd2-0705-4b7b-b8e6-ba2fb107e5ec",
    "LastModifiedDate": "2023-05-14T10:28:31.041Z",
    "Name": "PnP-Organizations",
    "CustomProperties": {},
    "CustomSortOrder": null,
    "IsAvailableForTagging": true,
    "Owner": "i:0#.f|membership|john.doe@contoso.com",
    "Contact": "",
    "Description": "",
    "IsOpenForTermCreation": false,
    "Names": {
      "1033": "PnP-Organizations"
    },
    "Stakeholders": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Contact              :
  CreatedDate          : 2023-05-14T10:30:41.018Z
  CustomProperties     : {}
  CustomSortOrder      : null
  Description          :
  Id                   : 41102744-9f7b-448b-a265-3bbe3db5c064
  IsAvailableForTagging: true
  IsOpenForTermCreation: false
  LastModifiedDate     : 2023-05-14T10:30:41.018Z
  Name                 : PnP-Organizations
  Names                : {"1033":"PnP-Organizations"}
  Owner                : i:0#.f|membership|john.doe@contoso.com
  Stakeholders         : []
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CreatedDate,Id,LastModifiedDate,Name,IsAvailableForTagging,Owner,Contact,Description,IsOpenForTermCreation
  2023-05-14T10:31:11.299Z,8f212d7d-eeb3-454b-811a-01b38fea56e1,2023-05-14T10:31:11.299Z,PnP-Organizations,1,i:0#.f|membership|john.doe@contoso.com,,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo term set add --name "PnP-Organizations" --termGroupId "0e8f395e-ff58-4d45-9ff7-e331ab728beb"

  Date: 5/14/2023

  ## PnP-Organizations (73824553-d254-44ef-ac0f-61926b65e925)

  Property | Value
  ---------|-------
  CreatedDate | 2023-05-14T10:31:42.422Z
  Id | 73824553-d254-44ef-ac0f-61926b65e925
  LastModifiedDate | 2023-05-14T10:31:42.422Z
  Name | PnP-Organizations
  IsAvailableForTagging | true
  Owner | i:0#.f\|membership\|john.doe@contoso.com
  Contact |
  Description |
  IsOpenForTermCreation | false
  ```

  </TabItem>
</Tabs>
