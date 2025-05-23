-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitescript list

Lists site script available for use with site designs

## Usage

```sh
m365 spo sitescript list [options]
```

## Options

<Global />

## Examples

List all site scripts available for use with site designs

```sh
m365 spo sitescript list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Content": null,
      "ContentByteArray": null,
      "Description": "Contoso site script",
      "Id": "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5",
      "IsSiteScriptPackage": false,
      "Title": "Contoso",
      "Version": 1
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Content  ContentByteArray  Description                Id                                    IsSiteScriptPackage  Title                Version
  -------  ----------------  -------------------------  ------------------------------------  -------------------  -------------------  -------
  null     null              Contoso site script        43d4ffa0-c7ee-4a97-91d7-db27e5b62de5  false                Contoso               1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,IsSiteScriptPackage,Title,Version
  43d4ffa0-c7ee-4a97-91d7-db27e5b62de5,,Contoso,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitescript list

  Date: 2023-06-22

  ## Contoso (43d4ffa0-c7ee-4a97-91d7-db27e5b62de5)

  Property | Value
  ---------|-------
  Description | Contoso site script
  Id | 43d4ffa0-c7ee-4a97-91d7-db27e5b62de5
  IsSiteScriptPackage | false
  Title | Contoso
  Version | 1
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
