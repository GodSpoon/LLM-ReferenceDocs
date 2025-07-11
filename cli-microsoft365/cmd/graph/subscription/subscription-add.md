-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# graph subscription add

Creates a Microsoft Graph subscription

## Usage

```sh
m365 graph subscription add [options]
```

## Options

```md definition-list
`-r, --resource <resource>`
: The resource that will be monitored for changes.

`-c, --changeTypes <changeTypes>`
: The type of change in the subscribed resource that will raise a notification. The supported values are: `created`, `updated`, `deleted`. Multiple values can be combined using a comma-separated list.

`-u, --notificationUrl <notificationUrl>`
: The URL of the endpoint that will receive the notifications. This URL must use the HTTPS protocol.

`-e, --expirationDateTime [expirationDateTime]`
: The date and time when the webhook subscription expires. The time is in UTC, and can be an amount of time from subscription creation that varies for the resource subscribed to. If not specified, the maximum allowed expiration for the specified resource will be used.

`-s, --clientState [clientState]`
: The value of the clientState property sent by the service in each notification. The maximum length is 128 characters.

`--lifecycleNotificationUrl [lifecycleNotificationUrl]`
: The URL of the endpoint that will receive the lifecycle notifications. This URL must use the HTTPS protocol.

`--notificationUrlAppId [notificationUrlAppId]`
: The app ID that the subscription service can use to generate the validation token. The value allows the client to validate the authenticity of the notification received.

`--latestTLSVersion [latestTLSVersion]`
: The latest version of TLS that the notification endpoint supports. Allowed values are `v1_0`, `v1_1`, `v1_2`, `v1_3`. Default is `v1_2`.

`--includeResourceData`
: (deprecated. Use option `withResourceData` instead) When set, the change notifications will include the changed resource data.

`--withResourceData`
: When set, the change notifications will include the changed resource data.

`--encryptionCertificate [encryptionCertificate]`
: A base64-encoded representation of a certificate with a public key used to encrypt resource data in change notifications. Required when using `withResourceData`.

`--encryptionCertificateId [encryptionCertificateId]`
: A custom app-provided identifier to help identify the certificate needed to decrypt resource data. Required when using `withResourceData`.
```

<Global />

## Remarks

On personal OneDrive, you can subscribe to the root folder or any subfolder in that drive. On OneDrive for Business, you can subscribe to only the root folder.

Notifications are sent for the requested types of changes on the subscribed folder, or any file, folder, or other `driveItem` instances in its hierarchy. You cannot subscribe to `drive` or `driveItem` instances that are not folders, such as individual files.

In Outlook, delegated permission supports subscribing to items in folders in only the signed-in user's mailbox.
That means, for example, you cannot use the delegated permission Calendars.Read to subscribe to events in another user’s mailbox.

To subscribe to change notifications of Outlook contacts, events, or messages in shared or delegated folders:

- Use the corresponding application permission to subscribe to changes of items in a folder or mailbox of any user in the tenant.
- Do not use the Outlook sharing permissions (Contacts.Read.Shared, Calendars.Read.Shared, Mail.Read.Shared, and their read/write counterparts), as they do not support subscribing to change notifications on items in shared or delegated folders.

:::info

For subscribers whose notification endpoint supports a version lower than the currently recommended version (TLS 1.2), specifying this property by a set timeline allows them to temporarily use their deprecated version of TLS before completing their upgrade to TLS 1.2. 
For these subscribers, not setting this property per the timeline would result in subscription operations failing.

:::

## Examples

Create a subscription

```sh
m365 graph subscription add --resource "me/mailFolders('Inbox')/messages" --changeTypes "updated" --notificationUrl "https://webhook.azurewebsites.net/api/send/myNotifyClient" --expirationDateTime "2016-11-20T18:23:45.935Z" --clientState "secretClientState"
```

Create a subscription on multiple change types and include resource data

```sh
m365 graph subscription add --resource "me/messages" --changeTypes "updated,deleted" --withResourceData --encryptionCertificate 'Q0xJIGZvciBNaWNyb3NvZnQgMzY1' --encryptionCertificateId 'myCert' --notificationUrl "https://webhook.azurewebsites.net/api/send/myNotifyClient" --expirationDateTime "2016-11-20T18:23:45.935Z" --clientState "secretClientState"
```

