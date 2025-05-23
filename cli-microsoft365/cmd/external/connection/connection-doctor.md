-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# external connection doctor

Checks if the external connection is correctly configured for use with a specified user experience in Microsoft 365

## Usage

```sh
m365 external connection doctor [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the external connection to check.

`--ux [ux]`
: Microsoft 365 experience for which to check compatibility. Allowed values `copilot`, `search`, `all` (default)
```

<Global />

## Remarks

The `external connection doctor` command runs several automated checks to verify if an external connection is correctly configured for use with a user experience in Microsoft 365.

Check|ID|UX|Type|Description
-----|--|:--:|--|------------
Required semantic labels|`copilotRequiredSemanticLabels`|Copilot|Required|Checks if the external connection schema has the required semantic labels configured: `title`, `url` and `iconUrl`
Searchable properties|Copilot|`searchableProperties`|Required|Checks if the external connection schema has at least one searchable property
Items have content ingested|`contentIngested`|Copilot|Required|Checks if external items have content ingested
Connection configured for inline results|`enabledForInlineResults`|Copilot|Required (manual)|Check if the external connection is configured for inline results
Items have activities recorded|`itemsHaveActivities`|Copilot|Recommended (manual)|Check if external items have activities recorded
Meaningful connection name and description|`meaningfulNameAndDescription`|Copilot|Required (manual)|Check if the external connection has a meaningful name and description
Semantic labels|`semanticLabels`|Search|Recommended|Checks if the external connection schema uses semantic labels
Searchable properties|`searchableProperties`|Search|Recommended|Checks if the external connection schema has at least one searchable property
Result types|`resultType`|Search|Recommended|Checks if the external connection has a result type configured
Items have content ingested|`contentIngested`|Search|Recommended|Checks if external items have content ingested
Items have activities recorded|`itemsHaveActivities`|Search|Recommended|Check if external items have activities recorded
urlToItemResolver configured|`urlToItemResolver`|All|Recommended|Checks if the external connection has at least one urlToItemResolver configured

Required checks must pass for the external connection to be compatible with the specified user experience. Recommended checks are optional, but recommended for optimal user experience.

Some checks must be done manually, because there are no APIs available to verify the configuration automatically.

When you check the compatibility with all UXs, and there are multiple checks with the same ID, the command will use the first matching check, following the order listed above.

## Examples

Checks if the external connection with the specified ID is correctly configured for use with Copilot for Microsoft 365.

```sh
m365 external connection doctor --id contosoproducts --ux copilot
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "loadExternalConnection",
      "text": "Load connection",
      "type": "required",
      "status": "passed"
    },
    {
      "id": "loadSchema",
      "text": "Load schema",
      "type": "required",
      "status": "passed"
    },
    {
      "id": "copilotRequiredSemanticLabels",
      "text": "Required semantic labels",
      "type": "required",
      "errorMessage": "Missing label iconUrl",
      "status": "failed"
    },
    {
      "id": "searchableProperties",
      "text": "Searchable properties",
      "type": "required",
      "status": "passed"
    },
    {
      "id": "contentIngested",
      "text": "Items have content ingested",
      "type": "required",
      "status": "passed"
    },
    {
      "id": "enabledForInlineResults",
      "text": "Connection configured for inline results",
      "type": "required",
      "status": "manual"
    },
    {
      "id": "itemsHaveActivities",
      "text": "Items have activities recorded",
      "type": "recommended",
      "status": "manual"
    },
    {
      "id": "meaningfulNameAndDescription",
      "text": "Meaningful connection name and description",
      "type": "required",
      "status": "manual"
    },
    {
      "id": "urlToItemResolver",
      "text": "urlToItemResolver configured",
      "type": "recommended",
      "status": "passed"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  √ Load connection
  √ Load schema
  × Required semantic labels: Missing label iconUrl
  √ Searchable properties
  √ Items have content ingested
  i Connection configured for inline results (manual)
  i Items have activities recorded (manual)
  i Meaningful connection name and description (manual)
  √ urlToItemResolver configured
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,text,type,status,errorMessage
  loadExternalConnection,Load connection,required,passed,
  loadSchema,Load schema,required,passed,
  copilotRequiredSemanticLabels,Required semantic labels,required,failed,Missing label iconUrl
  searchableProperties,Searchable properties,required,passed,
  contentIngested,Items have content ingested,required,passed,
  enabledForInlineResults,Connection configured for inline results,required,manual,
  itemsHaveActivities,Items have activities recorded,recommended,manual,
  meaningfulNameAndDescription,Meaningful connection name and description,required,manual,
  urlToItemResolver,urlToItemResolver configured,recommended,passed,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # external connection doctor --id "msgraphdocs" --ux "copilot"

  Date: 11/23/2023

  Check|Type|Status|Error message
  :----|:--:|:----:|:------------
  Load connection|required|passed|
  Load schema|required|passed|
  Required semantic labels|required|failed|Missing label iconUrl
  Searchable properties|required|passed|
  Items have content ingested|required|passed|
  Connection configured for inline results|required|manual|
  Items have activities recorded|recommended|manual|
  Meaningful connection name and description|required|manual|
  urlToItemResolver configured|recommended|passed|
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph connector experiences: [https://learn.microsoft.com/graph/connecting-external-content-experiences](https://learn.microsoft.com/graph/connecting-external-content-experiences)
