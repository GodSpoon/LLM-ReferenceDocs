-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph openextension get

Retrieves a specific open extension for a resource

## Usage

```sh
m365 graph openextension get [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the open extension to retrieve.

`-i, --resourceId <resourceId>`
: The Id of the resource for which to retrieve the open extension.

`-t, --resourceType <resourceType>`
: The type of resource. Allowed values are `user`, `group`, `device`, `organization`.
```

<Global />

## Examples

Retrieve a specified open extension for a user specified by id.

```sh
m365 graph openextension get --resourceId eb77fbcf-6fe8-458b-985d-1747284793bc --name 'com.contoso.roamingSettings' --resourceType user
```

Retrieve a specified open extension for a user specified by UPN.

```sh
m365 graph openextension get --resourceId john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "extensionName": "com.contoso.roamingSettings",
    "name": "com.contoso.roamingSettings",
    "resourceId": "john.doe@contoso.com",
    "resourceType": "user",
    "theme": "dark",
    "color": "red",
    "language": "English",
    "id": "com.contoso.roamingSettings"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  color        : red
  extensionName: com.contoso.roamingSettings
  id           : com.contoso.roamingSettings
  language     : English
  name         : com.contoso.roamingSettings
  resourceId   : john.doe@contoso.com
  resourceType : user
  theme        : dark
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  extensionName,name,resourceId,resourceType,theme,color,language,id
  com.contoso.roamingSettings,com.contoso.roamingSettings,john.doe@contoso.com,user,dark,red,English,com.contoso.roamingSettings
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph openextension get --debug "false" --verbose "false" --resourceId "john.doe@contoso.com" --resourceType "user" --name "com.contoso.roamingSettings"

  Date: 2025-04-07

  ## com.contoso.roamingSettings (com.contoso.roamingSettings)

  Property | Value
  ---------|-------
  extensionName | com.contoso.roamingSettings
  name | com.contoso.roamingSettings
  resourceId | john.doe@contoso.com
  resourceType | user
  theme | dark
  color | red
  language | English
  id | com.contoso.roamingSettings
  ```
  
  </TabItem>
</Tabs>

## More information

- Open extensions: https://learn.microsoft.com/graph/extensibility-overview?tabs=http#open-extensions
