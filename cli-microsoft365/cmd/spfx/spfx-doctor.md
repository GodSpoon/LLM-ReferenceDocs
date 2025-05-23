-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spfx doctor

Verifies environment configuration for using the specific version of the SharePoint Framework

## Usage

```sh
m365 spfx doctor [options]
```

## Options

```md definition-list
`-e, --env [env]`
: Version of SharePoint for which to check compatibility: `sp2016|sp2019|spo`

`-v, --spfxVersion [spfxVersion]`
: Version of the SharePoint Framework Yeoman generator to check compatibility for without `v`, eg. `1.11.0`

`-h, --help`
: output usage information

`--query [query]`
: JMESPath query string. See [http://jmespath.org/](http://jmespath.org/) for more information and examples

`-o, --output [output]`
: Output type. `text` or `json`. Default `text`

`--verbose`
: Runs command with verbose logging

`--debug`
: Runs command with debug logging
```

## Remarks

This commands helps you to verify if your environment meets all prerequisites for building solutions using a particular version of the SharePoint Framework.

The command starts by detecting the version of SharePoint Framework that you want to use. First, it looks at the current project. If you didn't run the command in the context of a SharePoint Framework project, the command will try to determine the SharePoint Framework version based on the SharePoint Framework Yeoman generator that you have installed either in the current directory or globally.

Based on the determined version of the SharePoint Framework, the command will look at other dependencies such as Node.js, npm, Yeoman, Gulp CLI and TypeScript to verify if their meet the requirements of that particular version of the SharePoint Framework.

If you miss any required tools or use a version that doesn't meet the SharePoint Framework requirements, the command will give you a list of recommendation how to address these issues.

Next to verifying the readiness of your environment to use a particular version of the SharePoint Framework, you can also check if the version of the SharePoint Framework that you use is compatible with the specific version of SharePoint. Supported versions are `sp2016`, `sp2019` and `spo`.

:::info

Checks ran by this command are based on what is officially supported by Microsoft. It's possible that using different package managers or packages versions will work just fine.

:::

:::info

This command supports only text or json output.

:::

## Examples

Verify if your environment meets the requirements to work with SharePoint Framework based on the globally installed version of the SharePoint Framework Yeoman generator or the current project

```sh
m365 spfx doctor --output text
```

Verify if your environment meets the requirements to work with the SharePoint Framework and also if the version of the SharePoint Framework that you're using is compatible with SharePoint 2019

```sh
m365 spfx doctor --env sp2019 --output text
```

Verify if your environment meets the requirements to work with SharePoint Framework v1.11.0

```sh
m365 spfx doctor --spfxVersion 1.11.0 --output text
```

Verify if your environment meets the requirements to work with SharePoint Framework v1.11.0 and outputs it in a JSON format.

```sh
m365 spfx doctor --spfxVersion 1.11.0 --output json
```

## Response

### Response with no issues

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "check": "SharePoint Framework",
      "passed": true,
      "version": "1.18.2",
      "message": "SharePoint Framework v1.18.2 valid."
    },
    {
      "check": "SharePoint Framework",
      "passed": true,
      "version": "1.18.2",
      "message": "SharePoint Framework v1.18.2"
    },
    {
      "check": "env",
      "passed": true,
      "message": "Supported in SPO",
      "version": "spo"
    },
    {
      "check": "Node",
      "passed": true,
      "message": "Node v18.18.2",
      "version": "18.18.2"
    },
    {
      "check": "yo",
      "passed": true,
      "message": "yo v5.0.0",
      "version": "5.0.0"
    },
    {
      "check": "gulp-cli",
      "passed": true,
      "message": "gulp-cli v2.3.0",
      "version": "2.3.0"
    },
    {
      "check": "typescript",
      "passed": true,
      "message": "bundled typescript used"
    }
  ]
  ```

  </TabItem>

  <TabItem value="Text">

  ```text
  CLI for Microsoft 365 SharePoint Framework doctor
  Verifying configuration of your system for working with the SharePoint Framework

  √ SharePoint Framework v1.15.0
  √ Node v16.13.0    
  √ yo v4.3.0
  √ gulp-cli v2.3.0
  √ bundled typescript used
  ```

  </TabItem>
</Tabs>

### Response with issues reported

When the installed version of Yeoman is lower than expected to run SharePoint Framework v1.15.0

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "check": "SharePoint Framework",
      "passed": true,
      "version": "1.15.0",
      "message": "SharePoint Framework v1.15.0 valid."
    },
    {
      "check": "SharePoint Framework",
      "passed": true,
      "version": "1.15.0",
      "message": "SharePoint Framework v1.15.0"
    },
    {
      "check": "env",
      "passed": true,
      "message": "Supported in SPO",
      "version": "spo"
    },
    {
      "check": "Node",
      "passed": true,
      "message": "Node v16.18.0",
      "version": "16.18.0"
    },
    {
      "check": "yo",
      "passed": false,
      "message": "yo v3.1.1 found, v^4 required",
      "version": "3.1.1",
      "fix": "npm i -g yo@4"
    },
    {
      "check": "gulp-cli",
      "passed": true,
      "message": "gulp-cli v2.3.0",
      "version": "2.3.0"
    },
    {
      "check": "typescript",
      "passed": true,
      "message": "bundled typescript used"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  CLI for Microsoft 365 SharePoint Framework doctor
  Verifying configuration of your system for working with the SharePoint Framework

  √ SharePoint Framework v1.15.0
  √ Node v16.16.0
  × yo v3.1.1 found, v^4 required
  √ gulp-cli v2.3.0
  √ bundled typescript used

  Recommended fixes:

  - npm i -g yo@4
  ```

  </TabItem>
</Tabs>
