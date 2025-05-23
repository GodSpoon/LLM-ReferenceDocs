-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli doctor

Retrieves diagnostic information about the current environment

## Usage

```sh
m365 cli doctor [options]
```

## Options

<Global />

## Remarks

This command gets all the necessary diagnostic information needed to triage and debug CLI issues without exposing any security-sensitive details

## Examples

Retrieve diagnostic information.

```sh
m365 cli doctor
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "os": {
      "platform": "win32",
      "version": "Windows 10 Pro",
      "release": "10.0.19045"
    },
    "cliVersion": "6.1.0",
    "nodeVersion": "v16.13.0",
    "cliEntraAppId": "31359c7f-bd7e-475c-86db-fdb8c937548e",
    "cliEntraAppTenant": "common",
    "authMode": "deviceCode",
    "cliEnvironment": "",
    "cliConfig": {
      "output": "json",
      "showHelpOnFailure": false
    },
    "roles": [],
    "scopes": {
      "https://graph.microsoft.com": [
        "AllSites.FullControl"
      ]
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  authMode         : deviceCode
  cliConfig        : {"output":"json","showHelpOnFailure":false}
  cliEntraAppId    : 31359c7f-bd7e-475c-86db-fdb8c937548e
  cliEntraAppTenant: common
  cliEnvironment   :
  cliVersion       : 6.1.0
  nodeVersion      : v16.13.0
  os               : {"platform":"win32","version":"Windows 10 Pro","release":"10.0.19045"}
  roles            : []
  scopes           : {"https://graph.microsoft.com":["AllSites.FullControl"]}
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  os,cliVersion,nodeVersion,cliEntraAppId,cliEntraAppTenant,authMode,cliEnvironment,cliConfig,roles,scopes
  "{""platform"":""win32"",""version"":""Windows 10 Pro"",""release"":""10.0.19045""}",6.1.0,v16.13.0,31359c7f-bd7e-475c-86db-fdb8c937548e,common,deviceCode,,"{""output"":""json"",""showHelpOnFailure"":false}",[],"{""https://graph.microsoft.com"":[""AllSites.FullControl""]}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # cli doctor

  Date: 2022-09-05

  Property | Value
  ---------|-------
  cliVersion | 6.1.0
  nodeVersion | v16.13.0
  cliEntraAppId | 31359c7f-bd7e-475c-86db-fdb8c937548e
  cliEntraAppTenant | common
  authMode | deviceCode
  cliEnvironment |
  ```

  </TabItem>
</Tabs>
