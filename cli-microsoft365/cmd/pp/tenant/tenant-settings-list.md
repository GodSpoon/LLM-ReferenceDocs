-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp tenant settings list

Lists the global Power Platform tenant settings

## Usage

```sh
m365 pp tenant settings list [options]
```

## Options

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Lists the global Power Platform settings of the tenant

```sh
m365 pp tenant settings list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "walkMeOptOut": false,
    "disableNPSCommentsReachout": false,
    "disableNewsletterSendout": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "disablePortalsCreationByNonAdminUsers": false,
    "disableSurveyFeedback": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
    "disableSupportTicketsVisibleByAllUsers": false,
    "powerPlatform": {
      "search": {
        "disableDocsSearch": false,
        "disableCommunitySearch": false,
        "disableBingVideoSearch": false
      },
      "teamsIntegration": {
        "shareWithColleaguesUserLimit": 10000
      },
      "powerApps": {
        "disableShareWithEveryone": false,
        "enableGuestsToMake": false,
        "disableMembersIndicator": false,
        "disableMakerMatch": false,
        "disableUnusedLicenseAssignment": false
      },
      "environments": {
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false
      },
      "governance": {
        "disableAdminDigest": true,
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
        "enableDefaultEnvironmentRouting": false
      },
      "licensing": {
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": 85
      },
      "powerPages": {},
      "champions": {
        "disableChampionsInvitationReachout": false,
        "disableSkillsMatchInvitationReachout": false
      },
      "intelligence": {
        "disableCopilot": false,
        "enableOpenAiBotPublishing": false
      },
      "modelExperimentation": {
        "enableModelDataSharing": false
      }
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  EXAMPLE_SECRET_VALUE_PLACEHOLDER  : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER     : false
  disableNPSCommentsReachout                    : false
  disablePortalsCreationByNonAdminUsers         : false
  disableSupportTicketsVisibleByAllUsers        : false
  disableSurveyFeedback                         : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER: false
  walkMeOptOut                                  : false
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  walkMeOptOut,disableNPSCommentsReachout,disableNewsletterSendout,EXAMPLE_SECRET_VALUE_PLACEHOLDER,disablePortalsCreationByNonAdminUsers,disableSurveyFeedback,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,disableSupportTicketsVisibleByAllUsers
  ,,,,,,,,
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp tenant settings list

  Date: 6/2/2023

  Property | Value
  ---------|-------
  walkMeOptOut | false
  disableNPSCommentsReachout | false
  disableNewsletterSendout | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  disablePortalsCreationByNonAdminUsers | false
  disableSurveyFeedback | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  disableSupportTicketsVisibleByAllUsers | false
  ```

  </TabItem>
</Tabs>
