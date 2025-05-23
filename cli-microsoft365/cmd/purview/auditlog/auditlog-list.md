-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# purview auditlog list

List audit logs within your tenant

## Usage

```sh
m365 purview auditlog list [options]
```

## Options

```md definition-list
`--contentType <contentType>`
: Content type of logs to retrieve. Possible values: `AzureActiveDirectory`, `Exchange`, `SharePoint`, `General`, `DLP`.

`--startTime [startTime]`
: Time indicating the **inclusive** start of a time range of content to return. This should be defined as a valid ISO 8601 string (2021-12-16T18:28:48.6964197Z). Start time cannot be more than 7 days in the past. Default value is 24h ago.

`--endTime [endTime]`
: Time indicating the **exclusive** end of a time range of content to return. This should be defined as a valid ISO 8601 string (2021-12-16T18:28:48.6964197Z). Default value is now.
```

<Global />

## Remarks

:::info

Before you can access audit log data, you must enable unified audit logging for your Microsoft 365 tenant. For instructions, check out the page [Turn auditing on or off](https://learn.microsoft.com/microsoft-365/compliance/audit-log-enable-disable).

:::

:::info

When running this command for the first time for a certain content type, a subscription for this content type is created. It can take up to 12 hours for the first content blobs to become available for that subscription.

:::

:::tip

Retrieving audit logs is an intensive process, especially for large or active tenants. In this case it may take some time to retrieve all audit logs. It can be useful to add the `--verbose` option to your command to view the command progress.

:::

When you specify a value for `contentType`, consider the following:

- `AzureActiveDirectory` includes all Microsoft Entra ID audit logs.
- `Exchange` includes all Exchange audit logs.
- `SharePoint` includes all SharePoint audit logs.
- `General` includes all other workloads not included in the previous content types.
- `DLP` DLP events only for all workloads.

## Examples

List all SharePoint audit logs for the past 24 hours

```sh
m365 purview auditlog list --contentType SharePoint
```

List all SharePoint audit logs within a specific time frame

```sh
m365 purview auditlog list --contentType SharePoint --startTime "2023-01-01T00:00:00Z" --endTime "2023-01-03T09:00:00Z"
```

Get all SharePoint audit logs within a specific time frame and save the logs to a file

```sh
m365 purview auditlog list --contentType SharePoint --startTime "2023-01-01T00:00:00Z" --endTime "2023-01-01T12:00:00Z" > auditLogs.json
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "AppAccessContext": {
          "ClientAppId": "94bfad6e-a0b3-4eb9-8e2b-83eeb335de28",
          "CorrelationId": "040d86a0-f096-5000-d4b4-baac627b75f3",
          "UniqueTokenId": "5CVDGmrynkGYBkY-MPynAA"
      },
      "CreationTime": "2023-01-10T00:00:00",
      "Id": "4d671836-c772-4169-55f9-08dae745c839",
      "Operation": "ListItemViewed",
      "OrganizationId": "6e40c2aa-0565-4013-b38c-d5e6f0c42993",
      "RecordType": 36,
      "UserKey": "i:0i.t|00000003-0000-0ff1-ce00-000000000000|app@sharepoint",
      "UserType": 0,
      "Version": 1,
      "Workload": "SharePoint",
      "ClientIP": "168.63.104.32",
      "ObjectId": "https://contoso.sharepoint.com/sites/Project-x/Lists/cae414a1-ac65-4a90-844e-651d7a1e463d/305_.000",
      "UserId": "john.doe@contoso.com",
      "ApplicationId": "94bfad6e-a0b3-4eb9-8e2b-83eeb335de28",
      "CorrelationId": "040d86a0-f096-5000-d4b4-baac627b75f3",
      "EventSource": "SharePoint",
      "ItemType": "ListItem",
      "ListId": "cae414a1-ac65-4a90-844e-651d7a1e463d",
      "ListItemUniqueId": "2d364471-4d27-4186-b139-072c8225ee4a",
      "Site": "51f5a236-b2e5-4a6d-a81d-13d188610155",
      "UserAgent": "NONISV|Contoso|ContosoApp/1.0",
      "WebId": "38ab94aa-a904-4c2b-8467-4be0e457f97b",
      "CustomizedDoclib": false,
      "FromApp": false,
      "ItemCount": 192,
      "ListBaseTemplateType": "100",
      "ListBaseType": "GenericList",
      "ListColor": "",
      "ListIcon": "",
      "Source": "Unknown",
      "TemplateTypeId": "",
      "ListTitle": "cae414a1-ac65-4a90-844e-651d7a1e463d"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```txt
  CreationTime         UserId                Operation       ObjectId                                                                                          
  -------------------  --------------------  --------------  --------------------------------------------------------------------------------------------------
  2023-01-10T00:00:00  john.doe@contoso.com  ListItemViewed  https://contoso.sharepoint.com/sites/Project-x/Lists/cae414a1-ac65-4a90-844e-651d7a1e463d/305_.000
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  CreationTime,UserId,Operation,ObjectId
  2023-01-10T00:00:00,john.doe@contoso.com,ListItemViewed,https://contoso.sharepoint.com/sites/Project-x/Lists/cae414a1-ac65-4a90-844e-651d7a1e463d/305_.000
  ```

  </TabItem>
</Tabs>

## More information

- Explanation of all available audit log activities/operations: https://learn.microsoft.com/purview/audit-log-activities
- Explanation of all available audit log properties: https://learn.microsoft.com/purview/audit-log-detailed-properties
