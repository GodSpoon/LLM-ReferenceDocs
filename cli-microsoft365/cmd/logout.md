-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# logout

Log out from Microsoft 365

## Usage

```sh
m365 logout [options]
```

## Options

<Global />

## Remarks

The `logout` command logs out from Microsoft 365 and removes any access and refresh tokens from memory

## Examples

Log out from Microsoft 365

```sh
m365 logout
```

Log out from Microsoft 365 in debug mode including detailed debug information in the console output

```sh
m365 logout --debug
```

## Response

The command won't return a response on success.
