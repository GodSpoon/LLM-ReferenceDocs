<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# pp dataverse table remove

Removes a dataverse table in a given environment

## Usage

```sh
m365 pp dataverse table remove [options]
```

## Options

```md definition-list
`-e, --environmentName <environmentName>`
: The name of the environment to remove a table from.

`-n, --name<name>`
: The name of the dataverse table to remove.

`-f, --force`
: Don't prompt for confirmation

`--asAdmin`
: Set, to remove the dataverse table as admin for environments you are not a member of.
```

<Global />

## Examples

Removes a dataverse table in a given environment

```sh
m365 pp dataverse table remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser"
```

Removes a dataverse table in a given environment as Admin

```sh
m365 pp dataverse table remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser" --asAdmin
```

Removes a dataverse table in a given environment without prompting for confirmation

```sh
m365 pp dataverse table remove --environmentName "EXAMPLE_SECRET_VALUE_PLACEHOLDER" --name "aaduser" --force
```

## Response

The command won't return a response on success.
