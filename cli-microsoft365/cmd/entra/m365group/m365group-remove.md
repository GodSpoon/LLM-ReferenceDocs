-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group remove

Removes an Microsoft 365 Group

## Usage

```sh
m365 entra m365group remove [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft 365 Group to remove. Specify either `id` or `displayName`, but not both.

`-n, --displayName [displayName]`
: Display name of the Microsoft 365 Group to remove. Specify either `id` or `displayName`, but not both.

`-f, --force`
: Don't prompt for confirming removing the group

`--skipRecycleBin`
: Set to directly remove the group without moving it to the Recycle Bin
```

<Global />

## Remarks

If the specified _id_ doesn't refer to an existing group, you will get a `Resource does not exist` error. Additionally, if you do not have access to the group or the associated group-connected site, you will get an `Access denied` error.

When you use `--skipRecycleBin` flag to remove a Microsoft 365 group permanently, the process involves deleting the associated group-connected site and the group, and then checking if the group has been moved to the deleted groups list. In some cases, it may take a few seconds for the group to appear in the deleted groups list.

To ensure a smooth deletion process, the command employs a retry mechanism with the following parameters:

- `maxRetries`: This parameter is set to 10 by default. It specifies the maximum number of times the command will check if the group has been moved to the deleted groups list.

- `intervalInMs`: This parameter is set to 5000 milliseconds (5 seconds) by default. It defines the time interval between each retry attempt.

If the group is successfully moved to the deleted groups list within the specified number of retries, the command will then proceed to permanently remove it from the tenant. If the group cannot be removed after all retries, it will remain in the deleted groups list.

## Examples

Remove group with id _28beab62-7540-4db1-a23f-29a6018a3848_. Will prompt for confirmation before removing the group

```sh
m365 entra m365group remove --id 28beab62-7540-4db1-a23f-29a6018a3848
```

Remove group with displayName _Finance_ without prompting for confirmation

```sh
m365 entra m365group remove --displayName Finance --force
```

Remove group with id _28beab62-7540-4db1-a23f-29a6018a3848_ without prompting for confirmation and without moving it to the Recycle Bin

```sh
m365 entra m365group remove --id 28beab62-7540-4db1-a23f-29a6018a3848 --force --skipRecycleBin
```

## Response

The command won't return a response on success.
