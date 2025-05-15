<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# outlook message move

Moves message to the specified folder

## Usage

```sh
m365 outlook message move [options]
```

## Options

```md definition-list
`--id <id>`
: ID of the message to move

`--sourceFolderName [sourceFolderName]`
: Name of the folder to move the message from

`--sourceFolderId [sourceFolderId]`
: ID of the folder to move the message from

`--targetFolderName [targetFolderName]`
: Name of the folder to move the message to

`--targetFolderId [targetFolderId]`
: ID of the folder to move the message to
```

<Global />

## Examples

Move the specified message to another folder specified by ID

```sh
m365 outlook message move --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --sourceFolderId EXAMPLE_SECRET_VALUE_PLACEHOLDER= --targetFolderId EXAMPLE_SECRET_VALUE_PLACEHOLDER=
```

Move the specified message to another folder specified by name

```sh
m365 outlook message move --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --sourceFolderName Inbox --targetFolderName "Project X"
```

Move the specified message to another folder specified by its well-known
name

```sh
m365 outlook message move --id EXAMPLE_SECRET_VALUE_PLACEHOLDER= --sourceFolderName inbox --targetFolderName archive
```

## Response

The command won't return a response on success.

## More information

- Well-known folder names: [https://learn.microsoft.com/graph/api/resources/mailfolder?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/resources/mailfolder?view=graph-rest-1.0)
