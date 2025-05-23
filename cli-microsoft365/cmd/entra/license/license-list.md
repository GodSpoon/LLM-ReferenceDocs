-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra license list

Lists commercial subscriptions that an organization has acquired

## Usage

```sh
m365 entra license list [options]
```

## Options

<Global />

## Examples

List all licenses within the tenant.

```sh
m365 entra license list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "accountName": "contoso",
      "accountId": "a9b44919-790b-4843-9b45-1923b8c3d61f",
      "appliesTo": "User",
      "capabilityStatus": "Enabled",
      "consumedUnits": 1,
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "skuId": "c7df2760-2c81-4ef7-b578-5b5392b571df",
      "skuPartNumber": "ENTERPRISEPREMIUM",      
      "subscriptionIds": [
        "b079cd48-7a9e-4d8b-af82-60f3adefe53b"
      ],
      "prepaidUnits": {
        "enabled": 10000,
        "suspended": 0,
        "warning": 0,
        "lockedOut": 0
      },
      "servicePlans": [
        {
          "servicePlanId": "8c098270-9dd4-4350-9b30-ba4703f3b36b",
          "servicePlanName": "ADALLOM_S_O365",
          "provisioningStatus": "Success",
          "appliesTo": "User"
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                                                         skuId                                 skuPartNumber
  -------------------------------------------------------------------------  ------------------------------------  ----------------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  c7df2760-2c81-4ef7-b578-5b5392b571df  ENTERPRISEPREMIUM
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  accountName,accountId,appliesTo,capabilityStatus,consumedUnits,id,skuId,skuPartNumber
  contoso,a9b44919-790b-4843-9b45-1923b8c3d61f,User,Enabled,1,EXAMPLE_SECRET_VALUE_PLACEHOLDER,c7df2760-2c81-4ef7-b578-5b5392b571df,ENTERPRISEPREMIUM
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra license list

  Date: 14/2/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  accountName | contoso
  accountId | a9b44919-790b-4843-9b45-1923b8c3d61f
  appliesTo | User
  capabilityStatus | Enabled
  consumedUnits | 1
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  skuId | c7df2760-2c81-4ef7-b578-5b5392b571df
  skuPartNumber | ENTERPRISEPREMIUM
  ```

  </TabItem>
</Tabs>
