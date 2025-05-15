<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage group list

Returns the list of groups in a Viva Engage network or the groups for a specific user

## Usage

```sh
m365 viva engage group list [options]
```

## Options

```md definition-list
`--userId [userId]`
: Returns the groups for a specific user

`--limit [limit]`
: Limits the groups returned
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

## Examples

Returns all Viva Engage network groups

```sh
m365 viva engage group list
```

Returns all Viva Engage network groups for the user with the ID `5611239081`

```sh
m365 viva engage group list --userId 5611239081
```

Returns the first 10 Viva Engage network groups

```sh
m365 viva engage group list --limit 10
```

Returns the first 10 Viva Engage network groups for the user with the ID `5611239081`

```sh
m365 viva engage group list --userId 5611239081 --limit 10
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "type": "group",
      "id": 31158067201,
      "email": "",
      "full_name": "Contoso Hub",
      "network_id": 5897756673,
      "name": "contosohub",
      "description": "",
      "privacy": "public",
      "url": "https://www.yammer.com/api/v1/groups/31158067201",
      "web_url": "https://www.yammer.com/contoso.onmicrosoft.com/#/threads/inGroup?type=in_group&feedId=31158067201",
      "mugshot_url": "https://mugshot0eu-1.assets-yammer.com/mugshot/images/group_profile.png?P1=1668205176&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size=48x48",
      "mugshot_redirect_url": "https://www.yammer.com/mugshot/images/redirect/48x48/group_profile.png",
      "mugshot_url_template": "https://mugshot0eu-1.assets-yammer.com/mugshot/images/group_profile.png?P1=1668205176&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size={width}x{height}",
      "mugshot_redirect_url_template": "https://www.yammer.com/mugshot/images/redirect/{width}x{height}/group_profile.png",
      "mugshot_id": null,
      "show_in_directory": "true",
      "created_at": "2022/11/11 20:54:52 +0000",
      "aad_guests": 0,
      "color": "#2c5b85",
      "external": false,
      "moderated": false,
      "header_image_url": "https://mugshot0eu-1.assets-yammer.com/mugshot/images/group-header-coffee.png?P1=1668204451&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "category": "unclassified",
      "default_thread_starter_type": "normal",
      "restricted_posting": false,
      "company_group": false,
      "creator_type": "user",
      "creator_id": 36425097217,
      "state": "active",
      "stats": {
        "members": 1,
        "aad_guests": 0,
        "updates": 0,
        "last_message_id": null,
        "last_message_at": null
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  email    :
  external : false
  id       : 31158067201
  moderated: false
  name     : contosohub
  privacy  : public
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name,email,privacy,external,moderated
  31158067201,wombathub,,public,false,false
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage group list --limit "1"

  Date: 2023-05-16

  ## leadership (123412865024)

  Property | Value
  ---------|-------
  type | group
  id | 123412865024
  email | leadership+contoso.onmicrosoft.com@yammer.com
  full\_name | Leadership
  network\_id | 98327945216
  name | leadership
  description | Share what's on your mind and get important announcements from Patti and the rest of the Leadership Team.
  privacy | public
  url | https://www.yammer.com/api/v1/groups/123412865024
  web\_url | https://www.yammer.com/contoso.onmicrosoft.com/#/threads/inGroup?type=in\_group&feedId=123412865024
  mugshot\_url | https://mugshot0.assets-yammer.com/mugshot/images/5jjCjcSTJsdzFn0Ps50Vz0tqNdWdgnWs?P1=1684267104&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER\_5ZOWefd8l537cWNUOPzeDg2lzXAMPLE_SECRET_VALUE_PLACEHOLDERXAMPLE_SECRET_VALUE_PLACEHOLDER\_r1IC24Sb-PLaSfAtKJZsswBBTkmzXAMPLE_SECRET_VALUE_PLACEHOLDER\_xUHWc54TrUIjFxnrwMDGZvzw&size=48x48
  mugshot\_redirect\_url | https://www.yammer.com/mugshot/images/redirect/48x48/5jjCjcSTJsdzFn0Ps50Vz0tqNdWdgnWs
  mugshot\_url\_template | https://mugshot0.assets-yammer.com/mugshot/images/5jjCjcSTJsdzFn0Ps50Vz0tqNdWdgnWs?P1=1684267104&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER\_5ZOWefd8l537cWNUOPzeDg2lzXAMPLE_SECRET_VALUE_PLACEHOLDERXAMPLE_SECRET_VALUE_PLACEHOLDER\_r1IC24Sb-PLaSfAtKJZsswBBTkmzXAMPLE_SECRET_VALUE_PLACEHOLDER\_xUHWc54TrUIjFxnrwMDGZvzw&size={width}x{height}
  mugshot\_redirect\_url\_template | https://www.yammer.com/mugshot/images/redirect/{width}x{height}/5jjCjcSTJsdzFn0Ps50Vz0tqNdWdgnWs
  mugshot\_id | 5jjCjcSTJsdzFn0Ps50Vz0tqNdWdgnWs
  show\_in\_directory | true
  created\_at | 2022/12/12 12:51:11 +0000
  aad\_guests | 0
  color | #0e4f7a
  external | false
  moderated | false
  header\_image\_url | https://mugshot0.assets-yammer.com/mugshot/images/group-header-megaphone.png?P1=1684266783&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDERXAMPLE_SECRET_VALUE_PLACEHOLDER\_wSRX\_fn6cP47uoC4wvSsGAmWeb6epr-hJpDWXAMPLE_SECRET_VALUE_PLACEHOLDER
  category | unclassified
  default\_thread\_starter\_type | normal
  restricted\_posting | false
  company\_group | false
  creator\_type | user
  creator\_id | 1842176974848
  state | active
  ```

  </TabItem>
</Tabs>
