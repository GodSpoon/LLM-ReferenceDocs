-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# graph schemaextension remove

Removes specified Microsoft Graph schema extension

## Usage

```sh
m365 graph schemaextension remove [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The unique identifier for the schema extension definition

`-f, --force`
: Don't prompt for confirming removing the specified schema extension
```

<Global />

## Remarks

To remove specified schema extension definition, you have to pass the ID of the schema
extension.

## Examples

Removes specified Microsoft Graph schema extension with ID domain_myExtension. Will prompt for confirmation

```sh
m365 graph schemaextension remove --id domain_myExtension 
```

Removes specified Microsoft Graph schema extension with ID domain_myExtension without prompt for confirmation

```sh
m365 graph schemaextension remove --id domain_myExtension --force
```

## Response

The command won't return a response on success.
