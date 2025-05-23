-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# flow recyclebinitem restore

Restores a soft-deleted Power Automate flow

## Usage

```sh
m365 flow recyclebinitem restore [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment where the flow is located.

`-n, --flowName <flowName>`
: The name of the Power Automate flow.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reaches general availability.

:::

:::info

To use this command, you must be a Global or Power Platform administrator.

:::

When a Power Automate flow is restored, it will be automatically disabled. To make it operational again, you must [enable](../flow-enable.mdx) it.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

## Examples

Restores a soft-deleted flow within a specific environment

```sh
m365 flow recyclebinitem restore --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a
```

## Response

The command won't return a response on success.
