-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo file move

Moves a file to another location

## Usage

```sh
m365 spo file move [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the file is located.

`-s, --sourceUrl [sourceUrl]`
: The server-, site-relative or absolute decoded URL of the file to move. Specify either `sourceUrl` or `sourceId` but not both.

`-i, --sourceId [sourceId]`
: The ID of the file to move. Specify either `sourceUrl` or `sourceId` but not both.

`-t, --targetUrl <targetUrl>`
: Server-relative or absolute decoded URL where to move the file.

`--newName [newName]`
: The new name of the destination file.

`--nameConflictBehavior [nameConflictBehavior]`
: Behavior when a file or folder with the same name is already present at the destination. Allowed values: `fail`, `replace`, `rename`. Defaults to `fail`.

`--includeItemPermissions`
: (deprecated. Use option `withItemPermissions` instead) Ensure that item-level permissions are preserved during the move.

`--withItemPermissions`
: Ensure that item-level permissions are preserved during the move.

`--bypassSharedLock`
: This indicates whether a file with a share lock can still be moved. Use this option to move a file that is locked.

`--skipWait`
: Don't wait for the move operation to complete.
```

<Global />

## Remarks

When you specify a value for `nameConflictBehavior`, consider the following:
- `fail` will throw an error when the destination file already exists.
- `replace` will replace the destination file if it already exists.
- `rename` will add a suffix (e.g. Document1.pdf) when the destination file already exists.

## Examples

Move a file to a document library in another site collection by server relative URL.

```sh
m365 spo file move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/sites/project-x/Shared Documents/sp1.pdf" --targetUrl "/sites/project-y/Archived documents"
```

Move a file specified by a server-relative URL to a document library and rename it.

```sh
m365 spo file move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/Shared Documents/sp1.pdf" --targetUrl "/sites/project-x/My Documents" --newName Report.pdf
```

Move a file to another document library and replace a file with the same name.

```sh
m365 spo file move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl "/Shared Documents/Report project-x.pdf" --targetUrl "/sites/project-x/My Documents" --newName Report.pdf --nameConflictBehavior replace
```

Move a file referenced by its ID to another document library and retain item-level permissions.

```sh
m365 spo file move --webUrl https://contoso.sharepoint.com/sites/project-x --sourceId b8cc341b-9c11-4f2d-aa2b-0ce9c18bcba2 --targetUrl "/sites/project-x/My Documents" --withItemPermissions
```

## Response

### Standard Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "CheckInComment": "",
    "CheckOutType": 2,
    "ContentTag": "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1",
    "CustomizedPageStatus": 0,
    "ETag": "\"{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1\"",
    "Exists": true,
    "IrmEnabled": false,
    "Length": "5987",
    "Level": 1,
    "LinkingUri": null,
    "LinkingUrl": "",
    "MajorVersion": 1,
    "MinorVersion": 0,
    "Name": "Test1.docx",
    "ServerRelativeUrl": "/sites/project-x/documents/Test1.docx",
    "TimeCreated": "2022-10-30T10:16:18Z",
    "TimeLastModified": "2022-10-30T10:16:18Z",
    "Title": null,
    "UIVersion": 512,
    "UIVersionLabel": "1.0",
    "UniqueId": "b2307a39-e878-458b-bc90-03bc578531d6"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  CheckInComment      :
  CheckOutType        : 2
  ContentTag          : {03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1
  CustomizedPageStatus: 0
  ETag                : "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1"
  Exists              : true
  IrmEnabled          : false
  Length              : 5987
  Level               : 1
  LinkingUri          : null
  LinkingUrl          :
  MajorVersion        : 1
  MinorVersion        : 0
  Name                : Test1.docx
  ServerRelativeUrl   : /sites/project-x/documents/Test1.docx
  TimeCreated         : 2022-10-30T10:16:18Z
  TimeLastModified    : 2022-10-30T10:16:18Z
  Title               : null
  UIVersion           : 512
  UIVersionLabel      : 1.0
  UniqueId            : b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CheckInComment,CheckOutType,ContentTag,CustomizedPageStatus,ETag,Exists,IrmEnabled,Length,Level,LinkingUri,LinkingUrl,MajorVersion,MinorVersion,Name,ServerRelativeUrl,TimeCreated,TimeLastModified,Title,UIVersion,UIVersionLabel,UniqueId
  ,2,"{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1",0,"""{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1""",1,,5987,1,,,1,0,Test1.docx,/sites/project-x/documents/Test1.docx,2022-10-30T10:16:18Z,2022-10-30T10:16:18Z,,512,1.0,b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo file move --webUrl "https://contoso.sharepoint.com/sites/IT" --sourceUrl "/Shared Documents/Document.docx" --targetUrl "/sites/project-x/Shared Documents"

  Date: 10/3/2023

  ## b2307a39-e878-458b-bc90-03bc578531d6

  Property | Value
  ---------|-------
  CheckInComment |
  CheckOutType | 2
  ContentTag | {03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1,1
  CustomizedPageStatus | 0
  ETag | "{03E171B6-9DF2-46D9-A7A1-D5FA0BD23E4B},1"
  Exists | true
  ExistsAllowThrowForPolicyFailures | true
  IrmEnabled | false
  Length | 5987
  Level | 1
  LinkingUri | https://contoso.sharepoint.com/sites/project-x/shared%20documents/Document.docx?d=w59d4e6fcf6f94ce78bea0273cedb1a19
  LinkingUrl | https://contoso.sharepoint.com/sites/project-x/shared documents/Document.docx?d=w59d4e6fcf6f94ce78bea0273cedb1a19
  MajorVersion | 1
  MinorVersion | 0
  Name | Document.docx
  ServerRelativeUrl | /sites/project-x/shared documents/Document.docx
  TimeCreated | 2023-05-23T09:51:34Z
  TimeLastModified | 2023-05-23T10:13:01Z
  Title |
  UIVersion | 1536
  UIVersionLabel | 1.0
  UniqueId | b2307a39-e878-458b-bc90-03bc578531d6
  ```

  </TabItem>
</Tabs>

### `skipWait` response

The command won't return a response on success.
