-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pa app remove

Removes the specified Power App

## Usage

```sh
m365 pa app remove [options]
```

## Options

```md definition-list
`-n, --name <name>`
: The name of the Power App to remove

`-f, --force`
: Don't prompt for confirmation

`--asAdmin`
: Run the command as admin for apps you don't own.

`-e, --environmentName [environmentName]`
: The name of the environment. Required when using `asAdmin`.
```

<Global />

## Remarks

By default, the command will try to remove a Power App. As maker, you are able to delete the Power Apps you own. As administrator, you are also able to delete Power Apps from other users.

To remove an app you do not own, use the `asAdmin` option and make sure to specify the `environmentName` option as well.

To remove a model-driven Power App you need administrator permissions.

If the Power App with the name you specified doesn't exist, you will get the `Error: App 'abc' does not exist` error.

## Examples

Removes the specified Power App

```sh
m365 pa app remove --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```

Removes the specified Power App without confirmation

```sh
m365 pa app remove --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --force
```

Removes the specified Power App you don't own

```sh
m365 pa app remove --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --environmentName EXAMPLE_SECRET_VALUE_PLACEHOLDER --asAdmin
```

## Response

The command won't return a response on success.
