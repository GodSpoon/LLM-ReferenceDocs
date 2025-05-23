-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user license list

Lists the license details for a given user

## Usage

```sh
m365 entra user license list [options]
```

## Options

```md definition-list
`--userId [userId]`
: The ID of the user. Specify either `userId` or `userName` but not both.

`--userName [userName]`
: User principal name of the user. Specify either `userId` or `userName` but not both.
```

<Global />

## Remarks

:::tip

If you don't specify any option, the command will list the license details of the current logged in user. This does not work when using application permissions.

:::

## Examples

List license details of the current logged in user.

```sh
m365 entra user license list
```

List license details of a specific user by its UPN.

```sh
m365 entra user license list --userName john.doe@contoso.com
```

List license details of a specific user by its ID.

```sh
m365 entra user license list --userId 59f80e08-24b1-41f8-8586-16765fd830d3
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "skuId": "c42b9cae-ea4f-4ab7-9717-81576235ccac",
      "skuPartNumber": "DEVELOPERPACK_E5",
      "servicePlans": [
        {
          "servicePlanId": "7547a3fe-08ee-4ccb-b430-5077c5041653",
          "servicePlanName": "YAMMER_ENTERPRISE",
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
  id                                           skuId                                 skuPartNumber
  -------------------------------------------  ------------------------------------  -----------------------------------------
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  c42b9cae-ea4f-4ab7-9717-81576235ccac  DEVELOPERPACK_E5
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,skuId,skuPartNumber
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,c42b9cae-ea4f-4ab7-9717-81576235ccac,DEVELOPERPACK_E5
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user license list --userId "0c9c625f-faa9-4c3b-8cd8-d874b869f78c"

  Date: 2/19/2023

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  skuId | c42b9cae-ea4f-4ab7-9717-81576235ccac
  skuPartNumber | DEVELOPERPACK\_E5
  ```

  </TabItem>
</Tabs>
