-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp gateway get

Get information about the specified gateway

## Usage

```sh
m365 pp gateway get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: ID of the Gateway.
```

<Global />

## Examples

Get information about the specified gateway.

```sh
m365 pp gateway get --id 1f69e798-5852-4fdd-ab01-33bb14b6e934
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id":"22660b34-31b3-4744-a99c-5e154458a784",
    "gatewayId":0,
    "name":"Contoso Gateway",
    "type":"Resource",
    "publicKey":{
      "exponent":"AQAB",
      "modulus":"EXAMPLE_SECRET_VALUE_PLACEHOLDER+EXAMPLE_SECRET_VALUE_PLACEHOLDER+sH6MRf/+EXAMPLE_SECRET_VALUE_PLACEHOLDER/EXAMPLE_SECRET_VALUE_PLACEHOLDER+gwuE5bjnmjazFljQ5sOP0VdA0fRoId3+nI7n1rSgRq265jNHX84HZbm2D/Pk8C0dElTmYEswGPDWEJQ=="
    },
    "gatewayAnnotation":"{\"gatewayContactInformation\":[\"admin@contoso.onmicrosoft.com\"],\"gatewayVersion\":\"3000.122.8\",\"gatewayWitnessString\":\"{\\"EncryptedResult\\":\\"EXAMPLE_SECRET_VALUE_PLACEHOLDER/KTJXpw9/1SiyhpO+EXAMPLE_SECRET_VALUE_PLACEHOLDER+XGB/lQ==\\",\\"IV\\":\\"QxCYjHEl8Ab9i78ZBYpnDw==\\",\\"Signature\\":\\"EXAMPLE_SECRET_VALUE_PLACEHOLDER=\\"}\",\"gatewayMachine\":\"SPFxDevelop\",\"gatewaySalt\":\"rA1M34AdgdCbOYQMvo/izA==\",\"gatewayWitnessStringLegacy\":null,\"gatewaySaltLegacy\":null,\"gatewayDepartment\":null,\"gatewayVirtualNetworkSubnetId\":null}"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id  : 22660b34-31b3-4744-a99c-5e154458a784    
  name: Contoso Gateway 
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name
  22660b34-31b3-4744-a99c-5e154458a784,Contoso Gateway
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp gateway get --id 22660b34-31b3-4744-a99c-5e154458a784

  Date: 9/1/2023

  ## Contoso Gateway (22660b34-31b3-4744-a99c-5e154458a784)
  
  Property | Value
  ---------|-------
  id | 22660b34-31b3-4744-a99c-5e154458a784
  gatewayId | 0
  name | Contoso Gateway
  type | Resource
  ```

  </TabItem>
</Tabs>
