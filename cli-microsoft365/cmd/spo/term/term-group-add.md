-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo term group add

Adds taxonomy term group

## Usage

```sh
m365 spo term group add [options]
```

## Options

```md definition-list
`-n, --name <name>`
: Name of the term group to add

`-i, --id [id]`
: ID of the term group to add

`-d, --description [description]`
: Description of the term group to add

`-u, --webUrl [webUrl]`
: If specified, allows you to add a term group to the tenant term store as a term store administrator without the SharePoint administrator role.
```

<Global />

## Remarks

:::warning

To use this command without the `--webUrl` option you must have permissions to access the tenant admin site.

When using the `--webUrl` option you can connect to the term store with limited permissions, and do not need the SharePoint Adminstrator role. It allows you to add a term group to the tenant term store if you are listed as a term store administrator.

This command does not create a sitecollection specific term store/group when using the `--webUrl` option.

:::

## Examples

Add a new taxonomy term group with the specified name

```sh
m365 spo term group add --name PnPTermSets
```

Add a new taxonomy term group with the specified name and id

```sh
m365 spo term group add --name PnPTermSets --id 0e8f395e-ff58-4d45-9ff7-e331ab728beb
```

Add a new taxonomy term group with the specified name and description with limited permissions

```sh
m365 spo term group add --name PnPTermSets --description 'Term sets for PnP' --webUrl 'https://contoso.sharepoint.com'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Name": "PnPTermSets",
    "Id": "cafe662c-c3fa-4c83-bcb0-50b701b37164",
    "Description": "Term sets for PnP"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Description: Term sets for PnP
  Id         : cafe662c-c3fa-4c83-bcb0-50b701b37164
  Name       : PnPTermSets
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Name,Id,Description
  PnPTermSets,cafe662c-c3fa-4c83-bcb0-50b701b37164,Term sets for PnP
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo term group add --name "PnPTermSets" --description 'Term sets for PnP'
  
  Date: 24/05/2023
  
  ## PnPTermSets (cafe662c-c3fa-4c83-bcb0-50b701b37164)
  
  | Property    | Value                                |
  | ----------- | ------------------------------------ |
  | Name        | PnPTermSets                          |
  | Id          | cafe662c-c3fa-4c83-bcb0-50b701b37164 |
  | Description | Term sets for PnP                    |
  ```

  </TabItem>
</Tabs>
