-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# pa app owner set

Sets a new owner for a Power Apps app

## Usage

```sh
m365 pa app owner set [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`--appName <appName>`
: The name (GUID) of the Microsoft Power App.

`--userId [userId]`
: The Microsoft Entra ID of the new owner. Specify either `userId` or `userName` but not both.

`--userName [userName]`
: The user principal name of the new owner. Specify either `userId` or `userName` but not both.

`--roleForOldAppOwner [roleForOldAppOwner]`
: Grant permissions for the previous owner. Allowed values: `CanView`, `CanEdit`. Don't specify a value to remove the previous owner from the app.
```

<Global />

## Remarks

:::info

To use this command you must be a Global or Power Platform admin.

:::

## Examples

Set a new owner for a Power Apps app and make the previous owner co-owner

```sh
m365 pa app owner set --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName 7ab97923-4a4d-4467-b030-12071d2b810b --userId c6ee6ed4-0172-4fdc-87a3-cfd9c324de1d --roleForOldAppOwner CanEdit
```

Set a new owner for a Power Apps app and remove the previous owner

```sh
m365 pa app owner set --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --appName 7ab97923-4a4d-4467-b030-12071d2b810b --userName john.doe@contoso.com
```

## Response

The command won't return a response on success.
