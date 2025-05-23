-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# entra user session revoke

Revokes all sign-in sessions for a given user

## Usage

```sh
m365 entra user session revoke [options]
```

## Options
```md definition-list
`-i, --userId [userId]`
: The id of the user. Specify either `userId` or `userName`, but not both.

`-n, --userName [userName]`
: The user principal name of the user. Specify either `userId` or `userName`, but not both.

`-f, --force`
: Don't prompt for confirmation.
```

<Global />

## Remarks

:::info

To use this command you must be either **User Administrator** or **Global Administrator**.

:::

:::note

There might be a small delay of a few minutes before tokens are revoked.

This API doesn't revoke sign-in sessions for external users, because external users sign in through their home tenant.

:::

## Examples

Revoke sign-in sessions of a user specified by id

```sh
m365 entra user session revoke --userId 4fb72b9b-d0b0-4a35-8bc1-83f9a6488c48
```

Revoke sign-in sessions of a user specified by its UPN

```sh
m365 entra user session revoke --userName john.doe@contoso.onmicrosoft.com
```

Revoke sign-in sessions of a user specified by its UPN without prompting for confirmation

```sh
m365 entra user session revoke --userName john.doe@contoso.onmicrosoft.com --force
```

## Response

The command won't return a response on success.
