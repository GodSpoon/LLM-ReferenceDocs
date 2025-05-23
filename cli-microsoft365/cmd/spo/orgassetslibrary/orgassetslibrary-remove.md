-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo orgassetslibrary remove

Removes a library that was designated as a central location for organization assets across the tenant.

## Usage

```sh
m365 spo orgassetslibrary remove [options]
```

## Options

```md definition-list
`--libraryUrl <libraryUrl>`
: The server relative URL of the library to be removed as a central location for organization assets.

`-f, --force`
: Don't prompt for confirming removing the organization asset library.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Removes organization assets library without prompting for confirmation

```sh
m365 spo orgassetslibrary remove --libraryUrl "/sites/branding/assets" --force
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "IsNull": false
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  IsNull: false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  IsNull
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo orgassetslibrary remove --libraryUrl "https://contoso.sharepoint.com/sites/branding/SiteAssets" --force

  Date: 5/1/2023

  Property | Value
  ---------|-------
  IsNull | false
  ```

  </TabItem>
</Tabs>
