-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# external item add

Creates external item

## Usage

```sh
m365 external item add [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the item to create

`--externalConnectionId <externalConnectionId>`
: The ID of the external connection on which to create the item

`--content <content>`
: External item content

`--contentType [contentType]`
: Type of content to load. Allowed values: `text` (default), `html`

`--acls <acls>`
: List of permissions to set on the item, in the format `accessType1,type1,value1;accessType2,type2,value2`, eg. `grant,everyone,everyone`
```
<Global />

## Remarks

When creating an external item, the options you specify will map to the external item properties, eg. `--author "Steve"` will set the `author` property of the external item to `Steve`.

If in your schema you have a multi-value property, to specify its value you need two things:

- you need to separate multiple values using `;#`, eg. `--author "Steve;#Bill"`
- you need to specify the type of the property as defined in the schema, eg. `--author@odata.type "Collection(String)"`

When creating items you can specify one or more permissions that define who can access the external item. The format of the permissions is `accessType1,type1,value1;accessType2,type2,value2`, eg. `grant,everyone,everyone`.

You can use the following access types:

- `grant` - grants access to the specified users or groups
- `deny` - denies access to the specified users or groups

You can use the following types:

- `everyone` - everyone
- `group` - an Entra group
- `user` - an Entra user
- `everyoneExceptGuests` - everyone except external users
- `externalGroup` - a group defined in the external system from which you're importing the content

For more information about using these options, see the Microsoft Graph API documentation and documentation about Microsoft Graph connectors.

## Examples

Creates an external item with simple properties that everyone is allowed to access

```sh
m365 external item add --id "pnp-ensure-siteassets-library" --externalConnectionId "samplesolutiongallery" --content "Ensure that the Site Assets library is created." --title "Ensure the Site Assets Library is created" --description "Ensure that the Site Assets library is created." --authors "Phil Harding" --acls "grant,everyone,everyone"
```

Creates an external item with multi-value properties accessible only to users from the specified Entra group

```sh
m365 external item add --id "pnp-ensure-siteassets-library" --externalConnectionId "samplesolutiongallery" --content "Ensure that the Site Assets library is created." --title "Ensure the Site Assets Library is created" --description "Ensure that the Site Assets library is created." --authors@odata.type "Collection(String)" --authors "Phil Harding;#Steve Smith" --acls "grant,group,Super users"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "pnp-ensure-siteassets-library",
    "acl": [
      {
        "type": "everyone",
        "value": "everyone",
        "accessType": "grant"
      }
    ],
    "properties": {
      "title": "Ensure the Site Assets Library is created",
      "description": "Ensure that the Site Assets library is created.",
      "authors": "Phil Harding"
    },
    "content": {
      "value": "Ensure that the Site Assets library is created.",
      "type": "text"
    },
    "activities": []
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  acl       : [{"type":"everyone","value":"everyone","accessType":"grant"}]
  activities: []
  content   : {"value":"Ensure that the Site Assets library is created.","type":"text"}
  id        : pnp-ensure-siteassets-library
  properties: {"title":"Ensure the Site Assets Library is created","description":"Ensure that the Site Assets library is created.","authors":"Phil Harding"}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id
  pnp-ensure-siteassets-library
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # m365 external item add --id "pnp-ensure-siteassets-library" --externalConnectionId "samplesolutiongallery" --content "Ensure that the Site Assets library is created." --title "Ensure the Site Assets Library is created" --description "Ensure that the Site Assets library is created." --authors "Phil Harding" --acls "grant,everyone,everyone"

  Date: 2023-10-28

  ## pnp-ensure-siteassets-library

  Property | Value
  ---------|-------
  id | pnp-ensure-siteassets-library
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph connectors access control list [https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER#access-control-list](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER#access-control-list)
- Create, update, and delete items added by your application via Microsoft Graph connectors [https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- Use external groups to manage permissions to Microsoft Graph connectors data sources [https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://learn.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
- Create externalItem [https://learn.microsoft.com/graph/api/EXAMPLE_SECRET_VALUE_PLACEHOLDER?view=graph-rest-1.0&tabs=http](https://learn.microsoft.com/graph/api/EXAMPLE_SECRET_VALUE_PLACEHOLDER?view=graph-rest-1.0&tabs=http)
