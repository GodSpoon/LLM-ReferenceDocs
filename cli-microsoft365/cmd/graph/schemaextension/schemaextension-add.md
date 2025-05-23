-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph schemaextension add

Creates a Microsoft Graph schema extension

## Usage

```sh
m365 graph schemaextension add [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The unique identifier for the schema extension definition

`-d, --description [description]`
: Description of the schema extension

`--owner <owner>`
: The Id of the Microsoft Entra application that is the owner of the schema extension

`-t, --targetTypes <targetTypes>`
: Comma-separated list of Microsoft Graph resource types the schema extension targets

`-p, --properties`
: The collection of property names and types that make up the schema extension definition formatted as a JSON string
```

<Global />

## Remarks

To create a schema extension, you have to specify a unique ID for the schema extension. You can assign a value in one of two ways:

- concatenate the name of one of your verified domains with a name for the schema extension to form a unique string in this format, `{domainName}_{schemaName}`, eg. `contoso_mySchema`.

    NOTE: Only verified domains under the following top-level domains are supported: .com, .net, .gov, .edu or .org.

- Provide a schema name, and let Microsoft Graph use that schema name to complete the id assignment in this format: `ext{8-random-alphanumeric-chars}_{schema-name}`, eg. `extkvbmkofy_mySchema`.

The schema extension ID cannot be changed after creation.

The schema extension owner is the ID of the Microsoft Entra application that is the owner of the schema extension. Once set, this property is read-only and cannot be changed.

The target types are the set of Microsoft Graph resource types (that support schema extensions) that this schema extension definition can be applied to. This option is specified as a comma-separated list

:::warning[Escaping JSON in PowerShell]

When using the `--properties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

## Examples

Create a schema extension

```sh
m365 graph schemaextension add --id MySchemaExtension --description "My Schema Extension" --targetTypes Group --owner 62375ab9-6b52-47ed-826b-58e47e0e304b --properties '[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]'
```

Create a schema extension with a verified domain

```sh
m365 graph schemaextension add --id contoso_MySchemaExtension --description "My Schema Extension" --targetTypes Group --owner 62375ab9-6b52-47ed-826b-58e47e0e304b --properties '[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "extb4lob7o4_MySchemaExtension",
    "description": "My Schema Extension",
    "targetTypes": [
      "Group"
    ],
    "status": "InDevelopment",
    "owner": "19b5bd1f-3d5e-404a-80f5-ca840b40a082",
    "properties": [
      {
        "name": "myProp1",
        "type": "Integer"
      },
      {
        "name": "myProp2",
        "type": "String"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  description: My Schema Extension
  id         : extuf4mntoy_MySchemaExtension
  owner      : 19b5bd1f-3d5e-404a-80f5-ca840b40a082
  properties : [{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]
  status     : InDevelopment
  targetTypes: ["Group"]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,description,status,owner
  extlywhx1h4_MySchemaExtension,My Schema Extension,InDevelopment,19b5bd1f-3d5e-404a-80f5-ca840b40a082
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph schemaextension add --id "MySchemaExtension" --description "My Schema Extension" --targetTypes "Group" --owner "19b5bd1f-3d5e-404a-80f5-ca840b40a082" --properties "[{"name":"myProp1","type":"Integer"},{"name":"myProp2","type":"String"}]"

  Date: 2023-05-22

  ## extnevl1fo8_MySchemaExtension

  Property | Value
  ---------|-------
  id | extnevl1fo8\_MySchemaExtension
  description | My Schema Extension
  status | InDevelopment
  owner | 19b5bd1f-3d5e-404a-80f5-ca840b40a082
  ```

  </TabItem>
</Tabs>
