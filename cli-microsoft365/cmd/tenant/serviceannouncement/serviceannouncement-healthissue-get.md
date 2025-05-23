-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant serviceannouncement healthissue get

Gets a specified service health issue for tenant.

## Usage

```sh
m365 tenant serviceannouncement healthissue get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The issue id to get details for
```

<Global />

## Examples

Gets information about issue with ID _MO226784_

```sh
m365 tenant serviceannouncement healthissue get --id MO226784
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
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
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  classification      : advisory
  details             : []
  endDateTime         : 2022-05-24T22:20:00Z
  feature             : Other
  featureGroup        : Other
  highImpact          : null
  id                  : CR384241
  impactDescription   : Users may have experienced delays when installing applications within the Power Platform admin center.
  isResolved          : true
  lastModifiedDateTime: 2022-05-24T22:27:18.63Z
  origin              : microsoft
  posts               : [{"createdDateTime":"2022-05-24T21:22:56.817Z","postType":"regular","description":{"contentType":"html","content":"Title: Installation delays within the Power Platform admin center

User Impact: Users may experience delays when installing applications within the Power Platform admin center.

We are aware of an emerging issue where users are experiencing delays when installing applications through the Power Platform admin center. We are investigating the issue and will provide another update within the next 30 minutes.

This information is preliminary and may be subject to changes, corrections, and updates."}}]
  service             : Dynamics 365 Apps
  startDateTime       : 2022-05-24T16:00:00Z
  status              : serviceRestored
  title               : Installation delays within the Power Platform admin center
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  startDateTime,endDateTime,lastModifiedDateTime,title,id,impactDescription,classification,origin,status,service,feature,featureGroup,isResolved,highImpact,details,posts
  2022-05-24T16:00:00Z,2022-05-24T22:20:00Z,2022-05-24T22:27:18.63Z,Installation delays within the Power Platform admin center,CR384241,Users may have experienced delays when installing applications within the Power Platform admin center.,advisory,microsoft,serviceRestored,Dynamics 365 Apps,Other,Other,1,,[],"[{""createdDateTime"":""2022-05-24T21:22:56.817Z"",""postType"":""regular"",""description"":{""contentType"":""html"",""content"":""Title: Installation delays within the Power Platform admin center

User Impact: Users may experience delays when installing applications within the Power Platform admin center.

We are aware of an emerging issue where users are experiencing delays when installing applications through the Power Platform admin center. We are investigating the issue and will provide another update within the next 30 minutes.

This information is preliminary and may be subject to changes, corrections, and updates.""}}]"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant serviceannouncement healthissue get --id "MO226784"

  Date: 5/24/2022

  ## Installation delays within the Power Platform admin center (MO226784)

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
