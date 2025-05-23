-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo group get

Gets site group

## Usage

```sh
m365 spo group get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the group is located.

`-i, --id [id]`
: ID of the site group to get. Use either `id`, `name` or `associatedGroup` but not multiple.

`--name [name]`
: Name of the site group to get. Use either `id`, `name` or `associatedGroup` but not multiple.

`--associatedGroup [associatedGroup]`
: Type of the associated group to get. Available values: `Owner`, `Member`, `Visitor`. Use either `id`, `name` or `associatedGroup` but not multiple.
```

<Global />

## Examples

Get group with ID for the specified web.

```sh
m365 spo group get --webUrl https://contoso.sharepoint.com/sites/project-x --id 7
```

Get group with name for the specified web.

```sh
m365 spo group get --webUrl https://contoso.sharepoint.com/sites/project-x --name "Team Site Members"
```

Get the associated owner group of a specified site.

```sh
m365 spo group get --webUrl https://contoso.sharepoint.com/sites/project-x --associatedGroup Owner
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Id": 40,
    "IsHiddenInUI": false,
    "LoginName": "Project leaders",
    "Title": "Project leaders",
    "PrincipalType": 8,
    "AllowMembersEditMembership": false,
    "AllowRequestToJoinLeave": false,
    "AutoAcceptRequestToJoinLeave": false,
    "Description": "This group contains all project leaders",
    "OnlyAllowMembersViewMembership": true,
    "OwnerTitle": "Jon Doe",
    "RequestToJoinLeaveEmailSetting": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AllowMembersEditMembership    : false
  AllowRequestToJoinLeave       : false
  AutoAcceptRequestToJoinLeave  : false
  Description                   : This group contains all project leaders
  Id                            : 40
  IsHiddenInUI                  : false
  LoginName                     : Project leaders
  OnlyAllowMembersViewMembership: true
  OwnerTitle                    : Jon Doe
  PrincipalType                 : 8
  RequestToJoinLeaveEmailSetting: null
  Title                         : Project leaders
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,IsHiddenInUI,LoginName,Title,PrincipalType,AllowMembersEditMembership,AllowRequestToJoinLeave,AutoAcceptRequestToJoinLeave,Description,OnlyAllowMembersViewMembership,OwnerTitle
  40,,Project leaders,Project leaders,8,,,,This group contains all project leaders,1,Jon Doe
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo group get --webUrl "https://contoso.sharepoint.com/sites/project-x" --name "Project leaders"

  Date: 10/3/2023

  ## Project leaders (40)

  Property | Value
  ---------|-------
  Id | 40
  IsHiddenInUI | false
  LoginName | Project leaders
  Title | Project leaders
  PrincipalType | 8
  AllowMembersEditMembership | false
  AllowRequestToJoinLeave | false
  AutoAcceptRequestToJoinLeave | false
  Description | This group contains all project leaders
  OnlyAllowMembersViewMembership | true
  OwnerTitle | Jon Doe
  ```

  </TabItem>
</Tabs>
