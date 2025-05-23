-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant serviceannouncement healthissue list

Gets all service health issues for the tenant.

## Usage

```sh
m365 tenant serviceannouncement healthissue list [options]
```

## Options

```md definition-list
`-s, --service [service]`
: Retrieve service health issues for the particular service. If not provided, retrieves health issues for all services
```

<Global />

## Examples

Get service health issues of all services in Microsoft 365

```sh
m365 tenant serviceannouncement healthissue list
```

Get service health issues for Microsoft Forms

```sh
m365 tenant serviceannouncement healthissue list --service "Microsoft Forms"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "startDateTime": "2022-05-24T16:00:00Z",
      "endDateTime": "2022-05-24T22:20:00Z",
      "lastModifiedDateTime": "2022-05-24T22:27:18.63Z",
      "title": "Installation delays within the Power Platform admin center",
      "id": "CR384241",
      "impactDescription": "Users may have experienced delays when installing applications within the Power Platform admin center.",
      "classification": "advisory",
      "origin": "microsoft",
      "status": "serviceRestored",
      "service": "Dynamics 365 Apps",
      "feature": "Other",
      "featureGroup": "Other",
      "isResolved": true,
      "highImpact": null,
      "details": [],
      "posts": [
        {
          "createdDateTime": "2022-05-24T21:22:56.817Z",
          "postType": "regular",
          "description": {
            "contentType": "html",
            "content": "Title: Installation delays within the Power Platform admin center\

User Impact: Users may experience delays when installing applications within the Power Platform admin center.\

We are aware of an emerging issue where users are experiencing delays when installing applications through the Power Platform admin center. We are investigating the issue and will provide another update within the next 30 minutes.\

This information is preliminary and may be subject to changes, corrections, and updates."
          }
        }
      ]
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  id        title
  --------  ----------------------------------------------------------
  CR384241  Installation delays within the Power Platform admin center
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,title
  CR384241,Installation delays within the Power Platform admin center
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant serviceannouncement healthissue list

  Date: 5/24/2022

  ## Installation delays within the Power Platform admin center (CR384241)

  Property | Value
  ---------|-------
  startDateTime | 2022-05-24T16:00:00Z
  endDateTime | 2022-05-24T22:20:00Z
  lastModifiedDateTime | 2022-05-24T22:27:18.63Z
  title | Installation delays within the Power Platform admin center
  id | CR384241
  impactDescription | Users may have experienced delays when installing applications within the Power Platform admin center.
  classification | advisory
  origin | microsoft
  status | serviceRestored
  service | Dynamics 365 Apps
  feature | Other
  featureGroup | Other
  isResolved | true
  ```

  </TabItem>
</Tabs>

## More information

- List serviceAnnouncement issues: [https://learn.microsoft.com/graph/api/serviceannouncement-list-issues](https://learn.microsoft.com/graph/api/serviceannouncement-list-issues)
