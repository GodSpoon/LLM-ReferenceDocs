-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pp copilot list

Lists Microsoft Power Platform copilots in the specified Power Platform environment

## Usage

```sh
m365 pp copilot list [options]
```

## Alias

```sh
m365 pp chatbot list [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--asAdmin`
: Run the command as admin for environments you do not have explicitly assigned permissions to.
```

<Global />

## Examples

List copilots in a specific environment.

```sh
m365 pp copilot list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"
```

List copilots in a specific environment as admin.

```sh
m365 pp copilot list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --asAdmin
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "language": 1033,
      "botid": "23f5f586-97fd-43d5-95eb-451c9797a53d",
      "authenticationTrigger": 0,
      "stateCode": 0,
      "createdOn": "2022-11-19T10:42:22Z",
      "cdsBotId": "23f5f586-97fd-43d5-95eb-451c9797a53d",
      "schemaName": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
      "ownerId": "5fa787c1-1c4d-ed11-bba1-000d3a2caf7f",
      "botModifiedOn": "2022-11-19T20:19:57Z",
      "solutionId": "fd140aae-4df4-11dd-bd17-0019b9312238",
      "isManaged": false,
      "versionNumber": 1429641,
      "timezoneRuleVersionNumber": 0,
      "name": "CLI Copilot",
      "statusCode": 1,
      "owner": "Doe, John",
      "overwriteTime": "1900-01-01T00:00:00Z",
      "componentState": 0,
      "componentIdUnique": "cdcd6496-e25d-4ad1-91cf-3f4d547fdd23",
      "authenticationMode": 1,
      "botModifiedBy": "Doe, John",
      "accessControlPolicy": 0,
      "publishedOn": "2022-11-19T19:19:53Z"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
   name         botid                                  publishedOn            createdOn              botModifiedOn
  -----------   ------------------------------------   --------------------   --------------------   --------------------
  CLI Copilot   23f5f586-97fd-43d5-95eb-451c9797a53d   2022-11-19T19:19:53Z   2022-11-19T10:42:22Z   2022-11-19T20:19:57Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  name,botid,publishedOn,createdOn,botModifiedOn
  CLI Copilot,23f5f586-97fd-43d5-95eb-451c9797a53d,2022-11-19T19:19:53Z,2022-11-19T10:42:22Z,2022-11-19T20:19:57Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # pp copilot list --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER"

  Date: 9/1/2023

  ## CLI Copilot

  Property | Value
  ---------|-------
  language | 1033
  botid | 23f5f586-97fd-43d5-95eb-451c9797a53d
  authenticationTrigger | 0
  stateCode | 0
  createdOn | 2022-11-19T10:42:22Z
  cdsBotId | 23f5f586-97fd-43d5-95eb-451c9797a53d
  schemaName | new\_bot\_23f5f58697fd43d595eb451c9797a53d
  ownerId | 5fa787c1-1c4d-ed11-bba1-000d3a2caf7f
  botModifiedOn | 2022-11-19T20:19:57Z
  solutionId | fd140aae-4df4-11dd-bd17-0019b9312238
  isManaged | false
  versionNumber | 1429641
  timezoneRuleVersionNumber | 0
  name | CLI Copilot
  statusCode | 1
  owner | Doe, John
  overwriteTime | 1900-01-01T00:00:00Z
  componentState | 0
  componentIdUnique | cdcd6496-e25d-4ad1-91cf-3f4d547fdd23
  authenticationMode | 1
  botModifiedBy | Doe, John
  accessControlPolicy | 0
  publishedOn | 2022-11-19T19:19:53Z
  ```

  </TabItem>
</Tabs>
