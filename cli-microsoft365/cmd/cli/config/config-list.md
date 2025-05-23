-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import CLISettings from '/docs/_clisettings.mdx';
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli config list

List all self-set CLI for Microsoft 365 configurations

## Usage

```sh
m365 cli config list [options]
```

## Options

<Global />

## Available settings

Following is the list of configuration settings available in CLI for Microsoft 365.

<CLISettings />

## Examples

List all self set configuration keys with their value

```sh
m365 cli config list
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "errorOutput": "stdout"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  errorOutput: stdout
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  errorOutput
  stdout
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # cli config list

  Date: 29/6/2023

  Property | Value
  ---------|-------
  errorOutput | stdout
  ```

  </TabItem>
</Tabs>

## More information

- [Configuring the CLI for Microsoft 365](../../../user-guide/configuring-cli.mdx)
