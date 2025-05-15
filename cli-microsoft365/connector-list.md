<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pa connector list

Lists custom connectors in the given environment

## Usage

```sh
m365 pa connector list [options]
```

## Alias

```sh
m365 flow connector list
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment for which to retrieve custom connectors.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

List all custom connectors in the given environment.

```sh
m365 pa connector list --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "name":"EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "id":"/providers/Microsoft.PowerApps/apis/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "type":"Microsoft.PowerApps/apis",
      "properties":{
        "displayName":"My connector",
        "iconUri":"https://az787822.vo.msecnd.net/defaulticons/api-dedicated.png",
        "iconBrandColor":"#007ee5",
        "contact":{},
        "license":{},
        "apiEnvironment":"Shared",
        "isCustomApi":true,
        "connectionParameters":{},
        "runtimeUrls":[
          "https://europe-002.azure-apim.net/apim/EXAMPLE_SECRET_VALUE_PLACEHOLDER"
        ],
        "primaryRuntimeUrl":"https://europe-002.azure-apim.net/apim/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "metadata":{
          "source":"powerapps-user-defined",
          "brandColor":"#007ee5",
          "contact":{},
          "license":{},
          "publisherUrl":null,
          "serviceUrl":null,
          "documentationUrl":null,
          "environmentName":"EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "xrmConnectorId":null,
          "almMode":"Environment",
          "createdBy":"{\"id\":\"03043611-d01e-4e58-9fbe-1a18ecb861d8\",\"displayName\":\"MOD Administrator\",\"email\":\"admin@contoso.OnMicrosoft.com\",\"type\":\"User\",\"tenantId\":\"0d645e38-ec52-4a4f-ac58-65f2ac4015f6\",\"userPrincipalName\":\"admin@contoso.onmicrosoft.com\"}",
          "modifiedBy":"{\"id\":\"03043611-d01e-4e58-9fbe-1a18ecb861d8\",\"displayName\":\"MOD Administrator\",\"email\":\"admin@contoso.OnMicrosoft.com\",\"type\":\"User\",\"tenantId\":\"0d645e38-ec52-4a4f-ac58-65f2ac4015f6\",\"userPrincipalName\":\"admin@contoso.onmicrosoft.com\"}",
          "allowSharing":false
        },
        "capabilities":[],
        "description":"",
        "apiDefinitions":{
          "originalSwaggerUrl":"https://paeu2weu8.blob.core.windows.net/api-swagger-files/EXAMPLE_SECRET_VALUE_PLACEHOLDER?sv=2018-03-28&sr=b&sig=EXAMPLE_SECRET_VALUE_PLACEHOLDER%3D&se=2019-12-05T19%3A53%3A49Z&sp=r",
          "modifiedSwaggerUrl":"https://paeu2weu8.blob.core.windows.net/api-swagger-files/EXAMPLE_SECRET_VALUE_PLACEHOLDER?sv=2018-03-28&sr=b&sig=rkpKHP8K%2F2yNBIUQcVN%2B0ZPjnP9sECrM%2FfoZMG%2BJZX0%3D&se=2019-12-05T19%3A53%3A49Z&sp=r"
        },
        "createdBy":{
          "id":"03043611-d01e-4e58-9fbe-1a18ecb861d8",
          "displayName":"MOD Administrator",
          "email":"admin@contoso.OnMicrosoft.com",
          "type":"User",
          "tenantId":"0d645e38-ec52-4a4f-ac58-65f2ac4015f6",
          "userPrincipalName":"admin@contoso.onmicrosoft.com"
        },
        "modifiedBy":{
          "id":"03043611-d01e-4e58-9fbe-1a18ecb861d8",
          "displayName":"MOD Administrator",
          "email":"admin@contoso.OnMicrosoft.com",
          "type":"User",
          "tenantId":"0d645e38-ec52-4a4f-ac58-65f2ac4015f6",
          "userPrincipalName":"admin@contoso.onmicrosoft.com"
        },
        "createdTime":"2019-12-05T18:45:03.4615313Z",
        "changedTime":"2019-12-05T18:45:03.4615313Z",
        "environment":{
          "id":"/providers/Microsoft.PowerApps/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
          "name":"EXAMPLE_SECRET_VALUE_PLACEHOLDER"
        },
        "tier":"Standard",
        "publisher":"MOD Administrator",
        "almMode":"Environment"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  name                                                        displayName
  ----------------------------------------------------------- ------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER My connector
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,displayName
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,My connector
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pa connector list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  ## My connector (/providers/Microsoft.PowerApps/apis/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

  Property | Value
  ---------|-------
  name | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  id | /providers/Microsoft.PowerApps/apis/EXAMPLE_SECRET_VALUE_PLACEHOLDER
  type | Microsoft.PowerApps/apis
  ```

  </TabItem>
</Tabs>
