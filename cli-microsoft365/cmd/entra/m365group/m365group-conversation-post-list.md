-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra m365group conversation post list

Lists conversation posts of a Microsoft 365 group

## Usage

```sh
m365 entra m365group conversation post list [options]
```

## Options

```md definition-list
`-i, --groupId [groupId]`
: The Id of the Microsoft 365 Group. You can specify the groupId or groupName, but not both.

`-d, --groupName [groupName]`
: The Displayname of the Microsoft 365 Group. You can specify the groupId or groupName, but not both.

`-t, --threadId <threadId>`
: The ID of the thread to retrieve details for
```

<Global />

## Examples

Lists the posts of the specific conversation of Microsoft 365 group by groupId

```sh
m365 entra m365group conversation post list --groupId '00000000-0000-0000-0000-000000000000' --threadId 'EXAMPLE_SECRET_VALUE_PLACEHOLDER='
```

Lists the posts of the specific conversation of Microsoft 365 group by groupName

```sh
m365 entra m365group conversation post list --groupName 'MyGroup' --threadId 'EXAMPLE_SECRET_VALUE_PLACEHOLDER='
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "createdDateTime": "2023-06-01T20:31:51Z",
      "lastModifiedDateTime": "2023-06-01T20:31:59Z",
      "changeKey": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "categories": [],
      "receivedDateTime": "2023-06-01T20:31:57Z",
      "hasAttachments": false,
      "body": {
        "contentType": "html",
        "content": "<html><body><div>\
<div style=\"direction:ltr;\"><table border=\"0\" cellspacing=\"0\" cellpadding=\"0\" id=\"x_bodyTable\" style=\"vertical-align:top;width:100%;height:100%;border-spacing:0;border-collapse:collapse;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td id=\"x_bodyCell\" style=\"vertical-align:top;direction:ltr;width:100%;height:100%;margin:0;padding:0;border-width:0;box-sizing:border-box;\"><table border=\"0\" cellspacing=\"0\" cellpadding=\"0\" id=\"x_content\" style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;border-spacing:0;border-collapse:collapse;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;height:64px;margin:0;padding:0 0 20px 0;border-width:0;box-sizing:border-box;\">\
<div style=\"color:#0072C6;font-size:18pt;vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Welcome to the Finance group.</div>\
<div style=\"font-size:10pt;vertical-align:top;margin:5px 0 0 0;padding:0;border-width:0;box-sizing:border-box;\">Use the group to share ideas, files, and important dates.</div></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\"><table align=\"left\" border=\"0\" cellspacing=\"0\" cellpadding=\"0\" style=\"color:#666666;vertical-align:top;width:213px;border-spacing:0;border-collapse:collapse;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"vertical-align:top;margin:0;padding:0 0 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"mailto:finance@contoso.onmicrosoft.com\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\"><img data-imagetype=\"AttachmentByCid\" originalSrc=\"cid:conversationicon\" explicitlogon=\"finance@contoso.onmicrosoft.com\" src=\"cid:conversationicon\" width=\"64\" height=\"64\" style=\"display:block;text-decoration:none;border-width:0;outline:none;\"></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:5px 15px 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"mailto:finance@contoso.onmicrosoft.com\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\">\
<div style=\"color:#0072C6;font-size:14pt;vertical-align:top;text-decoration:none;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Start a conversation</div></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0 15px 20px 0;border-width:0;box-sizing:border-box;\">\
<div style=\"color:#666666;font-size:10pt;font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Read group conversations or start your own.</div></td></tr></table><table align=\"left\" border=\"0\" cellspacing=\"0\" cellpadding=\"0\" style=\"color:#666666;vertical-align:top;width:213px;border-spacing:0;border-collapse:collapse;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"vertical-align:top;margin:0;padding:0 0 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"https://outlook.office365.com/owa/finance@contoso.onmicrosoft.com/groupsubscription.ashx?realm=contoso.onmicrosoft.com&amp;source=WarmingEmail&amp;action=site\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\"><img data-imagetype=\"AttachmentByCid\" originalSrc=\"cid:documenticon\" explicitlogon=\"finance@contoso.onmicrosoft.com\" src=\"cid:documenticon\" width=\"64\" height=\"64\" style=\"display:block;text-decoration:none;border-width:0;outline:none;\"></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:5px 15px 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"https://outlook.office365.com/owa/finance@contoso.onmicrosoft.com/groupsubscription.ashx?realm=contoso.onmicrosoft.com&amp;source=WarmingEmail&amp;action=site\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\">\
<div style=\"color:#0072C6;font-size:14pt;vertical-align:top;text-decoration:none;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Add to the team site</div></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0 15px 20px 0;border-width:0;box-sizing:border-box;\">\
<div style=\"color:#666666;font-size:10pt;font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Start sharing and collaborating on content in SharePoint.</div></td></tr></table></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\"><table align=\"left\" border=\"0\" cellspacing=\"0\" cellpadding=\"0\" style=\"color:#666666;vertical-align:top;width:213px;border-spacing:0;border-collapse:collapse;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"vertical-align:top;margin:0;padding:0 0 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"https://outlook.office365.com/owa/finance@contoso.onmicrosoft.com/groupsubscription.ashx?realm=contoso.onmicrosoft.com&amp;source=WarmingEmail&amp;action=files\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\"><img data-imagetype=\"AttachmentByCid\" originalSrc=\"cid:filesicon\" explicitlogon=\"finance@contoso.onmicrosoft.com\" src=\"cid:filesicon\" width=\"64\" height=\"64\" style=\"display:block;text-decoration:none;border-width:0;outline:none;\"></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:5px 15px 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"https://outlook.office365.com/owa/finance@contoso.onmicrosoft.com/groupsubscription.ashx?realm=contoso.onmicrosoft.com&amp;source=WarmingEmail&amp;action=files\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\">\
<div style=\"color:#0072C6;font-size:14pt;vertical-align:top;text-decoration:none;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Share files</div></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0 15px 20px 0;border-width:0;box-sizing:border-box;\">\
<div style=\"color:#666666;font-size:10pt;font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">View, edit, and share all group files, including email attachments.</div></td></tr></table><table align=\"left\" border=\"0\" cellspacing=\"0\" cellpadding=\"0\" style=\"color:#666666;vertical-align:top;width:213px;border-spacing:0;border-collapse:collapse;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"vertical-align:top;margin:0;padding:0 0 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"https://outlook.office365.com/connectors/?MailboxAddress=finance%40contoso.onmicrosoft.com&amp;src=wumail\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\"><img data-imagetype=\"AttachmentByCid\" originalSrc=\"cid:connectoricon\" explicitlogon=\"finance@contoso.onmicrosoft.com\" src=\"cid:connectoricon\" width=\"64\" height=\"64\" style=\"display:block;text-decoration:none;border-width:0;outline:none;\"></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:5px 15px 5px 0;border-width:0;box-sizing:border-box;\"><a href=\"https://outlook.office365.com/connectors/?MailboxAddress=finance%40contoso.onmicrosoft.com&amp;src=wumail\" data-auth=\"NotApplicable\" style=\"text-decoration:none;\">\
<div style=\"color:#0072C6;font-size:14pt;vertical-align:top;text-decoration:none;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Connect your apps</div></a></td></tr>\
<tr style=\"vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">\
<td style=\"font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0 15px 20px 0;border-width:0;box-sizing:border-box;\">\
<div style=\"color:#666666;font-size:10pt;font-family:Segoe UI,Tahoma,Microsoft Sans Serif,Verdana,sans-serif;vertical-align:top;margin:0;padding:0;border-width:0;box-sizing:border-box;\">Connect apps like Twitter and Trello to stay current with information and updates your team cares about.</div></td></tr></table></td></tr></table></td></tr></table></div></div>\
</body></html>"
      },
      "from": {
        "emailAddress": {
          "name": "Finance",
          "address": "finance@contoso.onmicrosoft.com"
        }
      },
      "sender": {
        "emailAddress": {
          "name": "Finance",
          "address": "finance@contoso.onmicrosoft.com"
        }
      }
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  lastDeliveredDateTime  id
  ---------------------  ----------------------------------------------------------------------------------------------------------------------------------------------------
  2023-06-01T20:31:57Z   EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,createdDateTime,lastModifiedDateTime,changeKey,receivedDateTime,hasAttachments
  EXAMPLE_SECRET_VALUE_PLACEHOLDER,2023-06-01T20:31:51Z,2023-06-01T20:31:59Z,EXAMPLE_SECRET_VALUE_PLACEHOLDER,2023-06-01T20:31:57Z,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra m365group conversation post list --groupId "1cdce329-46a9-4fd3-8826-fe6587d25a8c" --threadId "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

  Date: 2023-06-02

  ## EXAMPLE_SECRET_VALUE_PLACEHOLDER

  Property | Value
  ---------|-------
  id | EXAMPLE_SECRET_VALUE_PLACEHOLDER\EXAMPLE_SECRET_VALUE_PLACEHOLDER
  createdDateTime | 2023-06-01T20:31:51Z
  lastModifiedDateTime | 2023-06-01T20:31:59Z
  changeKey | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  receivedDateTime | 2023-06-01T20:31:57Z
  hasAttachments | false
  ```

  </TabItem>
</Tabs>
