-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook roomlist list

Get a collection of available roomlists

## Usage

```sh
m365 outlook roomlist list [options]
```

## Options

<Global />

## Examples

Get all roomlists in your tenant.

```sh
m365 outlook roomlist list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "5502bfbd-83f0-4b31-aa8c-5aebeda06091",
      "emailAddress": "RoomsBuilding1@contoso.com",
      "displayName": "Rooms building 1",
      "geoCoordinates": null,
      "phone": "",
      "address": {
        "street": "Microsoft Way 1",
        "city": "Redmond",
        "state": "Washington",
        "countryOrRegion": "US",
        "postalCode": "98053"
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  displayName : Rooms building 1
  emailAddress: RoomsBuilding1@contoso.com
  id          : 5502bfbd-83f0-4b31-aa8c-5aebeda06091
  phone       :
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,phone,emailAddress
  5502bfbd-83f0-4b31-aa8c-5aebeda06091,Rooms building 1,,RoomsBuilding1@contoso.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook roomlist list

  Date: 27/1/2023

  ## Rooms building 1 (5502bfbd-83f0-4b31-aa8c-5aebeda06091)

  Property | Value
  ---------|-------
  id | 5502bfbd-83f0-4b31-aa8c-5aebeda06091
  emailAddress | RoomsBuilding1@contoso.com
  displayName | Rooms building 1
  geoCoordinates | null
  phone |
  ```

  </TabItem>
</Tabs>
