-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo page template list

Lists all page templates in the given site

## Usage

```sh
m365 spo page template list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site from which to retrieve available pages.
```

<Global />

## Examples

Lists all page templates in the given site

```sh
m365 spo page template list --webUrl https://contoso.sharepoint.com/sites/team-a
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AbsoluteUrl": "https://contoso.sharepoint.com/sites/SPDemo/SitePages/Templates/Company-Policy.aspx",
      "AuthorByline": [
        "i:0#.f|membership|user@contoso.com"
      ],
      "BannerImageUrl": "https://cdn.hubblecontent.osi.office.net/m365content/publish/d22d83c8-3fb2-4168-8902-a29dc31e95b1/thumbnails/large.jpg?file=1131975775.jpg",
      "BannerThumbnailUrl": "https://cdn.hubblecontent.osi.office.net/m365content/publish/d22d83c8-3fb2-4168-8902-a29dc31e95b1/thumbnails/large.jpg?file=1131975775.jpg",
      "CallToAction": "",
      "Categories": null,
      "ContentTypeId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "Description": "Company policy are set in place to establish the rules of conduct within an organization, outlining the responsibilities of both employees and employers. The management of company policy and procedures aim to protect the rights of workers as well as…",
      "DoesUserHaveEditPermission": true,
      "FileName": "Company-Policy.aspx",
      "FirstPublished": "0001-01-01T08:00:00Z",
      "Id": 27,
      "IsPageCheckedOutToCurrentUser": false,
      "IsWebWelcomePage": false,
      "Modified": "2022-11-26T10:51:12Z",
      "PageLayoutType": "Article",
      "Path": {
        "DecodedUrl": "SitePages/Templates/Company-Policy.aspx"
      },
      "PromotedState": 0,
      "Title": "Company Policy",
      "TopicHeader": null,
      "UniqueId": "06509101-7e2f-4467-afd2-97bad4a53ef2",
      "Url": "SitePages/Templates/Company-Policy.aspx",
      "Version": "0.1",
      "VersionInfo": {
        "LastVersionCreated": "0001-01-01T00:00:00-08:00",
        "LastVersionCreatedBy": ""
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  FileName             Id  PageLayoutType  Title           Url
  -------------------  --  --------------  --------------  ----------------------------------------
  Company-Policy.aspx  27  Article         Company Policy  SitePages/Templates/Company-Policy.aspx
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Title,FileName,Id,PageLayoutType,Url
  Company Policy,Company-Policy.aspx,27,Article,SitePages/Templates/Company-Policy.aspx
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo page template list --webUrl "https://contoso.sharepoint.com/sites/team-a"

  Date: 5/4/2023

  ## template (12)

  Property | Value
  ---------|-------
  AbsoluteUrl | https://contoso.sharepoint.com/sites/team-a/SitePages/Templates/Company-Policy.aspx
  BannerImageUrl | https://contoso.sharepoint.com/\_layouts/15/images/sitepagethumbnail.png
  BannerThumbnailUrl | https://media.akamai.odsp.cdn.office.net/contoso.sharepoint.com/\_layouts/15/images/sitepagethumbnail.png
  CallToAction | 
  ContentTypeId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  DoesUserHaveEditPermission | true
  FileName | template.aspx
  FirstPublished | 0001-01-01T08:00:00Z
  Id | 12
  IsPageCheckedOutToCurrentUser | false
  IsWebWelcomePage | false
  Modified | 2023-05-04T09:37:10Z
  PageLayoutType | Article
  PromotedState | 0
  Title | template
  UniqueId | 318af790-8c04-4b34-b764-e47d6620bba2
  Url | SitePages/Templates/template.aspx
  Version | 0.1
  ```

  </TabItem>
</Tabs>
