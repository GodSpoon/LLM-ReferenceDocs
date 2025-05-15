<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp gateway list

Returns a list of gateways for which the user is an admin

## Usage

```sh
m365 pp gateway list [options]
```

## Options

<Global />

## Examples

List gateways for which the user is an admin.

```sh
m365 pp gateway list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
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
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                   name
  ------------------------------------ ---------------
  22660b34-31b3-4744-a99c-5e154458a784 Contoso Gateway
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
  # pp gateway list

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
