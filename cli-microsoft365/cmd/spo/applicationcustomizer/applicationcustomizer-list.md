-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo applicationcustomizer list

Get a list of application customizers that are added to a site

## Usage

```sh
m365 spo applicationcustomizer list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The url of the site.

`-s, --scope [scope]`
: Scope of the application customizers. Allowed values `Site`, `Web`, `All`. Defaults to `All`.
```

<Global />

## Remarks

This command can be used for retrieving a list of application customizers from a specific site. To retrieve a list of application customizers that are installed tenant-wide, view our dedicated [spo tenant applicationcustomizer list](../tenant/tenant-applicationcustomizer-list.mdx) command.

## Examples

Retrieves a list of application customizers.

```sh
m365 spo applicationcustomizer list --webUrl https://contoso.sharepoint.com/sites/sales
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
      "Scope": 3,
      "ScriptBlock": null,
      "ScriptSrc": null,
      "Sequence": 65536,
      "Title": "HelloWorld",
      "Url": null,
      "VersionOfUserCustomAction": "1.0.1.0"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Location                                   Name                                    Scope
  ------------------------------------  -----------------------------------------  --------------------------------------  -----
  4a428b32-08cf-45c7-9986-17585af38806  EXAMPLE_SECRET_VALUE_PLACEHOLDER  {4a428b32-08cf-45c7-9986-17585af38806}  3
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientSideComponentId,ClientSideComponentProperties,CommandUIExtension,Description,Group,HostProperties,Id,ImageUrl,Location,Name,RegistrationId,RegistrationType,Scope,ScriptBlock,ScriptSrc,Sequence,Title,Url,VersionOfUserCustomAction
  9a8b100c-246b-4592-9454-67826523e159,"{""testMessage"":""Test message""}",,,,,4a428b32-08cf-45c7-9986-17585af38806,,EXAMPLE_SECRET_VALUE_PLACEHOLDER,{4a428b32-08cf-45c7-9986-17585af38806},,0,3,,,65536,HelloWorld,,1.0.1.0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo applicationcustomizer list --webUrl "https://contoso.sharepoint.com/sites/Marketing"

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
  Scope | 3
  Sequence | 65536
  Title | HelloWorld
  VersionOfUserCustomAction | 1.0.1.0
  ```

  </TabItem>
</Tabs>
