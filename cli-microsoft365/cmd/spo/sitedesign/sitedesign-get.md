-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign get

Gets information about the specified site design

## Usage

```sh
m365 spo sitedesign get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: Site design ID. Specify either `id` or `title` but not both.

`--title [title]`
: Site design title. Specify either `id` or `title` but not both.
```

<Global />

## Remarks

If the specified `id` or `title` doesn't refer to an existing site design, you will get a `File not found` error.

## Examples

Get information about the site design with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_

```sh
m365 spo sitedesign get --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a
```

Get information about the site design with title _Contoso Site Design_

```sh
m365 spo sitedesign get --title "Contoso Site Design"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Description": null,
    "DesignPackageId": "00000000-0000-0000-0000-000000000000",
    "DesignType": "0",
    "ExpandedPreviewImages": [],
    "InternalName": null,
    "IsDefault": false,
    "IsOutOfBoxTemplate": false,
    "IsTenantAdminOnly": false,
    "ListColor": "0",
    "ListIcon": "0",
    "PreviewImageAltText": null,
    "PreviewImageUrl": null,
    "RequiresClassConnected": false,
    "RequiresGroupConnected": false,
    "RequiresSyntexLicense": false,
    "RequiresTeamsConnected": false,
    "RequiresYammerConnected": false,
    "SiteScriptIds": [
      "0c88bed7-943b-42aa-8fef-8fb69eebe3fe"
    ],
    "SupportedWebTemplates": [],
    "TargetPlatforms": [],
    "TemplateAssets": [],
    "TemplateFeatures": [],
    "ThumbnailUrl": null,
    "Title": "Contoso team site",
    "WebTemplate": "64",
    "Id": "00281728-3bc1-41d3-92b6-8fc493dcf4cc",
    "Order": null,
    "Version": 1
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Description            : null
  DesignPackageId        : 00000000-0000-0000-0000-000000000000
  DesignType             : 0
  ExpandedPreviewImages  : []
  Id                     : 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  InternalName           : null
  IsDefault              : false
  IsOutOfBoxTemplate     : false
  IsTenantAdminOnly      : false
  ListColor              : 0
  ListIcon               : 0
  Order                  : null
  PreviewImageAltText    : null
  PreviewImageUrl        : null
  RequiresClassConnected : false
  RequiresGroupConnected : false
  RequiresSyntexLicense  : false
  RequiresTeamsConnected : false
  RequiresYammerConnected: false
  SiteScriptIds          : ["0c88bed7-943b-42aa-8fef-8fb69eebe3fe"]
  SupportedWebTemplates  : []
  TargetPlatforms        : []
  TemplateAssets         : []
  TemplateFeatures       : []
  ThumbnailUrl           : null
  Title                  : Contoso team site
  Version                : 1
  WebTemplate            : 64
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  DesignPackageId,DesignType,IsDefault,IsOutOfBoxTemplate,IsTenantAdminOnly,ListColor,ListIcon,RequiresClassConnected,RequiresGroupConnected,RequiresSyntexLicense,RequiresTeamsConnected,RequiresYammerConnected,Title,WebTemplate,Id,Version
  00000000-0000-0000-0000-000000000000,0,,,,0,0,,,,,,Contoso team site,64,00281728-3bc1-41d3-92b6-8fc493dcf4cc,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign get --id "00281728-3bc1-41d3-92b6-8fc493dcf4cc"

  Date: 2023-06-22

  ## Contoso team site (00281728-3bc1-41d3-92b6-8fc493dcf4cc)

  Property | Value
  ---------|-------
  DesignPackageId | 00000000-0000-0000-0000-000000000000
  DesignType | 0
  IsDefault | false
  IsOutOfBoxTemplate | false
  IsTenantAdminOnly | false
  ListColor | 0
  ListIcon | 0
  RequiresClassConnected | false
  RequiresGroupConnected | false
  RequiresSyntexLicense | false
  RequiresTeamsConnected | false
  RequiresYammerConnected | false
  Title | Contoso team site
  WebTemplate | 64
  Id | 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  Version | 1
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
