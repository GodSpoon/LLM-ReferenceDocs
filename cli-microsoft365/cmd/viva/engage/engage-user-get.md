-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage user get

Retrieves the current user or searches for a user by ID or e-mail

## Usage

```sh
m365 viva engage user get [options]
```

## Options

```md definition-list
`-i, --id [id]`
: Retrieve a user by ID

`--email [email]`
: Retrieve a user by e-mail
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

All operations return a single user object. Operations executed with the `email` parameter return an array of user objects.

## Examples
  
Returns the current user

```sh
m365 viva engage user get
```

Returns the user with the ID 1496550697

```sh
m365 viva engage user get --id 1496550697
```

Returns an array of users matching the e-mail

```sh
m365 viva engage user get --email john.smith@contoso.com
```

Returns an array of users matching the e-mail in JSON. The JSON output returns a full user object

```sh
m365 viva engage user get --email john.smith@contoso.com --output json
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
    "full_name": "johndoe",
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
    "name": "admvalo",
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
    "show_invite_lightbox": false,
    "age_bucket": "notSet"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  type                     : user
  id                       : 172006440961
  network_id               : 5897756673
  state                    : active
  job_title                : 
  location                 : null
  interests                : null
  summary                  : null
  expertise                : null
  full_name                : johndoe
  activated_at             : 2021/10/08 11:45:32 +0000
  auto_activated           : false
  show_ask_for_photo       : true
  first_name               : 
  last_name                : 
  network_name             : Contoso
  network_domains          : [contoso.onmicrosoft.com]
  url                      : https://www.yammer.com/api/v1/users/172006440961
  web_url                  : https://www.yammer.com/contoso.onmicrosoft.com/users/172006440961
  name                     : admvalo
  mugshot_url              : https://mugshot0eu-1.assets-yammer.com/mugshot/images/no_photo.png?P1=1668205841&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size=48x48
  mugshot_redirect_url     : https://www.yammer.com/mugshot/images/redirect/48x48/no_photo.png
  mugshot_url_template     : https://mugshot0eu-1.assets-yammer.com/mugshot/images/no_photo.png?P1=1668205841&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size={width}x{height}
  mugshot_redirect_url_template: https://www.yammer.com/mugshot/images/redirect/{width}x{height}/no_photo.png
  birth_date               : 
  birth_date_complete      : 
  timezone                 : Pacific Time (US & Canada)
  external_urls            : []
  admin                    : true
  verified_admin           : true
  m365_yammer_admin        : false
  supervisor_admin         : false
  o365_tenant_admin        : true
  can_broadcast            : true
  department               : null
  email                    : johndoe@contoso.onmicrosoft.com
  guest                    : false
  aad_guest                : false
  can_view_delegations     : false
  can_create_new_network   : false
  can_browse_external_networks: false
  reaction_accent_color    : none
  significant_other        : 
  kids_names               : 
  previous_companies       : []
  schools                  : []
  show_invite_lightbox     : false
  age_bucket               : notSet
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  type,id,network_id,state,job_title,location,interests,summary,expertise,full_name,activated_at,auto_activated,show_ask_for_photo,first_name,last_name,network_name,network_domains,url,web_url,name,mugshot_url,mugshot_redirect_url,mugshot_url_template,mugshot_redirect_url_template,birth_date,birth_date_complete,timezone,external_urls,admin,verified_admin,m365_yammer_admin,supervisor_admin,o365_tenant_admin,can_broadcast,department,email,guest,aad_guest,can_view_delegations,can_create_new_network,can_browse_external_networks,reaction_accent_color,significant_other,kids_names,previous_companies,schools,show_invite_lightbox,age_bucket
  user,172006440961,5897756673,active,,,null,null,null,johndoe,"2021/10/08 11:45:32 +0000",false,true,,,Contoso,"[contoso.onmicrosoft.com]","https://www.yammer.com/api/v1/users/172006440961","https://www.yammer.com/contoso.onmicrosoft.com/users/172006440961",admvalo,"https://mugshot0eu-1.assets-yammer.com/mugshot/images/no_photo.png?P1=1668205841&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size=48x48","https://www.yammer.com/mugshot/images/redirect/48x48/no_photo.png","https://mugshot0eu-1.assets-yammer.com/mugshot/images/no_photo.png?P1=1668205841&P2=104&P3=1&P4=EXAMPLE_SECRET_VALUE_PLACEHOLDER&size={width}x{height}","https://www.yammer.com/mugshot/images/redirect/{width}x{height}/no_photo.png",,"",Pacific Time (US & Canada),[],true,true,false,false,true,true,null,johndoe@contoso.onmicrosoft.com,false,false,false,false,false,none,,,[],[],false,notSet
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage user get --email "johndoe@contoso.onmicrosoft.com"

  Date: 2023-05-16

  ## john (172006440961)

  Property | Value
  ---------|-------
  type | user
  id | 172006440961
  network\_id | 98327945216
  state | active
  job\_title |
  location |
  summary |
  full\_name | john doe
  activated\_at | 2022/12/12 12:48:58 +0000
  auto\_activated | false
  show\_ask\_for\_photo | false
  first\_name | john
  last\_name | doe
  network\_name | Contoso
  url | https://www.yammer.com/api/v1/users/172006440961
  web\_url | https://www.yammer.com/contoso.onmicrosoft.com/users/172006440961
  name | john
  mugshot\_url | https://mugshot0.assets-yammer.com/mugshot/images/j3vWbMtXbkp952gqLQlDqKj8s3Fw42Xc\_5306d18a-4133-48a7-b568-a47af1bab178?P1=1684269373&P2=104&P3=1&P4=fnQKCoHkdFGwue-NUtuMDHzqeFOZF0\_4qq0S0-H58C-98YH7QMJ51UBeJTbQduTeM5\EXAMPLE_SECRET_VALUE_PLACEHOLDER-\_CcptsxiOp1tP1jxZbE5x79STjUKaA&size=48x48
  mugshot\_redirect\_url | https://www.yammer.com/mugshot/images/redirect/48x48/j3vWbMtXbkp952gqLQlDqKj8s3Fw42Xc\_5306d18a-4133-48a7-b568-a47af1bab178
  mugshot\_url\_template | https://mugshot0.assets-yammer.com/mugshot/images/j3vWbMtXbkp952gqLQlDqKj8s3Fw42Xc\_5306d18a-4133-48a7-b568-a47af1bab178?P1=1684269373&P2=104&P3=1&P4=fnQKCoHkdFGwue-NUtuMDHzqeFOZF0\_4qq0S0-H58C-98YH7QMJ51UBeJTbQduTeM5\EXAMPLE_SECRET_VALUE_PLACEHOLDER-\_CcptsxiOp1tP1jxZbE5x79STjUKaA&size={width}x{height}
  mugshot\_redirect\_url\_template | https://www.yammer.com/mugshot/images/redirect/{width}x{height}/j3vWbMtXbkp952gqLQlDqKj8s3Fw42Xc\_5306d18a-4133-48a7-b568-a47af1bab178
  birth\_date |
  birth\_date\_complete |
  timezone | Pacific Time (US & Canada)
  admin | true
  verified\_admin | true
  m365\_yammer\_admin | false
  supervisor\_admin | false
  o365\_tenant\_admin | true
  answers\_admin | false
  corporate\_communicator | false
  can\_broadcast | true
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
