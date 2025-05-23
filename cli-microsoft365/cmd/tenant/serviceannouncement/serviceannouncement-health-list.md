-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant serviceannouncement health list

Gets the health report of all subscribed services for a tenant

## Usage

```sh
m365 tenant serviceannouncement health list [options]
```

## Options

```md definition-list
`-i, --issues`
: Return the collection of issues that happened on the service, with detailed information for each issue. Is only returned in JSON output mode.
```

<Global />

## Examples

Get the health report of all subscribed services for a tenant

```sh
m365 tenant serviceannouncement health list
```

Get the health report of all subscribed services for a tenant including the issues that happend on each service

```sh
m365 tenant serviceannouncement health list --issues
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "service": "Exchange Online",
      "status": "serviceDegradation",
      "id": "Exchange"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id          status              service
  ----------  ------------------  -----------------
  Exchange    serviceDegradation  Exchange Online
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,status,service
  Exchange,serviceDegradation,Exchange Online
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant serviceannouncement health list

  Date: 4/19/2023

  ## Exchange

  Property | Value
  ---------|-------
  service | Exchange Online
  status | serviceDegradation
  id | Exchange
  ```

  </TabItem>
</Tabs>

### `issues` response

When we make use of the option `issues` the response will differ.

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "service": "Microsoft Defender for Cloud Apps",
      "status": "serviceOperational",
      "id": "cloudappsecurity",
      "issues": [
        {
          "startDateTime": "2022-05-13T00:00:00Z",
          "endDateTime": "2022-05-16T13:10:00Z",
          "lastModifiedDateTime": "2022-05-17T11:00:42.2Z",
          "title": "Microsoft Defender for Cloud Apps admin panel changes not propagating to Microsoft Defender for Endpoint",
          "id": "CS381143",
          "impactDescription": "Admins may notice that Microsoft Defender for Cloud Apps admin panel changes did not propagate to Microsoft Defender for",
          "classification": "advisory",
          "origin": "microsoft",
          "status": "serviceRestored",
          "service": "Microsoft Defender for Cloud Apps",
          "feature": "Cloud App Security",
          "featureGroup": "Cloud App Security",
          "isResolved": true,
          "highImpact": null,
          "details": [],
          "posts": [
            {
              "createdDateTime": "2022-05-17T08:31:31.113Z",
              "postType": "regular",
              "description": {
                "contentType": "html",
                "content": "Title: Microsoft Defender for Cloud Apps admin panel changes not propagating to Microsoft Defender for Endpoint\

User Impact: Admins may notice that Microsoft Defender for Cloud Apps admin panel changes do not propagate to Microsoft Defender for Endpoint.\

Current status: We're analyzing system logs to determine the source of the issue.\

Scope of impact: Impact is specific to users who are served through the affected infrastructure.\

Next update by: Tuesday, May 17, 2022, at 10:30 AM UTC"
              }
            }
          ]
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id          status              service
  ----------  ------------------  -----------------
  Exchange    serviceDegradation  Exchange Online
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,status,service
  Exchange,serviceDegradation,Exchange Online
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant serviceannouncement health list --issues "true"

  Date: 4/19/2023

  ## Exchange

  Property | Value
  ---------|-------
  service | Exchange Online
  status | serviceDegradation
  id | Exchange
  ```

  </TabItem>
</Tabs>
