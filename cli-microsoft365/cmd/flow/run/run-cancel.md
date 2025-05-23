-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# flow run cancel

Cancels a specific run for the specified flow

## Usage

```sh
m365 flow run cancel [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the run to cancel

`--flowName <flowName>`
: The name of the flow to cancel the run for

`-e, --environmentName <environmentName>`
: The name of the environment where the flow is located

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

If the run with the name you specified doesn't exist, you will get the `The workflow 'xyz' run 'abc' could not be found.` error.

## Examples

Cancel the given run of the specified flow

```sh
m365 flow run cancel --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --name 08586653536760200319026785874CU62
```

## Response

The command won't return a response on success.
