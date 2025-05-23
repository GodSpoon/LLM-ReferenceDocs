-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp card list

Lists Microsoft Power Platform cards in the specified Power Platform environment.

## Usage

```sh
m365 pp card list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

List cards in a specific environment.

```sh
m365 pp card list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

List cards in a specific environment as admin.

```sh
m365 pp card list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "solutionid":"fd140aae-4df4-11dd-bd17-0019b9312238",
      "modifiedon":"2022-10-25T14:44:48Z",
      "_owninguser_value":"4f175d04-b952-ed11-bba2-000d3adf774e",
      "overriddencreatedon":null,
      "ismanaged":false,
      "schemaversion":null,
      "importsequencenumber":null,
      "tags":null,
      "componentidunique":"24205370-bc43-4c5e-b095-16da18f0b1a3",
      "_modifiedonbehalfby_value":null,
      "componentstate":0,
      "statecode":0,
      "name":"Tasks List",
      "versionnumber":4451230,
      "utcconversiontimezonecode":null,
      "cardid":"0eab9392-7354-ed11-bba2-000d3adf774e",
      "publishdate":null,
      "_createdonbehalfby_value":null,
      "_modifiedby_value":"4f175d04-b952-ed11-bba2-000d3adf774e",
      "createdon":"2022-10-25T14:44:48Z",
      "overwritetime":"1900-01-01T00:00:00Z",
      "_owningbusinessunit_value":"b419f090-fe22-ec11-b6e5-000d3ab596a1",
      "hiddentags":null,
      "description":" ",
      "appdefinition":"{\"screens\":{\"main\":{\"template\":{\"type\":\"AdaptiveCard\",\"body\":[{\"type\":\"TextBlock\",\"size\":\"Medium\",\"weight\":\"bolder\",\"text\":\"Your card title goes here\"},{\"type\":\"TextBlock\",\"text\":\"Add and remove element to customize your new card.\",\"wrap\":true}],\"actions\":[],\"$schema\":\"http://adaptivecards.io/schemas/1.4.0/adaptive-card.json\",\"version\":\"1.4\"},\"verbs\":{\"submit\":\"echo\"}}},\"sampleData\":{\"main\":{}},\"connections\":{},\"variables\":{},\"flows\":{}}",
      "statuscode":1,
      "remixsourceid":null,
      "sizes":null,
      "coowners":null,
      "_owningteam_value":null,
      "_createdby_value":"4f175d04-b952-ed11-bba2-000d3adf774e",
      "_ownerid_value":"4f175d04-b952-ed11-bba2-000d3adf774e",
      "publishsourceid":null,
      "timezoneruleversionnumber":null,
      "iscustomizable":{
        "Value":true,
        "CanBeChanged":true,
        "ManagedPropertyLogicalName":"iscustomizableanddeletable"
      },
      "owninguser":{
        "azureactivedirectoryobjectid":"78637d62-e872-4dc9-b7c1-bd161e631682",
        "fullname":"# John Doe",
        "systemuserid":"4f175d04-b952-ed11-bba2-000d3adf774e",
        "ownerid":"4f175d04-b952-ed11-bba2-000d3adf774e"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name        cardid                                publishdate          createdon             modifiedon
  ----------  ------------------------------------  -----------          --------------------  --------------------
  Tasks List  0eab9392-7354-ed11-bba2-000d3adf774e  2022-10-30T16:00:00Z 2022-10-25T14:44:48Z  2022-10-25T14:44:48Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,cardid,publishdate,createdon,modifiedon
  Tasks List,0eab9392-7354-ed11-bba2-000d3adf774e,2022-10-30T16:00:00Z,2022-10-25T14:44:48Z,2022-10-25T14:44:48Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp card list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  ## Tasks List

  Property | Value
  ---------|-------
  solutionid | fd140aae-4df4-11dd-bd17-0019b9312238
  modifiedon | 2022-10-25T14:44:48Z
  \_owninguser\_value | 4f175d04-b952-ed11-bba2-000d3adf774e
  overriddencreatedon | null
  ismanaged | false
  schemaversion | null
  tags | null
  importsequencenumber | null
  componentidunique | 24205370-bc43-4c5e-b095-16da18f0b1a3
  \_modifiedonbehalfby\_value | null
  componentstate | 0
  statecode | 0
  name | Tasks List
  versionnumber | 4451230
  utcconversiontimezonecode | null
  cardid | 0eab9392-7354-ed11-bba2-000d3adf774e
  publishdate | null
  \_createdonbehalfby\_value | null
  \_modifiedby\_value | 4f175d04-b952-ed11-bba2-000d3adf774e
  createdon | 2022-10-25T14:44:48Z
  overwritetime | 1900-01-01T00:00:00Z
  \_owningbusinessunit\_value | b419f090-fe22-ec11-b6e5-000d3ab596a1
  hiddentags | null
  description |
  statuscode | 1
  remixsourceid | null
  sizes | null
  \_createdby\_value | 4f175d04-b952-ed11-bba2-000d3adf774e
  \_owningteam\_value | null
  coowners | null
  \_ownerid\_value | 4f175d04-b952-ed11-bba2-000d3adf774e
  publishsourceid | null
  timezoneruleversionnumber | null
  ```

  </TabItem>
</Tabs>
