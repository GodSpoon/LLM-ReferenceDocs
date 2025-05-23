-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import CLISettings from '/docs/_clisettings.mdx';
import Global from '/docs/cmd/_global.mdx';

# cli config set

Sets CLI for Microsoft 365 configuration options

## Usage

```sh
m365 cli config set [options]
```

## Options

```md definition-list
`-k, --key <key>`
: Config key to specify

`-v, --value <value>`
: Config value to set
```

<Global />

## Available settings

Following is the list of configuration settings available in CLI for Microsoft 365.

<CLISettings />

## Examples

Configure CLI to automatically display help when executing a command failed

```sh
m365 cli config set --key showHelpOnFailure --value true
```

Configure the default CLI output to JSON

```sh
m365 cli config set --key output --value json
```

## Response

The command won't return a response on success.

## More information

- [Configuring the CLI for Microsoft 365](../../../user-guide/configuring-cli.mdx)
