-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# onedrive report activityfilecounts

Gets the number of unique, licensed users that performed file interactions against any OneDrive account

## Usage

```sh
m365 onedrive report activityfilecounts [options]
```

## Options

```md definition-list
`-p, --period <period>`
: The length of time over which the report is aggregated. Supported values `D7`, `D30`, `D90`, `D180`.
```

<Global />

## Remarks

:::info

This command supports only csv and json output.

:::

## Examples

Gets the number of unique, licensed users that performed file interactions against any OneDrive account for the last week

```sh
m365 onedrive report activityfilecounts --period D7
```

Gets the number of unique, licensed users that performed file interactions against any OneDrive account for the last week and exports the report data in the specified path in text format

```sh
m365 onedrive report activityfilecounts --period D7 --output text > "activityfilecounts.txt"
```

Gets the number of unique, licensed users that performed file interactions against any OneDrive account for the last week and exports the report data in the specified path in json format

```sh
m365 onedrive report activityfilecounts --period D7 --output json > "activityfilecounts.json"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Report Refresh Date": "2023-05-20",
      "Viewed Or Edited": "",
      "Synced": "",
      "Shared Internally": "",
      "Shared Externally": "",
      "Report Date": "2023-05-20",
      "Report Period": "7"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Report Refresh Date,Viewed Or Edited,Synced,Shared Internally,Shared Externally,Report Date,Report Period
  2023-05-20,,,,,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Report Refresh Date,Viewed Or Edited,Synced,Shared Internally,Shared Externally,Report Date,Report Period
  2023-05-20,,,,,2023-05-20,7
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Report Refresh Date,Viewed Or Edited,Synced,Shared Internally,Shared Externally,Report Date,Report Period
  2023-05-20,,,,,2023-05-20,7
  ```

  </TabItem>
</Tabs>
