-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo group list

Lists all the groups within specific web

## Usage

```sh
m365 spo group list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Url of the web to list the group within.

`--associatedGroupsOnly`
: Get only the associated visitor, member and owner groups of the site.
```

<Global />

## Examples

Lists all the groups within a specific web.

```sh
m365 spo group list --webUrl "https://contoso.sharepoint.com/sites/contoso"
```

Lists the associated groups within a specific web.

```sh
m365 spo group list --webUrl "https://contoso.sharepoint.com/sites/contoso" --associatedGroupsOnly
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id  Title             LoginName         IsHiddenInUI  PrincipalType
  --  ----------------  ----------------  ------------  -------------                                                                                                                       14  Limited Access System Group                                                                              Limited Access System Group                                                                              false         8
  40  Project leaders   Project leaders   false         8                                                                                                                                   19  EXAMPLE_SECRET_VALUE_PLACEHOLDER  EXAMPLE_SECRET_VALUE_PLACEHOLDER  false         8                                                                                                                                   32  EXAMPLE_SECRET_VALUE_PLACEHOLDER  EXAMPLE_SECRET_VALUE_PLACEHOLDER  false         8                                                                                                                                   34  EXAMPLE_SECRET_VALUE_PLACEHOLDER     EXAMPLE_SECRET_VALUE_PLACEHOLDER     false         8                                                                                                                                   33  EXAMPLE_SECRET_VALUE_PLACEHOLDER  EXAMPLE_SECRET_VALUE_PLACEHOLDER  false         8                                                                                                                                   18  EXAMPLE_SECRET_VALUE_PLACEHOLDER  EXAMPLE_SECRET_VALUE_PLACEHOLDER  false         8                                                                                                                                   13  EXAMPLE_SECRET_VALUE_PLACEHOLDER  EXAMPLE_SECRET_VALUE_PLACEHOLDER  false         8
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
  # spo group list --webUrl "https://contoso.sharepoint.com/sites/contoso"

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
