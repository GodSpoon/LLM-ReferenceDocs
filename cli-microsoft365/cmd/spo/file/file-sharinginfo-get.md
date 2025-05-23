-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file sharinginfo get

Generates a sharing information report for the specified file

## Usage

```sh
m365 spo file sharinginfo get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`--fileUrl [fileUrl]`
: The server- or site-relative decoded URL of the file for which to build the report. Specify either `fileUrl` or `fileId` but not both.

`-i, --fileId [fileId]`
: The UniqueId (GUID) of the file for which to build the report. Specify either `fileUrl` or `fileId` but not both.
```

<Global />

## Examples

Get file sharing information report for the file with the specified server-relative url located in the specified site.

```sh
m365 spo file sharinginfo get --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl "/sites/M365CLI/Shared Documents/SharedFile.docx"
```

Get file sharing information report for file with the specified id (UniqueId) located in the specified site.

```sh
m365 spo file sharinginfo get --webUrl https://contoso.sharepoint.com/sites/project-x --fileId "b2307a39-e878-458b-bc90-03bc578531d6"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "permissionsInformation": {
      "hasInheritedLinks": false,
      "links": [
        {
          "isInherited": false,
          "linkDetails": {
            "AllowsAnonymousAccess": false,
            "ApplicationId": null,
            "BlocksDownload": false,
            "Created": "",
            "CreatedBy": null,
            "Description": null,
            "Embeddable": false,
            "Expiration": "",
            "HasExternalGuestInvitees": false,
            "Invitations": [],
            "IsActive": false,
            "IsAddressBarLink": false,
            "IsCreateOnlyLink": false,
            "IsDefault": true,
            "IsEditLink": false,
            "IsEphemeral": false,
            "IsFormsLink": false,
            "IsManageListLink": false,
            "IsReviewLink": false,
            "IsUnhealthy": false,
            "LastModified": "",
            "LastModifiedBy": null,
            "LimitUseToApplication": false,
            "LinkKind": 3,
            "MeetingId": null,
            "PasswordLastModified": "",
            "PasswordLastModifiedBy": null,
            "RedeemedUsers": [],
            "RequiresPassword": false,
            "RestrictedShareMembership": false,
            "RestrictToExistingRelationships": false,
            "Scope": -1,
            "ShareId": "00000000-0000-0000-0000-000000000000",
            "ShareTokenString": null,
            "SharingLinkStatus": 0,
            "TrackLinkUsers": false,
            "Url": null
          },
          "linkMembers": []
        }
      ],
      "principals": [
        {
          "principal": {
            "directoryObjectId": null,
            "email": "",
            "expiration": null,
            "id": 4,
            "isActive": true,
            "isExternal": false,
            "jobTitle": null,
            "loginName": "project-x Owners",
            "name": "project-x Owners",
            "principalType": 8,
            "userId": null,
            "userPrincipalName": null
          },
          "role": 3
        }
      ],
      "siteAdmins": [
        {
          "principal": {
            "directoryObjectId": null,
            "email": "admin@contoso.onmicrosoft.com",
            "expiration": "",
            "id": 7,
            "isActive": true,
            "isExternal": false,
            "jobTitle": "Architect",
            "loginName": "i:0#.f|membership|admin@contoso.onmicrosoft.com",
            "name": "Nanddeep Nachan",
            "principalType": 1,
            "userId": null,
            "userPrincipalName": "admin@contoso.onmicrosoft.com"
          },
          "role": 3
        }
      ]
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  SharedWith            IsActive  IsExternal  PrincipalType
  --------------------  --------  ----------  ---------------
  project-x Owners         true      false       SharePointGroup
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file sharinginfo get --webUrl "https://contoso.sharepoint.com/sites/project-x" --fileUrl "/Shared Documents/logo.jpg"

  Date: 10/3/2023

  Property | Value
  ---------|-------
  ```

  </TabItem>
</Tabs>
