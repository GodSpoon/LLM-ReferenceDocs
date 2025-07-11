-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage network list

Returns a list of networks to which the current user has access

## Usage

```sh
m365 viva engage network list [options]
```

## Options

```md definition-list
`--includeSuspended`
: (deprecated. Use option `withSuspended` instead) Include the networks in which the user is suspended.

`--withSuspended`
: Include the networks in which the user is suspended.
```

<Global />

## Remarks

:::warning

In order to use this command, you need to grant the Microsoft Entra application used by the CLI for Microsoft 365 the permission to the Viva Engage API. To do this, execute the `cli consent --service VivaEngage` command.

:::

## Examples

Returns the current user's networks.

```sh
m365 viva engage network list
```

Returns the current user's networks including the networks in which the user is suspended.

```sh
m365 viva engage network list --withSuspended
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "type": "network",
      "id": 5897756673,
      "email": "",
      "name": "Contoso",
      "community": false,
      "permalink": "contoso.onmicrosoft.com",
      "web_url": "https://www.yammer.com/contoso.onmicrosoft.com",
      "show_upgrade_banner": false,
      "header_background_color": "#396B9A",
      "header_text_color": "#FFFFFF",
      "navigation_background_color": "#38699F",
      "navigation_text_color": "#FFFFFF",
      "paid": true,
      "moderated": false,
      "is_freemium": false,
      "is_org_chart_enabled": false,
      "is_group_enabled": true,
      "is_chat_enabled": true,
      "is_translation_enabled": false,
      "created_at": "2020/02/26 10:33:56 +0000",
      "is_storyline_enabled": true,
      "is_storyline_preview_enabled": false,
      "is_stories_enabled": true,
      "is_stories_preview_enabled": false,
      "is_premium_preview_enabled": false,
      "profile_fields_config": {
        "enable_work_history": true,
        "enable_education": true,
        "enable_job_title": true,
        "enable_work_phone": true,
        "enable_mobile_phone": true,
        "enable_summary": true,
        "enable_interests": true,
        "enable_expertise": true,
        "enable_location": true,
        "enable_im": true,
        "enable_skype": true,
        "enable_websites": true
      },
      "browser_deprecation_url": null,
      "external_messaging_state": "disabled",
      "state": "enabled",
      "enforce_office_authentication": true,
      "office_authentication_committed": true,
      "is_gif_shortcut_enabled": true,
      "is_link_preview_enabled": true,
      "attachments_in_private_messages": false,
      "secret_groups": false,
      "force_connected_groups": true,
      "force_spo_files": false,
      "connected_all_company": true,
      "m365_native_mode": true,
      "force_optin_modern_client": false,
      "admin_modern_client_flexible_optin": false,
      "aad_guests_enabled": false,
      "all_company_group_creation_state": null,
      "unseen_message_count": -1,
      "preferred_unseen_message_count": -1,
      "private_unseen_thread_count": 0,
      "inbox_unseen_thread_count": 0,
      "private_unread_thread_count": 0,
      "unseen_notification_count": 0,
      "has_fake_email": false,
      "is_primary": true,
      "allow_attachments": true,
      "attachment_types_allowed": "ALL",
      "privacy_link": "https://go.microsoft.com/fwlink/p/?linkid=857875"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  community: false
  email    :
  id       : 5897756673
  name     : Contoso
  permalink: contoso.onmicrosoft.com
  web_url  : https://www.yammer.com/contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,name,email,community,permalink,web_url
  5897756673,Contoso,,,contoso.onmicrosoft.com,https://www.yammer.com/contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # viva engage network list

  Date: 2023-05-16

  ## Contoso (98327945216)

  Property | Value
  ---------|-------
  type | network
  id | 98327945216
  email | contoso.onmicrosoft.com@yammer.com
  name | Contoso
  community | false
  permalink | contoso.onmicrosoft.com
  web\_url | https://www.yammer.com/contoso.onmicrosoft.com
  show\_upgrade\_banner | false
  header\_background\_color | #396B9A
  header\_text\_color | #FFFFFF
  navigation\_background\_color | #38699F
  navigation\_text\_color | #FFFFFF
  paid | true
  moderated | false
  is\_freemium | false
  is\_org\_chart\_enabled | false
  is\_group\_enabled | true
  is\_chat\_enabled | true
  is\_translation\_enabled | false
  created\_at | 2022/12/08 07:38:34 +0000
  is\_storyline\_enabled | true
  is\_storyline\_preview\_enabled | false
  is\_storyline\_per\_user\_control\_enabled | false
  is\_stories\_enabled | true
  is\_stories\_preview\_enabled | false
  is\_premium\_preview\_enabled | false
  is\_leadership\_corner\_enabled | true
  external\_messaging\_state | inbound\_only
  state | enabled
  enforce\_office\_authentication | true
  office\_authentication\_committed | true
  is\_gif\_shortcut\_enabled | true
  is\_link\_preview\_enabled | true
  attachments\_in\_private\_messages | false
  secret\_groups | false
  force\_connected\_groups | true
  force\_spo\_files | true
  connected\_all\_company | true
  m365\_native\_mode | true
  force\_optin\_modern\_client | true
  admin\_modern\_client\_flexible\_optin | false
  aad\_guests\_enabled | true
  all\_company\_group\_creation\_state | 3
  is\_network\_questions\_enabled | true
  is\_network\_questions\_only\_mode\_enabled | false
  unseen\_message\_count | -1
  preferred\_unseen\_message\_count | -1
  private\_unseen\_thread\_count | 0
  inbox\_unseen\_thread\_count | 0
  private\_unread\_thread\_count | 0
  unseen\_notification\_count | 2
  has\_fake\_email | false
  is\_primary | true
  allow\_attachments | true
  attachment\_types\_allowed | ALL
  privacy\_link | https://go.microsoft.com/fwlink/p/?linkid=857875
  user\_state | active
  ```

  </TabItem>
</Tabs>
