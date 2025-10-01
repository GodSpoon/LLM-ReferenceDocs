-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook mail searchfolder add

Creates a new mail search folder in the user's mailbox

## Usage

```sh
m365 outlook mail searchfolder add [options]
```

## Options

```md definition-list
`-i, --userId [userId]`
: The id of the user in whose mailbox the search folder should be created. Specify either `userId` or `userName`, but not both.

`-n, --userName [userName]`
: The UPN of the user in whose mailbox the search folder should be created. Specify either `userId` or `userName`, but not both.

`--folderName <folderName>`
: The name of the mail search folder.

`--sourceFolderIds <sourceFolderIds>`
: Comma-separated list of mail folders that should be searched.

`--includeNestedFolders`
: The nested mail folders will be searched if specified.

`--messageFilter <messageFilter>`
: The OData query to filter the messages.
```

<Global />

## Permissions

<Tabs>
  <TabItem value="Delegated">

  | Resource        | Permissions    |
  |-----------------|----------------|
  | Microsoft Graph | Mail.ReadWrite |

  </TabItem>
  <TabItem value="Application">

  | Resource        | Permissions    |
  |-----------------|----------------|
  | Microsoft Graph | Mail.ReadWrite |

  </TabItem>
</Tabs>

## Examples

Create a mail search folder in the user's mailbox specified by id for messages from the inbox that contain specific subject

```sh
m365 outlook mail searchfolder add --userId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --folderName 'CLI m365' --sourceFolderIds 'AQMkADYAAAIBDAAAAA==' --messageFilter "contains(subject, 'CLI for Microsoft 365')"
```

Create a mail search folder in the user's mailbox specified by UPN for incoming and outgoing messages from a specific year that contain specific text in a message body, search for messages inside all subfolders

```sh
m365 outlook mail searchfolder add --userName john.doe@contoso.com --folderName 'Power Platform Community' --sourceFolderIds 'AQMkADYAAAIBDAAAAA==,AQMkADYAAAIBDBBBBB==' --includeNestedFolders --messageFilter "contains(body/content,'Power Platform') AND receivedDateTime ge 2024-01-01 AND receivedDateTime le 2024-12-31"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER==",
    "displayName": "Microsoft Entra",
    "parentFolderId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "childFolderCount": 0,
    "unreadItemCount": 27,
    "totalItemCount": 41,
    "sizeInBytes": null,
    "isHidden": false,
    "isSupported": true,
    "includeNestedFolders": false,
    "sourceFolderIds": [
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
    ],
    "filterQuery": "contains(subject,'Microsoft Entra ID')"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  childFolderCount    : 0
  displayName         : Microsoft Entra
  filterQuery         : contains(subject,'Microsoft Entra ID')
  id                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  includeNestedFolders: false
  isHidden            : false
  isSupported         : true
  parentFolderId      : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  sizeInBytes         : null
  sourceFolderIds     : ["EXAMPLE_SECRET_VALUE_PLACEHOLDER"]
  totalItemCount      : 41
  unreadItemCount     : 27
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,parentFolderId,childFolderCount,unreadItemCount,totalItemCount,sizeInBytes,isHidden,isSupported,includeNestedFolders,filterQuery
  EXAMPLE_SECRET_VALUE_PLACEHOLDER==,Microsoft Entra,EXAMPLE_SECRET_VALUE_PLACEHOLDER,0,27,41,,,1,,"contains(subject,'Microsoft Entra ID')"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook mail searchfolder add --debug "false" --verbose "false" --userName "john.doe@contoso.com" --folderName "Microsoft Entra4" --messageFilter "contains(subject,'Microsoft Entra ID')" --sourceFoldersIds "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/6/2024

  ## Microsoft Entra (EXAMPLE_SECRET_VALUE_PLACEHOLDER==)

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER==
  displayName | Microsoft Entra
  parentFolderId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  childFolderCount | 0
  unreadItemCount | 27
  totalItemCount | 41
  isHidden | false
  isSupported | true
  includeNestedFolders | false
  filterQuery | contains(subject,'Microsoft Entra ID')
  ```

  </TabItem>
</Tabs>
