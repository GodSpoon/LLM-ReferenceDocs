-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitescript set

Updates existing site script

## Usage

```sh
m365 spo sitescript set [options]
```

## Options

```md definition-list
`-i, --id <id>`
: Site script ID.

`-t, --title [title]`
: Site script title.

`-d, --description [description]`
: Site script description.

`-v, --version [version]`
: Site script version.

`-c, --content [content]`
: JSON string containing the site script.
```

<Global />

## Remarks

If the specified `id` doesn't refer to an existing site script, you will get a `File not found` error.

## Examples

Update title of the existing site script with the specified ID.

```sh
m365 spo sitescript set --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a --title "Contoso"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Content": "{\"$schema\":\"https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json\",\"actions\":[{\"verb\":\"activateSPFeature\",\"name\":\"SiteNotebook feature\",\"title\":\"SiteNotebook feature\",\"featureId\":\"f151bb39-7c3b-414f-bb36-6bf18872052f\",\"scope\":\"web\"}],\"bindata\":{},\"version\":1}",
    "ContentByteArray": null,
    "Description": "Contoso site script",
    "Id": "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5",
    "IsSiteScriptPackage": false,
    "Title": "Contoso",
    "Version": 1
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Content            : {"$schema":"https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json","actions":[{"verb":"activateSPFeature","name":"SiteNotebook feature","title":"SiteNotebook feature","featureId":"f151bb39-7c3b-414f-bb36-6bf18872052f","scope":"web"}],"bindata":{},"version":1}
  ContentByteArray   : null
  Description        : Contoso site script
  Id                 : 43d4ffa0-c7ee-4a97-91d7-db27e5b62de5
  IsSiteScriptPackage: false
  Title              : Contoso
  Version            : 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Content,Description,Id,IsSiteScriptPackage,Title,Version
  "{""$schema"":""https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json"",""actions"":[{""verb"":""activateSPFeature"",""name"":""SiteNotebook feature"",""title"":""SiteNotebook feature"",""featureId"":""f151bb39-7c3b-414f-bb36-6bf18872052f"",""scope"":""web""}],""bindata"":{},""version"":1}",Contoso site script,43d4ffa0-c7ee-4a97-91d7-db27e5b62de5,,Contoso,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitescript set --id "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5" --title "Contoso"

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
