-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo web installedlanguage list

Lists all installed languages on site

## Usage

```sh
m365 spo web installedlanguage list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site for which to retrieve the list of installed languages
```

<Global />

## Examples

Return all installed languages from site _https://contoso.sharepoint.com/_

```sh
m365 spo web installedlanguage list --webUrl https://contoso.sharepoint.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [ 
    {
      "DisplayName": "English",
      "LanguageTag": "en-US",
      "Lcid": 1033
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  DisplayName                 LanguageTag  Lcid
  --------------------------  -----------  -----
  English                     en-US        1033
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  DisplayName,LanguageTag,Lcid
  English,en-US,1033
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo web installedlanguage list --webUrl "https://contoso.sharepoint.com"

  Date: 4/10/2023

  ## English

  Property | Value
  ---------|-------
  DisplayName | English
  LanguageTag | en-US
  Lcid | 1033   
  ```

  </TabItem>
</Tabs>
