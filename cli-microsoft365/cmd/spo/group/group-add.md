-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo group add

Creates group in the specified site

## Usage

```sh
m365 spo group add [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site where the group should be added.

`-n, --name <name>`
: Name of the group to add.

`--description [description]`
: The description for the group.

`--allowMembersEditMembership [allowMembersEditMembership]`
: Who can edit the membership of the group? When `true` members can edit membership, otherwise only owners can do this. Default `false`.

`--onlyAllowMembersViewMembership [onlyAllowMembersViewMembership]`
: Who can view the membership of the group? When `false` everyone can view the group membership, otherwise only group members can. Default `true`.

`--allowRequestToJoinLeave [allowRequestToJoinLeave]`
: Specify whether to allow users to request membership in this group and allow users to request to leave the group. Default `false`.

`--autoAcceptRequestToJoinLeave [autoAcceptRequestToJoinLeave]`
: If auto-accept is enabled, users will automatically be added or removed when they make a request. Default `false`.

`--requestToJoinLeaveEmailSetting [requestToJoinLeaveEmailSetting]`
: All membership requests will be sent to the email address specified.
```

<Global />

## Examples

Create group with title and description

```sh
m365 spo group add --webUrl https://contoso.sharepoint.com/sites/project-x --name "Project leaders" --description "This group contains all project leaders"
```

Create group with membership requests

```sh
m365 spo group add --webUrl https://contoso.sharepoint.com/sites/project-x --name "Project leaders" --allowRequestToJoinLeave true --requestToJoinLeaveEmailSetting john.doe@contoso.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Id": 37,
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
  Id                            : 38
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
  39,,Project leaders,Project leaders,8,,,,This group contains all project leaders,1,Jon Doe
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo group add --webUrl "https://contoso.sharepoint.com/sites/project-x" --name "Project leaders" --description "This group contains all project leaders"

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
