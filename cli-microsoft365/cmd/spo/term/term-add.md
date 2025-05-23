-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo term add

Adds taxonomy term

## Usage

```sh
m365 spo term add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the term to add

`-u, --webUrl [webUrl]`
: If specified, allows you to add a term to the tenant term store as well as the sitecollection specific term store. Defaults to the tenant admin site.

`--termSetId [termSetId]`
: ID of the term set in which to create the term. Specify `termSetId` or `termSetName` but not both

`--termSetName [termSetName]`
: Name of the term set in which to create the term. Specify `termSetId` or `termSetName` but not both

`--termGroupId [termGroupId]`
: ID of the term group to which the term set belongs. Specify `termGroupId` or `termGroupName` but not both

`--termGroupName [termGroupName]`
: Name of the term group to which the term set belongs. Specify `termGroupId` or `termGroupName` but not both

`-i, --id [id]`
: ID of the term to add

`-d, --description [description]`
: Description of the term to add

`--parentTermId [parentTermId]`
: ID of the term below which the term should be added

`--customProperties [customProperties]`
: JSON string with key-value pairs representing custom properties to set on the term

`--localCustomProperties [localCustomProperties]`
: JSON string with key-value pairs representing local custom properties to set on the term
```

<Global />

## Remarks

:::warning[Escaping JSON in PowerShell]

When using the `--customProperties` and/or `--localCustomProperties` options it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::
 
:::info

To use this command without the `--webUrl` option you have to have permissions to access the tenant admin site.

:::

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Administrator role. It allows you to add a term to a term set in the tenant term store if you are listed as a term store administrator. It allows you to add terms to a term set in the sitecollection term store if you are a site owner.

## Examples

Add taxonomy term with the specified name to the term group and term set specified by their names.

```sh
m365 spo term add --name IT --termSetName Department --termGroupName People
```

Add taxonomy term with the specified name to the term group and term set specified by their IDs.

```sh
m365 spo term add --name IT --termSetId 8ed8c9ea-7052-4c1d-a4d7-b9c10bffea6f --termGroupId 5c928151-c140-4d48-aab9-54da901c7fef
```

Add taxonomy term with the specified name and ID.

```sh
m365 spo term add --name IT --id 5c928151-c140-4d48-aab9-54da901c7fef --termSetName Department --termGroupName People
```

Add taxonomy term to the specified sitecollection with the specified name and ID.

```sh
m365 spo term add --name IT --id 5c928151-c140-4d48-aab9-54da901c7fef --termSetName Department --termGroupName People --webUrl https://contoso.sharepoint.com/sites/project-x
```

Add taxonomy term with custom properties.

```sh
m365 spo term add --name IT --termSetName Department --termGroupName People --customProperties '{"Property": "Value"}'
```

Add taxonomy term below the specified term.

```sh
m365 spo term add --name IT --parentTermId 5c928151-c140-4d48-aab9-54da901c7fef --termGroupName People
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CreatedDate": "2023-05-10T06:21:33.873Z",
    "Id": "346f49b0-3d1c-4ed3-b590-df303294cc16",
    "LastModifiedDate": "2023-05-10T06:21:33.873Z",
    "Name": "IT",
    "CustomProperties": {},
    "CustomSortOrder": null,
    "IsAvailableForTagging": true,
    "Owner": "i:0#.f|membership|john.doe@contoso.onmicrosoft.com",
    "Description": "",
    "IsDeprecated": false,
    "IsKeyword": false,
    "IsPinned": false,
    "IsPinnedRoot": false,
    "IsReused": false,
    "IsRoot": true,
    "IsSourceTerm": true,
    "LocalCustomProperties": {},
    "MergedTermIds": [],
    "PathOfTerm": "IT",
    "TermsCount": 0
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  CreatedDate          : 2023-05-10T06:22:34.686Z
  CustomProperties     : {}
  CustomSortOrder      : null
  Description          :
  Id                   : 53156df9-5485-4724-9f4f-6670a3d41f88
  IsAvailableForTagging: true
  IsDeprecated         : false
  IsKeyword            : false
  IsPinned             : false
  IsPinnedRoot         : false
  IsReused             : false
  IsRoot               : true
  IsSourceTerm         : true
  LastModifiedDate     : 2023-05-10T06:22:34.686Z
  LocalCustomProperties: {}
  MergedTermIds        : []
  Name                 : IT
  Owner                : i:0#.f|membership|john.doe@contoso.onmicrosoft.com
  PathOfTerm           : IT
  TermsCount           : 0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CreatedDate,Id,LastModifiedDate,Name,IsAvailableForTagging,Owner,Description,IsDeprecated,IsKeyword,IsPinned,IsPinnedRoot,IsReused,IsRoot,IsSourceTerm,PathOfTerm,TermsCount
  2023-05-10T06:23:13.490Z,0f1e0630-9f45-42d1-a64e-e82fe76826da,2023-05-10T06:23:13.490Z,IT,1,i:0#.f|membership|john.doe@contoso.onmicrosoft.com,,,,,,,1,1,IT,0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo term add --termGroupName "People" --termSetName "Department" --name "IT"

  Date: 5/10/2023

  ## IT (6e72d493-000d-4517-aa3e-2afb3a3d4bc8)

  Property | Value
  ---------|-------
  CreatedDate | 2023-05-10T06:23:49.970Z
  Id | 6e72d493-000d-4517-aa3e-2afb3a3d4bc8
  LastModifiedDate | 2023-05-10T06:23:49.970Z
  Name | IT
  IsAvailableForTagging | true
  Owner | i:0#.f\|membership\|john.doe@contoso.onmicrosoft.com
  Description |
  IsDeprecated | false
  IsKeyword | false
  IsPinned | false
  IsPinnedRoot | false
  IsReused | false
  IsRoot | true
  IsSourceTerm | true
  PathOfTerm | IT
  TermsCount | 0
  ```

  </TabItem>
</Tabs>
