-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import CLISettings from '/docs/_clisettings.mdx';
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli config get

Gets value of a CLI for Microsoft 365 configuration option

## Usage

```sh
m365 cli config get [options]
```

## Options

```md definition-list
`-k, --key <key>`
: Config key to get the value of
```

<Global />

## Available settings

Following is the list of configuration settings available in CLI for Microsoft 365.

<CLISettings />

## Remarks

If the specified setting has not been configured, CLI will return no output.

## Examples

Get the output configured for CLI for Microsoft 365

```sh
m365 cli config get --key output
```

## Response

When retrieving the `output` key, responses will look like this:

<Tabs>
  <TabItem value="JSON">

  ```json
  "json"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  json
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  json
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  json
  ```

  </TabItem>
</Tabs>

## More information

- [Configuring the CLI for Microsoft 365](../../../user-guide/configuring-cli.mdx)
