-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# teams funsettings list

Lists fun settings for the specified Microsoft Teams team

## Usage

```sh
m365 teams funsettings list [options]
```

## Options

```md definition-list
`-i, --teamId <teamId>`
: The ID of the team for which to list fun settings
```

<Global />

## Examples

List fun settings of a Microsoft Teams team

```sh
m365 teams funsettings list --teamId 83cece1e-938d-44a1-8b86-918cf6151957
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "allowGiphy": true,
    "giphyContentRating": "moderate",
    "allowStickersAndMemes": true,
    "allowCustomMemes": true
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  allowCustomMemes     : true
  allowGiphy           : true
  allowStickersAndMemes: true
  giphyContentRating   : moderate
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  allowGiphy,giphyContentRating,allowStickersAndMemes,allowCustomMemes
  1,moderate,1,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # teams funsettings list --teamId "83cece1e-938d-44a1-8b86-918cf6151957"

  Date: 5/7/2023

  Property | Value
  ---------|-------
  allowGiphy | true
  giphyContentRating | moderate
  allowStickersAndMemes | true
  allowCustomMemes | true
  ```

  </TabItem>
</Tabs>
