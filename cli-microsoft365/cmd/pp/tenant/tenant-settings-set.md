-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp tenant settings set

Sets the global Power Platform configuration of the tenant

## Usage

```sh
m365 pp tenant settings set [options]
```

## Options

```md definition-list
`--walkMeOptOut [walkMeOptOut]`
: Ability to opt out of guided experiences using WalkMe in Power Platform. Valid values: `true`, `false`.

`--disableNPSCommentsReachout [disableNPSCommentsReachout]`
: Ability to disable re-surveying users who left prior feedback via NPS prompts in Power Platform. Valid values: `true`, `false`.

`--disableNewsletterSendout [disableNewsletterSendout]`
: Ability to disable the newsletter sendout feature. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Restrict all environments to be created by Global Admins, Power Platform Admins, or Dynamics365 Service Admins. Valid values: `true`, `false`.

`--disablePortalsCreationByNonAdminUsers [disablePortalsCreationByNonAdminUsers]`
: Restrict all portals to be created by Global Admins, Power Platform Admins, or Dynamics365 Service Admins. Valid values: `true`, `false`.

`--disableSurveyFeedback [disableSurveyFeedback]`
: Ability to disable all NPS survey feedback prompts in Power Platform. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Restrict all trial environments to be created by Global Admins, Power Platform Admins, or Dynamics365 Service Admins. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Ability to disable capacity allocation by environment administrators. Valid values: `true`, `false`.

`--disableSupportTicketsVisibleByAllUsers [disableSupportTicketsVisibleByAllUsers]`
: Ability to disable support ticket creation by non-admin users in the tenant. Valid values: `true`, `false`.

`--disableDocsSearch [disableDocsSearch]`
: When this setting is true, users in the environment will see a message that Microsoft Learn and Documentation search categories have been turned off by the administrator in the search results page. Valid values: `true`, `false`.

`--disableCommunitySearch [disableCommunitySearch]`
: When this setting is true, users in the environment will see a message that Community and Blog search categories have been turned off by the administrator in the search results page. Valid values: `true`, `false`.

`--disableBingVideoSearch [disableBingVideoSearch]`
: When this setting is true, users in the environment will see a message that video search categories have been turned off by the administrator in the search results page. Valid values: `true`, `false`.

`--shareWithColleaguesUserLimit [shareWithColleaguesUserLimit]`
: Maximum value setting for the number of users in a security group used to share an app built using Power Apps on Microsoft Teams. Specify any number as a value.

`--disableShareWithEveryone [disableShareWithEveryone]`
: Ability to disable the Share With Everyone capability in all Power Apps. Valid values: `true`, `false`.

`--enableGuestsToMake [enableGuestsToMake]`
: Ability to allow guest users in your tenant to create Power Apps. Valid values: `true`, `false`.

`--disableMembersIndicator [disableMembersIndicator]`
: Ability to disable the display of a members indicator. Valid values: `true`, `false`.

`--disableMakerMatch [disableMakerMatch]`
: Ability to disable the Maker Match feature, which helps organizations find internal resources with the necessary skills to develop custom apps and solutions using Power Platform. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Ability to disable the selection of a preferred data location for Teams environment. Valid values: `true`, `false`.

`--disableAdminDigest [disableAdminDigest]`
: When true, the entire organization is unsubscribed from the weekly digest. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Restrict all developer environments to be created by Global Admins, Power Platform Admins, or Dynamics365 Service Admins. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Restrict billing policies to be created by Global Admins, Power Platform Admins, or Dynamics365 Service Admins. Valid values: `true`, `false`.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Ability to set a threshold for storage capacity consumption warnings. Specify any number as a value.

`--disableChampionsInvitationReachout [disableChampionsInvitationReachout]`
: Ability to disable all invitations to become a Power Platform champion. Valid values: `true`, `false`.

`--disableSkillsMatchInvitationReachout [disableSkillsMatchInvitationReachout]`
: Ability to disable all skills match invitations to become part of the makers community. Valid values: `true`, `false`.

`--disableCopilot [disableCopilot]`
: Ability to turn off or disable the Copilot feature. Valid values: `true`, `false`.

`--enableOpenAiBotPublishing [enableOpenAiBotPublishing]`
: Ability to enable or disable the publishing of OpenAI bots within the organization's environment. Valid values: `true`, `false`.

`--enableModelDataSharing [enableModelDataSharing]`
: Ability to enable or disable the sharing of model data within the organization's environment. Valid values: `true`, `false`.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Disable environment creation for non-admin users

```sh
m365 pp tenant settings set --EXAMPLE_SECRET_VALUE_PLACEHOLDER true --EXAMPLE_SECRET_VALUE_PLACEHOLDER true --EXAMPLE_SECRET_VALUE_PLACEHOLDER true
```

Enable Power App creation for guest users

```sh
m365 pp tenant settings set --enableGuestsToMake true
```

Disable guided experience, survey feedback and newsletter

```sh
m365 pp tenant settings set --walkMeOptOut true --disableNewsletterSendout true --disableSurveyFeedback true
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
        "disableMakerMatch": false
      },
      "environments": {
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false
      },
      "governance": {
        "disableAdminDigest": false,
        "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false
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
  disableNewsletterSendout                      : false
  disablePortalsCreationByNonAdminUsers         : false
  disableSupportTicketsVisibleByAllUsers        : false
  disableSurveyFeedback                         : false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER: false
  powerPlatform                                 : {"search":{"disableDocsSearch":false,"disableCommunitySearch":false,"disableBingVideoSearch":false},"teamsIntegration":{"shareWithColleaguesUserLimit":10000},"powerApps":{"disableShareWithEveryone":false,"enableGuestsToMake":false,"disableMembersIndicator":false,"disableMakerMatch":false},"environments":{"EXAMPLE_SECRET_VALUE_PLACEHOLDER":false},"governance":{"disableAdminDigest":false,"EXAMPLE_SECRET_VALUE_PLACEHOLDER":false},"licensing":{"EXAMPLE_SECRET_VALUE_PLACEHOLDER":false,"EXAMPLE_SECRET_VALUE_PLACEHOLDER":85},"powerPages":{},"champions":{"disableChampionsInvitationReachout":false,"disableSkillsMatchInvitationReachout":false},"intelligence":{"disableCopilot":false,"enableOpenAiBotPublishing":false},"modelExperimentation":{"enableModelDataSharing":false}}
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
  # pp tenant settings set --EXAMPLE_SECRET_VALUE_PLACEHOLDER false --EXAMPLE_SECRET_VALUE_PLACEHOLDER false --EXAMPLE_SECRET_VALUE_PLACEHOLDER false

  Date: 14/3/2023

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
