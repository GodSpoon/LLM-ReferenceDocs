-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra m365group renew

Renews Microsoft 365 group's expiration

## Usage

```sh
m365 entra m365group renew [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The ID of the Microsoft 365 group to renew. Specify either `id` or `displayName`, but not both.

`-n, --displayName [displayName]`
: Display name of the Microsoft 365 Group to renew. Specify either `id` or `displayName`, but not both.
```

<Global />

## Remarks

If the specified _id_ doesn't refer to an existing group, you will get a `The remote server returned an error: (404) Not Found.` error.

## Examples

Renew the Microsoft 365 group with id _28beab62-7540-4db1-a23f-29a6018a3848_

```sh
m365 entra m365group renew --id 28beab62-7540-4db1-a23f-29a6018a3848
```

Renew the Microsoft 365 group with displayName _Finance_

```sh
m365 entra m365group renew --displayName Finance
```

## Response

The command won't return a response on success.