Create a subscription using the maximum allowed expiration for Group resources

```sh
m365 graph subscription add --resource groups --changeTypes "updated" --notificationUrl "https://webhook.azurewebsites.net/api/send/myNotifyClient" --lifecycleNotificationUrl "https://webhook.azurewebsites.net/api/send/lifecycleNotifications"
```

Create a subscription for Event Hub location if you are using Key Vault

```sh
m365 graph subscription add --resource user --changeTypes "created,updated,deleted" --notificationUrl "EventHub:https://azureKeyVaultName.vault.azure.net/secrets/secretName?tenantId=contoso.com"
```

Create a subscription for Event Hub location if you are using role-based access control

```sh
m365 graph subscription add --resource user --changeTypes "created,updated,deleted" --notificationUrl "EventHub:https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/eventhubname/eventHubName?tenantId=contoso.com"
```

Create a subscription for Event Grid Partner Topic and use TLS 1.3

```sh
m365 graph subscription add --resource user --changeTypes "created,updated,deleted" --latestTLSVersion 'v1_3' --notificationUrl "EventGrid:?azuresubscriptionid=8A8A8A8A-4B4B-4C4C-4D4D-12E12E12E12E&resourcegroup=resourceGroupName&partnertopic=partnerTopicName&location=partnerTopicAzureRegionName"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "id": "d2df2c16-26ee-4431-ab22-3b133556fb26",
    "resource": "groups",
    "applicationId": "31359c7f-bd7e-475c-86db-fdb8c937548e",
    "changeType": "updated",
    "clientState": "some secret value",
    "notificationUrl": "https://webhook.azurewebsites.net/api/changeNotificationHook",
    "notificationQueryOptions": null,
    "lifecycleNotificationUrl": null,
    "expirationDateTime": "2023-05-23T18:23:45.935Z",
    "creatorId": "0649d0bd-53dc-4e1d-a357-76f1d92d447b",
    "includeResourceData": null,
    "latestSupportedTlsVersion": "v1_2",
    "encryptionCertificate": null,
    "encryptionCertificateId": null,
    "notificationUrlAppId": null
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  applicationId            : 31359c7f-bd7e-475c-86db-fdb8c937548e
  changeType               : updated
  clientState              : some secret value
  creatorId                : 0649d0bd-53dc-4e1d-a357-76f1d92d447b
  encryptionCertificate    : null
  encryptionCertificateId  : null
  expirationDateTime       : 2023-05-23T18:23:45.935Z
  id                       : e2484150-c26d-4ad6-af45-84ccf6ac985a
  includeResourceData      : null
  latestSupportedTlsVersion: v1_2
  lifecycleNotificationUrl : null
  notificationQueryOptions : null
  notificationUrl          : https://webhook.azurewebsites.net/api/changeNotificationHook
  notificationUrlAppId     : null
  resource                 : groups
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,resource,applicationId,changeType,clientState,notificationUrl,expirationDateTime,creatorId,latestSupportedTlsVersion
  34270781-91cf-48ab-a930-072c5eedf808,groups,31359c7f-bd7e-475c-86db-fdb8c937548e,updated,some secret value,https://webhook.azurewebsites.net/api/changeNotificationHook,2023-05-23T18:23:45.935Z,0649d0bd-53dc-4e1d-a357-76f1d92d447b,v1_2
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # graph subscription add --resource "groups" --changeTypes "updated" --notificationUrl "https://webhook.azurewebsites.net/api/changeNotificationHook" --expirationDateTime "2023-05-23T18:23:45.935Z" --clientState "some secret value"

  Date: 2023-05-22

  ## 01d62711-6503-4b5b-8500-a5af0ee3967a

  Property | Value
  ---------|-------
  id | 01d62711-6503-4b5b-8500-a5af0ee3967a
  resource | groups
  applicationId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  changeType | updated
  clientState | some secret value
  notificationUrl | https://webhook.azurewebsites.net/api/changeNotificationHook
  expirationDateTime | 2023-05-23T18:23:45.935Z
  creatorId | 0649d0bd-53dc-4e1d-a357-76f1d92d447b
  latestSupportedTlsVersion | v1\_2
  ```

  </TabItem>
</Tabs>
