-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams app remove

Removes a Teams app from the organization's app catalog

## Usage

```sh
m365 teams app remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: ID of the Teams app to remove. Needs to be available in your organization\'s app catalog. Specify either `id` or `name`.

`-n, --name [name]`
: Name of the Teams app to remove. Needs to be available in your organization\'s app catalog. Specify either `id` or `name`.

`-f, --force`
: Don't prompt for confirming removing the app.
```

<Global />

### Remarks

You can only remove a Teams app as a global administrator.

## Examples

Remove the Teams app by ID from the organization's app catalog. Will prompt for confirmation before actually removing the app.

```sh
m365 teams app remove --id 83cece1e-938d-44a1-8b86-918cf6151957
```

Remove the Teams app by name from the organization's app catalog. Don't prompt for confirmation.

```sh
m365 teams app remove --name HelloWorld --force
```

## Response

The command won't return a response on success.
