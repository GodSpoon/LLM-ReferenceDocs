-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo userprofile set

Sets user profile property for a SharePoint user

## Usage

```sh
m365 spo userprofile set [options]
```

## Options

```md definition-list
`-u, --userName <userName>`
: Account name of the user

`-n, --propertyName <propertyName>`
: The name of the property to be set

`-v, --propertyValue <propertyValue>`
: The value of the property to be set
```

<Global />

## Remarks

You have to have tenant admin permissions in order to use this command to update profile properties of other users.

## Examples

 Updates the single-value _AboutMe_ property

```sh
m365 spo userprofile set --userName 'john.doe@mytenant.onmicrosoft.com' --propertyName 'AboutMe' --propertyValue 'Working as a Microsoft 365 developer'
```

Updates the multi-value _SPS-Skills_ property

```sh
m365 spo userprofile set --userName 'john.doe@mytenant.onmicrosoft.com' --propertyName 'SPS-Skills' --propertyValue 'CSS, HTML'
```

## Response

The command won't return a response on success.
