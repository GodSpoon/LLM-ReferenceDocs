-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo folder get

Gets information about the specified folder

## Usage

```sh
m365 spo folder get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--url [url]`
: The server- or site-relative decoded URL of the folder to retrieve. Specify either `folderUrl` or `id` but not both.

`-i, --id [id]`
: The UniqueId (GUID) of the folder to retrieve. Specify either `url` or `id` but not both.

`--withPermissions`
: Set if you want to return associated roles and permissions of the folder. 
```

<Global />

## Remarks

If no folder exists at the specified URL, you will get a `Please check the folder URL. Folder might not exist on the specified URL` error.

If root level folder is passed, you will get a `Please ensure the specified folder URL or folder Id does not refer to a root folder. Use \'spo list get\' with withPermissions instead' error.` Please use the command 'spo list get'.

## Examples

Get folder properties for a folder with a specific site-relative URL.

```sh
m365 spo folder get --webUrl https://contoso.sharepoint.com/sites/project-x --url "/Shared Documents"
```

Get folder properties for a folder with a specific id (UniqueId).

```sh
m365 spo folder get --webUrl https://contoso.sharepoint.com/sites/project-x --id "b2307a39-e878-458b-bc90-03bc578531d6"
```

Get folder properties with permissions for a folder with server-relative URL.

```sh
m365 spo folder get --webUrl https://contoso.sharepoint.com/sites/test --url "/sites/test/Shared Documents/Test1" --withPermissions
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Exists": true,
    "ExistsAllowThrowForPolicyFailures": true,
    "IsWOPIEnabled": false,
    "ItemCount": 0,
    "Name": "Test",
    "ProgID": null,
    "ServerRelativeUrl": "/sites/test/Shared Documents/Test",
    "TimeCreated": "2020-10-29T17:28:43Z",
    "TimeLastModified": "2023-10-02T19:25:28Z",
    "UniqueId": "ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e",
    "WelcomePage": ""
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Exists                           : true
  ExistsAllowThrowForPolicyFailures: true
  IsWOPIEnabled                    : false
  ItemCount                        : 0
  Name                             : Test
  ProgID                           : null
  ServerRelativeUrl                : /sites/test/Shared Documents/Test
  TimeCreated                      : 2020-10-29T17:28:43Z
  TimeLastModified                 : 2023-10-02T19:25:28Z
  UniqueId                         : ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e
  WelcomePage                      :
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Exists,ExistsAllowThrowForPolicyFailures,IsWOPIEnabled,ItemCount,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,UniqueId,WelcomePage
  1,1,,0,Test,/sites/test/Shared Documents/Test,2020-10-29T17:28:43Z,2023-10-02T19:25:28Z,ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder get --webUrl "https://contoso.sharepoint.com/sites/test" --url "/sites/test/Shared Documents/Test"

  Date: 10/3/2023

  ## Test (ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e)

  Property | Value
  ---------|-------
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IsWOPIEnabled | false
  ItemCount | 0
  Name | Test
  ServerRelativeUrl | /sites/test/Shared Documents/Test
  TimeCreated | 2020-10-29T17:28:43Z
  TimeLastModified | 2023-10-02T19:25:28Z
  UniqueId | ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e
  WelcomePage |
  ```

  </TabItem>
</Tabs>

### `withPermissions` response

When we make use of the option `withPermissions` the response will differ.

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ListItemAllFields": {
      "RoleAssignments": [
        {
          "Member": {
            "Id": 4,
            "IsHiddenInUI": false,
            "LoginName": "SPDemo Owners",
            "Title": "SPDemo Owners",
            "PrincipalType": 8,
            "AllowMembersEditMembership": false,
            "AllowRequestToJoinLeave": false,
            "AutoAcceptRequestToJoinLeave": false,
            "Description": null,
            "OnlyAllowMembersViewMembership": false,
            "OwnerTitle": "SPDemo Owners",
            "RequestToJoinLeaveEmailSetting": "",
            "PrincipalTypeString": "SharePointGroup"
          },
          "RoleDefinitionBindings": [
            {
              "BasePermissions": {
                "High": "2147483647",
                "Low": "4294967295"
              },
              "Description": "Has full control.",
              "Hidden": false,
              "Id": 1073741829,
              "Name": "Full Control",
              "Order": 1,
              "RoleTypeKind": 5,
              "BasePermissionsValue": [
                "ViewListItems",
                "AddListItems",
                "EditListItems",
                "DeleteListItems",
                "ApproveItems",
                "OpenItems",
                "ViewVersions",
                "DeleteVersions",
                "CancelCheckout",
                "ManagePersonalViews",
                "ManageLists",
                "ViewFormPages",
                "AnonymousSearchAccessList",
                "Open",
                "ViewPages",
                "AddAndCustomizePages",
                "ApplyThemeAndBorder",
                "ApplyStyleSheets",
                "ViewUsageData",
                "CreateSSCSite",
                "ManageSubwebs",
                "CreateGroups",
                "ManagePermissions",
                "BrowseDirectories",
                "BrowseUserInfo",
                "AddDelPrivateWebParts",
                "UpdatePersonalWebParts",
                "ManageWeb",
                "AnonymousSearchAccessWebLists",
                "UseClientIntegration",
                "UseRemoteAPIs",
                "ManageAlerts",
                "CreateAlerts",
                "EditMyUserInfo",
                "EnumeratePermissions"
              ],
              "RoleTypeKindValue": "Administrator"
            }
          ],
          "PrincipalId": 4
        }
      ],
      "HasUniqueRoleAssignments": false,
      "FileSystemObjectType": 1,
      "Id": 7,
      "ServerRedirectedEmbedUri": null,
      "ServerRedirectedEmbedUrl": "",
      "ContentTypeId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "ComplianceAssetId": null,
      "Title": null,
      "MediaServiceOCR": null,
      "MediaServiceKeyPoints": null,
      "HideFromDelve": null,
      "MediaServiceImageTags": [],
      "SharedWithUsersId": null,
      "SharedWithDetails": null,
      "OData__ColorTag": null,
      "OData__Version": null,
      "ID": 7,
      "Created": "2020-10-29T10:28:43",
      "AuthorId": 7,
      "Modified": "2020-10-29T10:28:43",
      "EditorId": 7,
      "OData__CopySource": null,
      "CheckoutUserId": null,
      "OData__UIVersionString": "1.0",
      "GUID": "d66963e6-7b83-45e6-aa97-ce8d92857b28"
    },
    "Exists": true,
    "ExistsAllowThrowForPolicyFailures": true,
    "IsWOPIEnabled": false,
    "ItemCount": 0,
    "Name": "Test",
    "ProgID": null,
    "ServerRelativeUrl": "/sites/test/Shared Documents/Test",
    "TimeCreated": "2020-10-29T17:28:43Z",
    "TimeLastModified": "2023-10-02T19:25:28Z",
    "UniqueId": "ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e",
    "WelcomePage": ""
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Exists                           : true
  ExistsAllowThrowForPolicyFailures: true
  IsWOPIEnabled                    : false
  ItemCount                        : 0
  ListItemAllFields                : {"RoleAssignments":[{"Member":{"Id":4,"IsHiddenInUI":false,"LoginName":"SPDemo Owners","Title":"SPDemo Owners","PrincipalType":8,"AllowMembersEditMembership":false,"AllowRequestToJoinLeave":false,"AutoAcceptRequestToJoinLeave":false,"Description":null,"OnlyAllowMembersViewMembership":false,"OwnerTitle":"SPDemo Owners","RequestToJoinLeaveEmailSetting":"","PrincipalTypeString":"SharePointGroup"},"RoleDefinitionBindings":[{"BasePermissions":{"High":"2147483647","Low":"4294967295"},"Description":"Has full control.","Hidden":false,"Id":1073741829,"Name":"Full Control","Order":1,"RoleTypeKind":5,"BasePermissionsValue":["ViewListItems","AddListItems","EditListItems","DeleteListItems","ApproveItems","OpenItems","ViewVersions","DeleteVersions","CancelCheckout","ManagePersonalViews","ManageLists","ViewFormPages","AnonymousSearchAccessList","Open","ViewPages","AddAndCustomizePages","ApplyThemeAndBorder","ApplyStyleSheets","ViewUsageData","CreateSSCSite","ManageSubwebs","CreateGroups","ManagePermissions","BrowseDirectories","BrowseUserInfo","AddDelPrivateWebParts","UpdatePersonalWebParts","ManageWeb","AnonymousSearchAccessWebLists","UseClientIntegration","UseRemoteAPIs","ManageAlerts","CreateAlerts","EditMyUserInfo","EnumeratePermissions"],"RoleTypeKindValue":"Administrator"}],"PrincipalId":4},"RoleDefinitionBindings":[{"BasePermissions":{"High":"48","Low":"134287360"},"Description":"Can view specific lists, document libraries, list items, folders, or documents when given permissions.","Hidden":true,"Id":1073741825,"Name":"Limited Access","Order":160,"RoleTypeKind":1,"BasePermissionsValue":["ViewFormPages","Open","BrowseUserInfo","UseClientIntegration","UseRemoteAPIs"],"RoleTypeKindValue":"Guest"}],"PrincipalId":30}],"HasUniqueRoleAssignments":false,"FileSystemObjectType":1,"Id":7,"ServerRedirectedEmbedUri":null,"ServerRedirectedEmbedUrl":"","ContentTypeId":"EXAMPLE_SECRET_VALUE_PLACEHOLDER","ComplianceAssetId":null,"Title":null,"MediaServiceOCR":null,"MediaServiceKeyPoints":null,"HideFromDelve":null,"MediaServiceImageTags":[],"SharedWithUsersId":null,"SharedWithDetails":null,"OData__ColorTag":null,"OData__Version":null,"ID":7,"Created":"2020-10-29T10:28:43","AuthorId":7,"Modified":"2020-10-29T10:28:43","EditorId":7,"OData__CopySource":null,"CheckoutUserId":null,"OData__UIVersionString":"1.0","GUID":"d66963e6-7b83-45e6-aa97-ce8d92857b28"}
  Name                             : Test
  ProgID                           : null
  ServerRelativeUrl                : /sites/test/Shared Documents/Test
  TimeCreated                      : 2020-10-29T17:28:43Z
  TimeLastModified                 : 2023-10-02T19:25:28Z
  UniqueId                         : ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e
  WelcomePage                      :
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Exists,ExistsAllowThrowForPolicyFailures,IsWOPIEnabled,ItemCount,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,UniqueId,WelcomePage
  1,1,,0,Test,/sites/test/Shared Documents/Test,2020-10-29T17:28:43Z,2023-10-02T19:25:28Z,ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo folder get --webUrl "https://contoso.sharepoint.com/sites/test" --url "/sites/test/Shared Documents/Test" --withPermissions "true"

  Date: 10/3/2023

  ## Test (ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e)

  Property | Value
  ---------|-------
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IsWOPIEnabled | false
  ItemCount | 0
  Name | Test
  ServerRelativeUrl | /sites/test/Shared Documents/Test
  TimeCreated | 2020-10-29T17:28:43Z
  TimeLastModified | 2023-10-02T19:25:28Z
  UniqueId | ab5efdaf-bc47-44ae-a29c-2cfff63ecc9e
  WelcomePage |
  ```

  </TabItem>
</Tabs>
