-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# cli completion pwsh setup

Sets up command completion for PowerShell

## Usage

```sh
m365 cli completion pwsh setup [options]
```

## Options

```md definition-list
`-p, --profile <profile>`
: Path to the PowerShell profile file
```

<Global />

## Remarks

This commands sets up command completion for the CLI for Microsoft 365 in PowerShell by registering a custom PowerShell argument completer in the specified profile. Because CLI for Microsoft 365 is not a native PowerShell module, it requires a custom completer to provide completion.

If the specified profile path doesn't exist, the CLI will try to create it.

## Examples

Set up command completion for PowerShell using the profile from the profile variable

```powershell
m365 cli completion pwsh setup --profile $profile
```

## Response

The command won't return a response on success.

## More information

- Command completion: [https://pnp.github.io/cli-microsoft365/user-guide/completion/](https://pnp.github.io/cli-microsoft365/user-guide/completion/)
