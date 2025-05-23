-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview threatassessment add

Create a threat assessment

## Usage

```sh
m365 purview threatassessment add [options]
```

## Options

```md definition-list
`-t, --type <type>`
: The type of threat assessment to retrieve. Supports `file` and `url`.

`-e, --expectedAssessment <expectedAssessment>`
: The expected assessment from submitter. Possible values are: `block` and `unblock`.

`-c, --category <category>`
: The threat category. Possible values are: `spam`, `phishing`, `malware`.

`-p, --path [path]`
: Local path to the file to upload. Can only be used for threat assessment with type `file`.

`-u, --url [url]`
: The URL string. Can only be used for threat assessment with type `url`.
```

<Global />

## Remarks

:::info

    This command currently only supports delegated permissions.

:::

## Examples

Create a file threat assessment

```sh
m365 purview threatassessment add --type file --expectedAssessment block --category malware --fileName 'test.txt' --path 'C:\Path\To\File.txt'
```

Create a url threat assessment

```sh
m365 purview threatassessment add --type url --expectedAssessment block --category phishing --url 'http://contoso.com'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
    {
      "id": "b0e69f1c-adda-4df2-2906-08dc2caa6b3f",
      "createdDateTime": "2024-02-13T15:42:43.5131654Z",
      "contentType": "file",
      "expectedAssessment": "block",
      "category": "malware",
      "status": "pending",
      "requestSource": "administrator",
      "fileName": "test.txt",
      "contentData": "dGVzdC50eHQ=",
      "createdBy": {
        "user": {
          "id": "fe36f75e-c103-410b-a18a-2bf6df06ac3a",
          "displayName": "John Doe"
        }
      }
    }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  category          : malware
  contentData       : dGVzdC50eHQ=
  contentType       : file
  createdBy         : {"user":{"id":"fe36f75e-c103-410b-a18a-2bf6df06ac3a","displayName":"John Doe"}}
  createdDateTime   : 2024-02-13T16:15:00.4125206Z
  expectedAssessment: block
  fileName          : test.txt
  id                : be1223c4-4e92-4a4c-8c16-08dc2caeedba
  requestSource     : administrator
  status            : pending
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,contentType,expectedAssessment,category,status,requestSource,fileName,contentData
  d31eb5f5-ecd5-4a8e-fb2a-08dc2caf00a8,2024-02-13T16:15:32.1741098Z,file,block,malware,pending,administrator,test.txt,dGVzdC50eHQ=
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # purview threatassessment add --type "file" --expectedAssessment "block" --category "malware" --path "C:	emp	est.txt"

  Date: 13/02/2024

  ## e3524baf-6ea6-4fab-68af-08dc2caf0ae3

  Property | Value
  ---------|-------
  id | e3524baf-6ea6-4fab-68af-08dc2caf0ae3
  createdDateTime | 2024-02-13T16:15:49.3342383Z
  contentType | file
  expectedAssessment | block
  category | malware
  status | pending
  requestSource | administrator
  fileName | test.txt
  contentData | dGVzdC50eHQ=
  ```

  </TabItem>
</Tabs>
