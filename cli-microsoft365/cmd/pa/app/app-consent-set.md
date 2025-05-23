-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pa app consent set

Configures if users can bypass the API Consent window for the selected canvas app

## Usage

```sh
m365 pa app consent set [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment.

`-n, --name <name>`
: The name of the Power App to update

`-b, --bypass <bypass>`
: Set to `true` to allow users to bypass the API Consent window. Set to `false` to disable the bypass.

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Remarks

This command only works for canvas apps.

## Examples

Enables the bypass for the specified canvas app

```sh
m365 pa app consent set --environmentName 4be50206-9576-4237-8b17-38d8aadfaa36 --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --bypass true
```

Disables the bypass consent for the specified canvas app

```sh
m365 pa app consent set --environmentName 4be50206-9576-4237-8b17-38d8aadfaa36 --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --bypass false --force
```

## Response

The command won't return a response on success.
