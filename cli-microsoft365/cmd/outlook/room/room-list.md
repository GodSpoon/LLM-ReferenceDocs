-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# outlook room list

Get a collection of all available rooms

## Usage

```sh
m365 outlook room list [options]
```

## Options

```md definition-list
`--roomlistEmail [roomlistEmail]`
: Use to filter returned rooms by their roomlist email (eg. bldg2@contoso.com).
```

<Global />

## Examples

Get all the rooms.

```sh
m365 outlook room list
```

Get all the rooms of specified roomlist e-mail address.

```sh
m365 outlook room list --roomlistEmail "bldg2@contoso.com"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "98c40767-158a-44f0-9dda-c95b86f079ca",
      "emailAddress": "Largeroom@contoso.com",
      "displayName": "Large room",
      "geoCoordinates": null,
      "phone": "",
      "nickname": "Large room",
      "building": null,
      "floorNumber": null,
      "floorLabel": null,
      "label": null,
      "capacity": 25,
      "bookingType": "standard",
      "audioDeviceName": null,
      "videoDeviceName": null,
      "displayDeviceName": null,
      "isWheelChairAccessible": false,
      "tags": [],
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
  id                                    displayName  phone  emailAddress
  ------------------------------------  -----------  -----  ---------------------
  98c40767-158a-44f0-9dda-c95b86f079ca  Large room          Largeroom@contoso.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,displayName,phone,emailAddress
  98c40767-158a-44f0-9dda-c95b86f079ca,Large room,,Largeroom@contoso.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # outlook room list

  Date: 27/1/2023

  ## Large room (98c40767-158a-44f0-9dda-c95b86f079ca)

  Property | Value
  ---------|-------
  id | 98c40767-158a-44f0-9dda-c95b86f079ca
  emailAddress | Largeroom@VanRoeyBeSPDev.onmicrosoft.com
  displayName | Large room
  geoCoordinates | null
  phone |
  nickname | Large room
  building | null
  floorNumber | null
  floorLabel | null
  label | null
  capacity | 25
  bookingType | standard
  audioDeviceName | null
  videoDeviceName | null
  displayDeviceName | null
  isWheelChairAccessible | false
  ```

  </TabItem>
</Tabs>
