-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group recyclebinitem clear

Clears Microsoft 365 Groups from the recycle bin in the current tenant

## Usage

```sh
m365 entra m365group recyclebinitem clear [options]
```

## Options

```md definition-list
`-f, --force`
: Don't prompt for confirmation to clear the recycle bin items.
```

<Global />

## Examples

Removes all deleted Microsoft 365 Groups in the tenant. Will prompt for confirmation before permanently removing groups.

```sh
m365 entra m365group recyclebinitem clear
```

Removes all deleted Microsoft 365 Groups in the tenant. Will NOT prompt for confirmation before permanently removing groups.

```sh
m365 entra m365group recyclebinitem clear --force
```

## Response

The command won't return a response on success.
