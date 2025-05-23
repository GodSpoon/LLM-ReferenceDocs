-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo applicationcustomizer get

Get an application customizer that is added to a site

## Usage

```sh
m365 spo applicationcustomizer get [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site.

`-t, --title [title]`
: The title of the Application Customizer. Specify either `title`, `id` or `clientSideComponentId`.

`-i, --id [id]`
: The id of the Application Customizer. Specify either `title`, `id` or `clientSideComponentId`.

`-c, --clientSideComponentId  [clientSideComponentId]`
: The Client Side Component Id (GUID) of the application customizer. Specify either `title`, `id` or `clientSideComponentId`.

`-s, --scope [scope]`
: Scope of the application customizer. Allowed values: `Site`, `Web`, `All`. Defaults to `All`.

`-p, --clientSideComponentProperties`
: Only output the client-side component properties.
```

<Global />

## Remarks

This command can be used for retrieving an application customizer from a specific site. To retrieve an application customizer that's installed tenant-wide, view our dedicated [spo tenant applicationcustomizer get](../tenant/tenant-applicationcustomizer-get.mdx) command.

## Examples

Retrieves an application customizer by title.

```sh
m365 spo applicationcustomizer get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```

Retrieves an application customizer by id.

```sh
m365 spo applicationcustomizer get --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales
```

Retrieves an application customizer by clientSideComponentId.

```sh
m365 spo applicationcustomizer get --clientSideComponentId 7096cded-b83d-4eab-96f0-df477ed7c0bc --webUrl https://contoso.sharepoint.com/sites/sales
```

Retrieves an application customizer by title available at the site scope.

```sh
m365 spo applicationcustomizer get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales --scope site
```

Retrieves the client-side component properties of a application customizer.

```sh
m365 spo applicationcustomizer get --id 14125658-a9bc-4ddf-9c75-1b5767c9a337 --webUrl https://contoso.sharepoint.com/sites/sales --clientSideComponentProperties
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "ClientSideComponentId": "9a8b100c-246b-4592-9454-67826523e159",
    "ClientSideComponentProperties": "{\"testMessage\":\"Test message\"}",
    "CommandUIExtension": null,
    "Description": null,
    "Group": null,
    "HostProperties": "",
    "Id": "4a428b32-08cf-45c7-9986-17585af38806",
    "ImageUrl": null,
    "Location": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "Name": "{4a428b32-08cf-45c7-9986-17585af38806}",
    "RegistrationId": null,
    "RegistrationType": 0,
    "Rights": {
      "High": 0,
      "Low": 0
    },
    "Scope": "Web",
    "ScriptBlock": null,
    "ScriptSrc": null,
    "Sequence": 65536,
    "Title": "HelloWorld",
    "Url": null,
    "VersionOfUserCustomAction": "1.0.1.0"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  ClientSideComponentId        : 9a8b100c-246b-4592-9454-67826523e159
  ClientSideComponentProperties: {"testMessage":"Test message"}
  CommandUIExtension           : null
  Description                  : null
  Group                        : null
  HostProperties               :
  Id                           : 4a428b32-08cf-45c7-9986-17585af38806
  ImageUrl                     : null
  Location                     : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Name                         : {4a428b32-08cf-45c7-9986-17585af38806}
  RegistrationId               : null
  RegistrationType             : 0
  Scope                        : Web
  ScriptBlock                  : null
  ScriptSrc                    : null
  Sequence                     : 65536
  Title                        : HelloWorld
  Url                          : null
  VersionOfUserCustomAction    : 1.0.1.0
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientSideComponentId,ClientSideComponentProperties,CommandUIExtension,Description,Group,Id,ImageUrl,Location,Name,RegistrationId,RegistrationType,Scope,ScriptBlock,ScriptSrc,Sequence,Title,Url,VersionOfUserCustomAction
  9a8b100c-246b-4592-9454-67826523e159,"{""testMessage"":""Test message""}",,,,4a428b32-08cf-45c7-9986-17585af38806,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,Some customizer,,0,Web,,,0,Some customizer,,16.0.1.0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo applicationcustomizer get --webUrl "https://contoso.sharepoint.com/sites/Marketing" --id "4a428b32-08cf-45c7-9986-17585af38806"

  Date: 16/05/2024

  ## HelloWorld (4a428b32-08cf-45c7-9986-17585af38806)

  Property | Value
  ---------|-------
  ClientSideComponentId | 9a8b100c-246b-4592-9454-67826523e159
  ClientSideComponentProperties | {"testMessage":"Test message"}
  HostProperties |
  Id | 4a428b32-08cf-45c7-9986-17585af38806
  Location | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Name | {4a428b32-08cf-45c7-9986-17585af38806}
  RegistrationType | 0
  Scope | Web
  Sequence | 65536
  Title | HelloWorld
  VersionOfUserCustomAction | 1.0.1.0
  ```

  </TabItem>
</Tabs>

### `clientSideComponentProperties` response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "testMessage": "Test message"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  testMessage: Test message
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  testMessage
  Test message
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo applicationcustomizer get --title "Some customizer" --webUrl "https://contoso.sharepoint.com/sites/sales" --scope "Web" --clientSideComponentProperties "true"

  Date: 15/05/2024

  Property | Value
  ---------|-------
  testMessage | Test message
  ```

  </TabItem>
</Tabs>
