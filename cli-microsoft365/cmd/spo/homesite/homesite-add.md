-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo homesite add

Adds a home site

## Usage

```sh
m365 spo homesite add [options]
```

## Options

```md definition-list
`-u, --url <url>`
: URL of the site to use as a home site.

`--isInDraftMode [isInDraftMode]`
: Specifies whether the home site is in draft mode. Accepts `true` or `false`. Default is `false`. 

`--vivaConnectionsDefaultStart [vivaConnectionsDefaultStart]`
: Specifies whether the home site is the default start for Viva Connections. Accepts `true` or `false`. Default is `true`.

`--audiences [audiences]`
: Comma-separated list of Microsoft Entra group IDs that will be used as audience.

`--order [order]`
: Order of the home site. Must be a positive integer.
```

<Global />

## Examples

Add a home site

```sh
m365 spo homesite add --url "https://contoso.sharepoint.com/sites/testcomms"
```

Add a home site with additional options

```sh
m365 spo homesite add --url "https://contoso.sharepoint.com/sites/testcomms" --isInDraftMode true --vivaConnectionsDefaultStart false --audiences "af8c0bc8-7b1b-44b4-b087-ffcc8df70d16,754ff15c-76b1-44cb-88c7-0065a4d3cfb7" --order 2 
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Audiences": [
      {
        "Email": "active@contoso.onmicrosoft.com",
        "Id": "7a1eea7f-9ab0-40ff-8f2e-0083d9d63451",
        "Title": "active Members"
      }
    ],
    "IsInDraftMode": true,
    "IsVivaBackendSite": false,
    "SiteId": "ca49054c-85f3-41eb-a290-46ffda8f219c",
    "TargetedLicenseType": 0,
    "Title": "testcommsite",
    "Url": "https://contoso.sharepoint.com/sites/testcomms",
    "VivaConnectionsDefaultStart": false,
    "WebId": "256c4f0f-e372-47b4-a891-b4888e829e20"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Audiences                  : [{"Email":"active@contoso.onmicrosoft.com","Id":"7a1eea7f-9ab0-40ff-8f2e-0083d9d63451","Title":"active Members"}]
  IsInDraftMode              : true
  IsVivaBackendSite          : false
  SiteId                     : ca49054c-85f3-41eb-a290-46ffda8f219c
  TargetedLicenseType        : 0
  Title                      : testcommsite
  Url                        : https://contoso.sharepoint.com/sites/testcomms
  VivaConnectionsDefaultStart: false
  WebId                      : 256c4f0f-e372-47b4-a891-b4888e829e20
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  IsInDraftMode,IsVivaBackendSite,SiteId,TargetedLicenseType,Title,Url,VivaConnectionsDefaultStart,WebId
  1,0,ca49054c-85f3-41eb-a290-46ffda8f219c,0,testcommsite,https://contoso.sharepoint.com/sites/testcomms,0,256c4f0f-e372-47b4-a891-b4888e829e20
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo homesite add --url "https://contoso.sharepoint.com/sites/testcomms"

  Date: 12/23/2024

  ## testcommsite (https://contoso.sharepoint.com/sites/testcomms)

  Property | Value
  ---------|-------
  IsInDraftMode | true
  IsVivaBackendSite | false
  SiteId | ca49054c-85f3-41eb-a290-46ffda8f219c
  TargetedLicenseType | 0
  Title | testcommsite
  Url | https://contoso.sharepoint.com/sites/testcomms
  VivaConnectionsDefaultStart | false
  WebId | 256c4f0f-e372-47b4-a891-b4888e829e20
  ```
  </TabItem>
</Tabs>

## More information

- SharePoint home sites [Viva Connections set up](https://learn.microsoft.com/en-us/viva/connections/set-up-admin-center)
