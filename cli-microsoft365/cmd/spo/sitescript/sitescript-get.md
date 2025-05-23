-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo sitescript get

Gets information about the specified site script

## Usage

```sh
m365 spo sitescript get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: Site script ID.

`-c, --content`
: Specify to only retrieve the content of the site script.
```

<Global />

## Remarks

If the specified `id` doesn't refer to an existing site script, you will get a `File not found` error.

## Examples

Get information about the site script with the specified ID.

```sh
m365 spo sitescript get --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a
```

Returns the site script contents:

```sh
m365 spo sitescript get --id 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a --content
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "Content": { 
      "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
      "actions": [ 
        {
          "verb":"activateSPFeature",
          "name": "SiteNotebook feature", 
          "title": "SiteNotebook feature",
          "featureId": "f151bb39-7c3b-414f-bb36-6bf18872052f", 
          "scope": "web"
        }
      ], 
      "bindata":{},
      "version":1
    },
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
  Content,Id,IsSiteScriptPackage,Title,Version
  "{""$schema"":""https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json"",""actions"":[{""verb"":""activateSPFeature"",""name"":""SiteNotebook feature"",""title"":""SiteNotebook feature"",""featureId"":""f151bb39-7c3b-414f-bb36-6bf18872052f"",""scope"":""web""}],""bindata"":{},""version"":1}",43d4ffa0-c7ee-4a97-91d7-db27e5b62de5,false,Contoso,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitescript get --id "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5"

  Date: 2023-06-22

  ## Contoso (43d4ffa0-c7ee-4a97-91d7-db27e5b62de5)

  Property | Value
  ---------|-------
  Content | {"$schema":"https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json","actions":[{"verb":"activateSPFeature","name":"SiteNotebook feature","title":"SiteNotebook feature","featureId":"f151bb39-7c3b-414f-bb36-6bf18872052f","scope":"web"}],"bindata":{},"version":1}
  Description | Contoso site script
  Id | 43d4ffa0-c7ee-4a97-91d7-db27e5b62de5
  IsSiteScriptPackage | false
  Title | Contoso
  Version | 1
  ```

  </TabItem>
</Tabs>

### `content` response

When we make use of the option `content` the response will differ.

<Tabs>
  <TabItem value="JSON">

  ```json
  { 
    "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
    "actions": [ 
      {
        "verb":"activateSPFeature",
        "name": "SiteNotebook feature", 
        "title": "SiteNotebook feature",
        "featureId": "f151bb39-7c3b-414f-bb36-6bf18872052f", 
        "scope": "web"
      }
    ], 
    "bindata":{},
    "version":1
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  $schema            : https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json
  actions            : [{"verb":"createSPList","listName":"Customer Tracking","templateType":100,"subactions":[{"verb":"setDescription","description":"List of Customers and Orders"},{"verb":"addSPField","fieldType":"Text","displayName":"Customer Name","isRequired":false,"addToDefaultView":true},{"verb":"addSPField","fieldType":"Number","displayName":"Requisition Total","addToDefaultView":true,"isRequired":true},{"verb":"addSPField","fieldType":"User","displayName":"Contact","addToDefaultView":true,"isRequired":true},{"verb":"addSPField","fieldType":"Note","displayName":"Meeting Notes","isRequired":false}]}]
  version            : 1
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  $schema,version
  https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json,1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo sitescript get --id "43d4ffa0-c7ee-4a97-91d7-db27e5b62de5" --content "true"

  Date: 2023-06-22

  Property | Value
  ---------|-------
  $schema | https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json
  version | 1
  ```

  </TabItem>
</Tabs>

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
