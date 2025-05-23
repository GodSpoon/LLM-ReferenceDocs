-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# cli completion pwsh update

Updates command completion for PowerShell

## Usage

```sh
m365 cli completion pwsh update [options]
```

## Options

<Global />

## Remarks

This commands updates the list of commands and their options used by command completion in PowerShell. You should run this command each time after upgrading the CLI for Microsoft 365.

## Examples

Update list of commands for PowerShell command completion

```powershell
m365 cli completion pwsh update
```

## Response

The command won't return a response on success.

## More information

- Command completion: [https://pnp.github.io/cli-microsoft365/user-guide/completion/](https://pnp.github.io/cli-microsoft365/user-guide/completion/)
