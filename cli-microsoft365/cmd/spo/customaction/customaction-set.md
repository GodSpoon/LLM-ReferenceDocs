-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo customaction set

Updates a user custom action for site or site collection

## Usage

```sh
m365 spo customaction set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: Url of the site or site collection to update the custom action.

`-i, --id <id>`
: ID of the custom action to update.

`-n, --name [name]`
: The name of the custom action.

`-t, --title [title]`
: The title of the custom action.

`-l, --location [location]`
: The actual location where this custom action need to be added like `CommandUI.Ribbon`.

`-g, --group [group]`
: The group of the custom action like `SiteActions`.

`-d, --description [description]`
: The description of the custom action.

`--sequence [sequence]`
: Sequence of this CustomAction being injected. Use when you have a specific sequence with which to have multiple CustomActions being added to the page.

`--actionUrl [actionUrl]`
: The URL, URI or JavaScript function associated with the action. URL example `~site/_layouts/sampleurl.aspx` or `~sitecollection/_layouts/sampleurl.aspx`.

`--imageUrl [imageUrl]`
: The URL of the image associated with the custom action.

`-e, --commandUIExtension [commandUIExtension]`
: XML fragment that determines user interface properties of the custom action.

`--registrationId [registrationId]`
: Specifies the identifier of the list or item content type that this action is associated with, or the file type or programmatic identifier.

`--registrationType [registrationType]`
: Specifies the type of object associated with the custom action. Allowed values `None`, `List`, `ContentType`, `ProgId`, `FileType`. Defaults to `None`.

`--rights [rights]`
: A case-sensitive string array that contain the permissions needed for the custom action. Allowed values `EmptyMask`, `ViewListItems`, `AddListItems`, `EditListItems`, `DeleteListItems`, `ApproveItems`, `OpenItems`, `ViewVersions`, `DeleteVersions`, `CancelCheckout`, `ManagePersonalViews`, `ManageLists`, `ViewFormPages`, `AnonymousSearchAccessList`, `Open`, `ViewPages`, `AddAndCustomizePages`, `ApplyThemeAndBorder`, `ApplyStyleSheets`, `ViewUsageData`, `CreateSSCSite`, `ManageSubwebs`, `CreateGroups`, `ManagePermissions`, `BrowseDirectories`, `BrowseUserInfo`, `AddDelPrivateWebParts`, `UpdatePersonalWebParts`, `ManageWeb`, `AnonymousSearchAccessWebLists`, `UseClientIntegration`, `UseRemoteAPIs`, `ManageAlerts`, `CreateAlerts`, `EditMyUserInfo`, `EnumeratePermissions`, `FullMask`. Defaults to `EmptyMask`.

`-s, --scope [scope]`
: Scope of the existing custom action. Allowed values `Site`, `Web`, `All`. Default `All`. Note, this would not update the scope, but might speed up the execution of the scope of the custom action is known.

`--scriptBlock [scriptBlock]`
: Specifies a block of script to be executed. This attribute is only applicable when the Location attribute is set to ScriptLink.

`--scriptSrc [scriptSrc]`
: Specifies a file that contains script to be executed. This attribute is only applicable when the Location attribute is set to ScriptLink.

`-c, --clientSideComponentId [clientSideComponentId]`
: The Client Side Component Id (GUID) of the custom action.

`-p, --clientSideComponentProperties [clientSideComponentProperties]`
: The Client Side Component Properties of the custom action. Specify values as a JSON string : `'{"testMessage":"Test message"}'`.
```

<Global />

## Remarks

Running this command from the Windows Command Shell (cmd.exe) or PowerShell for Windows OS XP, 7, 8, 8.1 without bash installed might require additional formatting for command options that have JSON, XML or JavaScript values because the command shell treats quotes differently. For example, this is how ApplicationCustomizer user custom action can be created from the Windows cmd.exe:

```sh
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --clientSideComponentProperties '{\"testMessage\":\"Test message\"}'
```

The `--rights` option accepts **case-sensitive** values.

Note, specifying the scope option might speed up the execution of the command, but would not update the scope. If the scope has to be changed, then the existing custom action should be removed and new should be added with different scope.

:::warning[Escaping JSON in PowerShell]

When using the `--clientSideComponentProperties` option it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::

## Examples

Updates a tenant-wide SharePoint Framework Application Customizer extension properties in the specified site.

```sh
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --clientSideComponentProperties '{"testMessage":"Test message"}'
```

Updates a tenant-wide SharePoint Framework **modern List View** Command Set extension in the specified site.

```sh
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --clientSideComponentProperties '{"sampleTextOne":"One item is selected in the list.", "sampleTextTwo":"This command is always visible."}' --sequence 100
```

Updates a url custom action in the SiteActions menu in the specified site.

```sh
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --actionUrl "~site/SitePages/Home.aspx"
```

Updates a ScriptLink custom action with script source in **classic pages** in the specified site collection.

```sh
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --scriptSrc "~sitecollection/SiteAssets/YourScript.js"
```

Creates a custom action with delegated rights in the SiteActions menu in the specified site.

```sh
m365 spo customaction set --webUrl https://contoso.sharepoint.com/sites/test --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --rights "AddListItems,DeleteListItems,ManageLists"
```

## Response

The command won't return a response on success.

## More information

- UserCustomAction REST API resources: [https://msdn.microsoft.com/en-us/library/office/dn531432.aspx#bk_UserCustomAction](https://msdn.microsoft.com/en-us/library/office/dn531432.aspx#bk_UserCustomAction)
- UserCustomAction Locations and Group IDs: [https://msdn.microsoft.com/en-us/library/office/bb802730.aspx](https://msdn.microsoft.com/en-us/library/office/bb802730.aspx)
- UserCustomAction Element: [https://msdn.microsoft.com/en-us/library/office/ms460194.aspx](https://msdn.microsoft.com/en-us/library/office/ms460194.aspx)
- UserCustomAction Rights: [https://msdn.microsoft.com/en-us/library/office/EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://msdn.microsoft.com/en-us/library/office/EXAMPLE_SECRET_VALUE_PLACEHOLDER)
