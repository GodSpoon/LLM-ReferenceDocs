-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# booking business list

Lists all Microsoft Bookings businesses that are created for the tenant.

## Usage

```sh
m365 booking business list [options]
```

## Options

<Global />

## Examples

Returns a list of all Microsoft Bookings businesses that are created for the tenant.

```sh
m365 booking business list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "Accounting@contoso.onmicrosoft.com",
      "displayName": "Accounting"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id                                 displayName
  ---------------------------------  -----------
  Accounting@contoso.onmicrosoft.com  Accounting
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName
  Accounting@contoso.onmicrosoft.com,Accounting
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # booking business list

  Date: 5/29/2023

  ## Accounting (Accounting@contoso.onmicrosoft.com)

  Property | Value
  ---------|-------
  id | Accounting@contoso.onmicrosoft.com
  displayName | Accounting
  ```
  
  </TabItem>
</Tabs>
