-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign set

Updates a site design with new values

## Usage

```sh
m365 spo sitedesign set [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the site design to update

`-t, --title [title]`
: The new display name of the updated site design

`-w, --webTemplate [webTemplate]`
: The new template to add the site design to. Allowed values `TeamSite,CommunicationSite`

`-s, --siteScripts [siteScripts]`
: Comma-separated list of new site script IDs. The scripts will run in the order listed

`-d, --description [description]`
: The new display description of updated site design

`-m, --previewImageUrl [previewImageUrl]`
: The new URL of a preview image. If none is specified SharePoint will use a generic image

`-a, --previewImageAltText [previewImageAltText]`
: The new alt text description of the image for accessibility

`--thumbnailUrl [thumbnailUrl]`
: The new URL of a thumbnail image. If none is specified SharePoint will use a generic image

`-v, --version [version]`
: The new version number for the site design

`--isDefault [isDefault]`
: Set to true if the site design is applied as the default site design
```

<Global />

## Remarks

If you had previously set the `isDefault` option to `true`, and wish for it to remain `true`, you must pass in this option again or it will be reset to `false`.

When specifying IDs of site scripts to use with your site design, ensure that the IDs refer to existing site scripts or provisioning sites using the design will lead to unexpected results.

## Examples

Update the site design title and version

```sh
m365 spo sitedesign set --id 9b142c22-037f-4a7f-9017-e9d8c0e34b98 --title "Contoso site design" --version 2
```

Update the site design to be the default design for provisioning modern communication sites

```sh
m365 spo sitedesign set --id 9b142c22-037f-4a7f-9017-e9d8c0e34b98 --webTemplate CommunicationSite  --isDefault true
```


Update the site design to be the default design for provisioning modern communication sites, with specific scripts

```sh
m365 spo sitedesign set --id 9b142c22-037f-4a7f-9017-e9d8c0e34b98 --webTemplate CommunicationSite  --isDefault true --siteScripts "19b0e1b2-e3d1-473f-9394-f08c198ef43e,b2307a39-e878-458b-bc90-03bc578531d6"
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
    "Title": "Contoso site design",
    "WebTemplate": "64",
    "Id": "00281728-3bc1-41d3-92b6-8fc493dcf4cc",
    "Order": null,
    "Version": 2
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
  Title                  : Contoso site design
  Version                : 2
  WebTemplate            : 64
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  DesignPackageId,DesignType,IsDefault,IsOutOfBoxTemplate,IsTenantAdminOnly,ListColor,ListIcon,RequiresClassConnected,RequiresGroupConnected,RequiresSyntexLicense,RequiresTeamsConnected,RequiresYammerConnected,Title,WebTemplate,Id,Version
  00000000-0000-0000-0000-000000000000,0,,,,0,0,,,,,,Contoso site design,64,00281728-3bc1-41d3-92b6-8fc493dcf4cc,2
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign set --id "00281728-3bc1-41d3-92b6-8fc493dcf4cc" --title "Contoso site design" --version "2"

  Date: 2023-06-22

  ## Contoso site design (00281728-3bc1-41d3-92b6-8fc493dcf4cc)

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
  Title | Contoso site design
  WebTemplate | 64
  Id | 00281728-3bc1-41d3-92b6-8fc493dcf4cc
  Version | 2
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
- Customize a default site design: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/customize-default-site-design](https://learn.microsoft.com/sharepoint/dev/declarative-customization/customize-default-site-design)
- Site design JSON schema: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)
