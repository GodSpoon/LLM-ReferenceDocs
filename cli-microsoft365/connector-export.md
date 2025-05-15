<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pa connector export

Exports the specified Power Automate or Power Apps custom connector

## Usage

```sh
m365 pa connector export [options]
```

## Alias

```sh
m365 flow connector export
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment where the custom connector to export is located

`-n, --name <name>`
: The name of the custom connector to export

`--outputFolder [outputFolder]`
: Path where the folder with connector's files should be saved. If not specified, will create the connector's folder in the current folder.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If no output folder has been specified, the `pa connector export` command will create a folder named after the connector in the current folder. If the output folder has been specified, the folder named after the connector will be created in that folder.

## Examples

Export the specified custom connector

```sh
m365 pa connector export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE_SECRET_VALUE_PLACEHOLDER
```

Export the specified custom connector to the specific directory

```sh
m365 pa connector export --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name EXAMPLE_SECRET_VALUE_PLACEHOLDER --outputFolder connector
```

## Response

The command won't return a response on success.
