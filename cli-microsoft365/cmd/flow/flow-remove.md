-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# flow remove

Removes the specified Power Automate flow

## Usage

```sh
m365 flow remove [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the Power Automate flow to remove

`-e, --environmentName <environmentName>`
: The name of the environment to which the flow belongs

`--asAdmin`
: Set, to remove the flow as admin

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Remarks

By default, the command will try to remove a Power Automate flow you own. If you want to remove a Flow owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Power Automate flow with the name you specified doesn't exist, you will get the `Error: Resource 'abc' does not exist in environment 'xyz'` error.

## Examples

Removes the specified Power Automate flow owned by the currently signed-in user

```sh
m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```

Removes the specified Power Automate flow owned by the currently signed-in user without confirmation

```sh
m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --force
```

Removes the specified Power Automate flow owned by another user

```sh
m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --asAdmin
```

Removes the specified Power Automate flow owned by another user without confirmation

```sh
m365 flow remove --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --asAdmin --force
```

## Response

The command won't return a response on success.
