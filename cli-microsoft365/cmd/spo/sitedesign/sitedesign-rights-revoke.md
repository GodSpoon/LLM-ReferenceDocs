-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo sitedesign rights revoke

Revokes access from a site design for one or more principals

## Usage

```sh
m365 spo sitedesign rights revoke [options]
```

## Options

```md definition-list
`-i, --siteDesignId <siteDesignId>`
: The ID of the site design to revoke rights from

`-p, --principals <principals>`
: Comma-separated list of principals to revoke view rights from. Principals can be users or mail-enabled security groups in the form of `alias` or `alias@<domain name>.com`

`-f, --force`
: Don't prompt for confirming removing the site design
```

<Global />

## Remarks

If the specified id doesn't refer to an existing site design, you will get a `File not found` error.

If all principals have rights revoked on the site design, the site design becomes viewable to everyone.

If you try to revoke access for a user that doesn't have access granted to the specified site design you will get a `The specified user or domain group was not found error`.

## Examples

Revoke access to the site design with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_ from user with alias _PattiF_. Will prompt for confirmation before revoking the access

```sh
m365 spo sitedesign rights revoke --siteDesignId 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a --principals PattiF
```

Revoke access to the site design with ID _2c1ba4c4-cd9b-4417-832f-92a34bc34b2a_ from users with aliases _PattiF_ and _AdeleV_ without prompting for confirmation

```sh
m365 spo sitedesign rights revoke --siteDesignId 2c1ba4c4-cd9b-4417-832f-92a34bc34b2a --principals "PattiF,AdeleV" --force
```

## Response

The command won't return a response on success.

## More information

- SharePoint site design and site script overview: [https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview](https://learn.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)
