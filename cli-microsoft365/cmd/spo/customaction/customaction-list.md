-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo customaction list

Lists user custom actions for site or site collection

## Usage

```sh
m365 spo customaction list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Url of the site or site collection to retrieve the custom action from.

`-s, --scope [scope]`
: Scope of the custom action. Allowed values `Site`, `Web`, `All`. Default `All`.
```

<Global />

## Remarks

When using the text output type (default), the command lists only the values of the `Name`, `Location`, `Scope` and `Id` properties of the custom action. When setting the output type to JSON, all available properties are included in the command output.

## Examples

Return details about all user custom actions located in the specified site or site collection.

```sh
m365 spo customaction list --webUrl https://contoso.sharepoint.com/sites/test
```

Return details about all user custom actions located in the specified site collection.

```sh
m365 spo customaction list --webUrl https://contoso.sharepoint.com/sites/test --scope Site
```

Return details about all user custom actions located in the specified site.

```sh
m365 spo customaction list --webUrl https://contoso.sharepoint.com/sites/test --scope Web
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "ClientSideComponentId": "b41916e7-e69d-467f-b37f-ff8ecf8f99f2",
      "ClientSideComponentProperties": "'{testMessage:Test message}'",
      "CommandUIExtension": null,
      "Description": null,
      "Group": null,
      "HostProperties": "",
      "Id": "a70d8013-3b9f-4601-93a5-0e453ab9a1f3",
      "ImageUrl": null,
      "Location": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "Name": "YourName",
      "RegistrationId": null,
      "RegistrationType": 0,
      "Rights": {
        "High": 0,
        "Low": 0
      },
      "Scope": 3,
      "ScriptBlock": null,
      "ScriptSrc": null,
      "Sequence": 0,
      "Title": "YourAppCustomizer",
      "Url": null,
      "VersionOfUserCustomAction": "16.0.1.0"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Name             Location                                   Scope  Id
  ---------------  -----------------------------------------  -----  ------------------------------------
  YourName         EXAMPLE_SECRET_VALUE_PLACEHOLDER  Web    a70d8013-3b9f-4601-93a5-0e453ab9a1f3
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  ClientSideComponentId,ClientSideComponentProperties,HostProperties,Id,Location,Name,RegistrationType,Scope,Sequence,Title,VersionOfUserCustomAction
  b41916e7-e69d-467f-b37f-ff8ecf8f99f2,'{testMessage:Test message}',,a70d8013-3b9f-4601-93a5-0e453ab9a1f3,EXAMPLE_SECRET_VALUE_PLACEHOLDER,YourName,0,Web,0,YourAppCustomizer,16.0.1.0
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo customaction list --webUrl "https://contoso.sharepoint.com/sites/sales"

  Date: 10/2/2023

  ## YourAppCustomizer (a70d8013-3b9f-4601-93a5-0e453ab9a1f3)

  Property | Value
  ---------|-------
  ClientSideComponentId | b41916e7-e69d-467f-b37f-ff8ecf8f99f2
  ClientSideComponentProperties | '{testMessage:Test message}'
  HostProperties |
  Id | a70d8013-3b9f-4601-93a5-0e453ab9a1f3
  Location | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Name | YourName
  RegistrationType | 0
  Scope | Web
  Sequence | 0
  Title | YourAppCustomizer
  VersionOfUserCustomAction | 16.0.1.0
  ```

  </TabItem>
</Tabs>

## More information

- UserCustomAction REST API resources: [https://msdn.microsoft.com/en-us/library/office/dn531432.aspx#bk_UserCustomAction](https://msdn.microsoft.com/en-us/library/office/dn531432.aspx#bk_UserCustomAction)
