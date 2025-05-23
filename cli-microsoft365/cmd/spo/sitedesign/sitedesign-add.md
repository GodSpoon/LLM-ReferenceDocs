-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitedesign add

Adds site design for creating modern sites

## Usage

```sh
m365 spo sitedesign add [options]
```

## Options

```md definition-list
`-t, --title <title>`
: The display name of the site design

`-w, --webTemplate <webTemplate>`
: Identifies which base template to add the design to. Allowed values `TeamSite,CommunicationSite`

`-s, --siteScripts <siteScripts>`
: Comma-separated list of site script IDs. The scripts will run in the order listed

`-d, --description [description]`
: The display description of site design

`-m, --previewImageUrl [previewImageUrl]`
: The URL of a preview image. If none is specified SharePoint will use a generic image

`-a, --previewImageAltText [previewImageAltText]`
: The alt text description of the image for accessibility

`--thumbnailUrl [thumbnailUrl]`
: The new URL of a thumbnail image. If none is specified SharePoint will use a generic image

`--isDefault`
: Set if the site design is applied as the default site design
```

<Global />

## Remarks

Each time you execute the `spo sitedesign add` command, it will create a new site design with a unique ID. Before creating a site design, be sure that another design with the same name doesn't already exist.

When specifying IDs of site scripts to use with your site design, ensure that the IDs refer to existing site scripts or provisioning sites using the design will lead to unexpected results.

## Examples

Create new site design for provisioning modern team sites

```sh
m365 spo sitedesign add --title "Contoso team site" --webTemplate TeamSite --siteScripts "19b0e1b2-e3d1-473f-9394-f08c198ef43e,b2307a39-e878-458b-bc90-03bc578531d6"
```

Create new default site design for provisioning modern communication sites

```sh
m365 spo sitedesign add --title "Contoso communication site" --webTemplate CommunicationSite --siteScripts "19b0e1b2-e3d1-473f-9394-f08c198ef43e" --isDefault
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Description": null,
    "DesignPackageId": null,
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
      "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5"
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
  DesignPackageId        : null
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
  SiteScriptIds          : ["43d4ffa0-c7ee-4a97-91d7-db27e5b62de5"]
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
  DesignType,IsDefault,IsOutOfBoxTemplate,IsTenantAdminOnly,ListColor,ListIcon,RequiresClassConnected,RequiresGroupConnected,RequiresSyntexLicense,RequiresTeamsConnected,RequiresYammerConnected,Title,WebTemplate,Id,Version
  0,,,,0,0,,,,,,Contoso team site,64,00281728-3bc1-41d3-92b6-8fc493dcf4cc,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitedesign add --title "Contoso team site" --webTemplate "TeamSite" --siteScripts "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5"

  Date: 2023-06-22

  ## Contoso team site (00281728-3bc1-41d3-92b6-8fc493dcf4cc)

  Property | Value
  ---------|-------
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
- Customize a default site design: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/customize-default-site-design](https://learn.microsoft.com/sharepoint/dev/declarative-customization/customize-default-site-design)
- Site design JSON schema: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)
