-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import CLISettings from '/docs/_clisettings.mdx';
import Global from '/docs/cmd/_global.mdx';

# cli config reset

Resets the specified CLI configuration option to its default value

## Usage

```sh
m365 cli config reset [options]
```

## Options

```md definition-list
`-k, --key [key]`
: Config key to reset. If not specified, will reset all configuration settings to default
```

<Global />

## Available settings

Following is the list of configuration settings available in CLI for Microsoft 365.

<CLISettings />

## Examples

Reset CLI configuration option _showHelpOnFailure_ to its default value

```sh
m365 cli config reset --key showHelpOnFailure
```

Reset all configuration settings to default

```sh
m365 cli config reset
```

## Response

The command won't return a response on success.

## More information

- [Configuring the CLI for Microsoft 365](../../../user-guide/configuring-cli.mdx)
