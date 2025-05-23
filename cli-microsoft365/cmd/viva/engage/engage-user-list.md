-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage user list

Returns users from the current network

## Usage

```sh
m365 viva engage user list [options]
```

## Options

```md definition-list
`-g, --groupId [groupId]`
: Returns users within a given group

`-l, --letter [letter]`
: Returns users with usernames beginning with the given character

`--reverse`
: Returns users in reverse sorting order

`--limit [limit]`
: Limits the users returned

`--sortBy [sortBy]`
: Returns users sorted by a number of messages or followers, instead of the default behavior of sorting alphabetically. Allowed values are `messages,followers`
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

## Examples
  
Returns all Viva Engage network users

```sh
m365 viva engage user list
```

Returns all Viva Engage network users with usernames beginning with "a"

```sh
m365 viva engage user list --letter a
```

Returns all Viva Engage network users sorted alphabetically in descending order

```sh
m365 viva engage user list --reverse
```

Returns the first 10 Viva Engage network users within the group 5785177

```sh
m365 user list --groupId 5785177 --limit 10
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "type": "user",
      "id": 172006440961,
      "network_id": 5897756673,
      "state": "active",
      "job_title": "",
      "location": null,
      "interests": null,
      "summary": null,
      "expertise": null,
      "full_name": "John Doe",
      "activated_at": "2021/10/08 11:45:32 +0000",
      "auto_activated": false,
      "show_ask_for_photo": true,
      "first_name": "",
      "last_name": "",
      "network_name": "Contoso",
      "network_domains": [
        "contoso.onmicrosoft.com"
      ],
      "url": "https://www.yammer.com/api/v1/users/172006440961",
      "web_url": "https://www.yammer.com/contoso.onmicrosoft.com/users/172006440961",
      "name": "johndoe",
      "mugshot_url": "https://mugshot0eu-1.assets-yammer.com/mugshot/images/no_photo.png?P1=1668205841&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size=48x48",
      "mugshot_redirect_url": "https://www.yammer.com/mugshot/images/redirect/48x48/no_photo.png",
      "mugshot_url_template": "https://mugshot0eu-1.assets-yammer.com/mugshot/images/no_photo.png?P1=1668205841&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size={width}x{height}",
      "mugshot_redirect_url_template": "https://www.yammer.com/mugshot/images/redirect/{width}x{height}/no_photo.png",
      "birth_date": "",
      "birth_date_complete": "",
      "timezone": "Pacific Time (US & Canada)",
      "external_urls": [],
      "admin": "true",
      "verified_admin": "true",
      "m365_yammer_admin": "false",
      "supervisor_admin": "false",
      "o365_tenant_admin": "true",
      "can_broadcast": "true",
      "department": null,
      "email": "johndoe@contoso.onmicrosoft.com",
      "guest": false,
      "aad_guest": false,
      "can_view_delegations": false,
      "can_create_new_network": false,
      "can_browse_external_networks": false,
      "reaction_accent_color": "none",
      "significant_other": "",
      "kids_names": "",
      "previous_companies": [],
      "schools": [],
      "contact": {
        "im": {
          "provider": "",
          "username": ""
        },
        "phone_numbers": [],
        "email_addresses": [
          {
            "type": "primary",
            "address": "johndoe@contoso.onmicrosoft.com"
          }
        ],
        "has_fake_email": false
      },
      "stats": {
        "updates": 0,
        "following": 0,
        "followers": 0
      },
      "settings": {
        "xdr_proxy": ""
      },
      "show_invite_lightbox": false
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id            full_name         email
  ------------  ----------------  -------------------------------
  36425097217   John Doe          johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,full_name,email
  36425097217,John Doe,johndoe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage user list --limit "1"

  Date: 2023-05-16

  ## john (172006440961)

  Property | Value
  ---------|-------
  type | user
  id | 172006440961
  network\_id | 98327945216
  state | active
  job\_title | Retail Manager
  location | 18/2111
  summary |
  full\_name | john doe
  activated\_at | 2022/12/12 12:49:34 +0000
  auto\_activated | false
  show\_ask\_for\_photo | false
  first\_name | john
  last\_name | doe
  network\_name | Contoso
  url | https://www.yammer.com/api/v1/users/172006440961
  web\_url | https://www.yammer.com/contoso.onmicrosoft.com/users/172006440961
  name | john
  mugshot\_url | https://mugshot0.assets-yammer.com/mugshot/images/jm2p4dHNWgVr1Q1C5jbGvcmWqVM5W9Zj?P1=1684269325&P2=104&P3=1&P4=I\_DbxkwAcCq1cmFgxWINlSF3VQH9EqvZBvoYtO\EXAMPLE_SECRET_VALUE_PLACEHOLDER\_l0MyMUGAL2tcSHRy\_j0IvfrP3i4jkColZbiYmng\_4QseJC5y1G9fFn7mpPt2LN7-Qew\_ybxWJXEh6ABLAoCm9\_PmV7TuUt4M\_s-pKDZkQA6\EXAMPLE_SECRET_VALUE_PLACEHOLDER\_4\_T\_Ncp5OfYXGQXmZt3L5OhAlk2SpoYhdBYtQ&size=48x48
  mugshot\_redirect\_url | https://www.yammer.com/mugshot/images/redirect/48x48/jm2p4dHNWgVr1Q1C5jbGvcmWqVM5W9Zj
  mugshot\_url\_template | https://mugshot0.assets-yammer.com/mugshot/images/jm2p4dHNWgVr1Q1C5jbGvcmWqVM5W9Zj?P1=1684269325&P2=104&P3=1&P4=I\_DbxkwAcCq1cmFgxWINlSF3VQH9EqvZBvoYtO\EXAMPLE_SECRET_VALUE_PLACEHOLDER\_l0MyMUGAL2tcSHRy\_j0IvfrP3i4jkColZbiYmng\_4QseJC5y1G9fFn7mpPt2LN7-Qew\_ybxWJXEh6ABLAoCm9\_PmV7TuUt4M\_s-pKDZkQA6\EXAMPLE_SECRET_VALUE_PLACEHOLDER\_4\_T\_Ncp5OfYXGQXmZt3L5OhAlk2SpoYhdBYtQ&size={width}x{height}
  mugshot\_redirect\_url\_template | https://www.yammer.com/mugshot/images/redirect/{width}x{height}/jm2p4dHNWgVr1Q1C5jbGvcmWqVM5W9Zj
  birth\_date |
  birth\_date\_complete |
  timezone | Pacific Time (US & Canada)
  admin | false
  verified\_admin | false
  m365\_yammer\_admin | false
  supervisor\_admin | false
  o365\_tenant\_admin | false
  answers\_admin | false
  corporate\_communicator | false
  can\_broadcast | false
  email | johndoe@contoso.onmicrosoft.com
  guest | false
  aad\_guest | false
  can\_view\_delegations | false
  can\_create\_new\_network | true
  can\_browse\_external\_networks | true
  reaction\_accent\_color | none
  significant\_other |
  kids\_names |
  show\_invite\_lightbox | false
  ```

  </TabItem>
</Tabs>
