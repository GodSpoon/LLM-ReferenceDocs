-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# app permission list

Lists API permissions for the current Microsoft Entra app

## Usage

```sh
m365 app permission list [options]
```

## Options

```md definition-list
`--appId [appId]`
: Client ID of the Microsoft Entra app registered in the .m365rc.json file to retrieve API permissions for.
```

<Global />

## Remarks

Use this command to quickly look up API permissions for the Microsoft Entra application registration registered in the _.m365rc.json_ file in your current project (folder).

If you have multiple apps registered in your .m365rc.json file, you can specify the app for which you'd like to retrieve permissions using the `--appId` option. If you don't specify the app using the `--appId` option, you'll be prompted to select one of the applications from your _.m365rc.json_ file.

## Examples

Retrieve API permissions for your current Microsoft Entra app.

```sh
m365 app permission list
```

Retrieve API permissions for the Microsoft Entra app with the client ID specified in the _.m365rc.json_ file.

```sh
m365 app permission list --appId e23d235c-fcdf-45d1-ac5f-24ab2ee0695d
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "resource": "Microsoft Teams - Teams And Channels Service",
      "permission": "channels.readwrite",
      "type": "Application"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  resource                                      permission          type
  --------------------------------------------  ------------------  -----------
  Microsoft Teams - Teams And Channels Service  channels.readwrite  Application
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  resource,permission,type
  Microsoft Teams - Teams And Channels Service,channels.readwrite,Application
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # app permission list

  Date: 5/29/2023

  Property | Value
  ---------|-------
  resource | Microsoft Teams - Teams And Channels Service
  permission | channels.readwrite
  type | Application
  ```

  </TabItem>
</Tabs>
