-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# flow run resubmit

Resubmits a specific flow run for the specified Microsoft Flow

## Usage

```sh
m365 flow run resubmit [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the run to resubmit

`--flowName <flowName>`
: The name of the flow to resubmit the run for

`-e, --environmentName <environmentName>`
: The name of the environment where the Flow is located

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Microsoft Flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error.

If the run with the name you specified doesn't exist, you will get the `The workflow 'xyz' run 'abc' could not be found.` error.

## Examples

Resubmits a specific flow run for the specified Microsoft Flow

```sh
m365 flow run resubmit --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --name 08586653536760200319026785874CU62
```

Resubmits a specific flow run for the specified Microsoft Flow without prompting for confirmation

```sh
m365 flow run resubmit --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --name 08586653536760200319026785874CU62 --force
```

## Response

The command won't return a response on success.
