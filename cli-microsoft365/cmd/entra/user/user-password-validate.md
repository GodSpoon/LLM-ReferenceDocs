-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user password validate

Check a user's password against the organization's password validation policy

## Usage

```sh
m365 entra user password validate [options]
```

## Options

```md definition-list
`-p, --password <password>`
: The password to be validated.
```

<Global />

## Remarks

:::warning

This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

:::

## Examples

Validate password _cli365P@ssW0rd_ against the organization's password validation policy.

```sh
m365 entra user password validate --password "cli365P@ssW0rd"
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "isValid": true,
    "validationResults": [
      {
        "ruleName": "PasswordMinLength",
        "validationPassed": true,
        "message": "The new password must have a minimum of 8 characters."
      },
      {
        "ruleName": "PasswordMaxLength",
        "validationPassed": true,
        "message": "The new password cannot contain more than 256 characters."
      },
      {
        "ruleName": "PasswordComplexity",
        "validationPassed": true,
        "message": "The new password must contain characters from at least 3 out of: Lowercase characters, Uppercase characters, Numbers, Symbols."
      },
      {
        "ruleName": "PasswordNotBanned",
        "validationPassed": true,
        "message": "The new password must not be weak or commonly used."
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  isValid          : true
  validationResults: [{"ruleName":"PasswordMinLength","validationPassed":true,"message":"The new password must have a minimum of 8 characters."},{"ruleName":"PasswordMaxLength","validationPassed":true,"message":"The new password cannot contain more than 256 characters."},{"ruleName":"PasswordComplexity","validationPassed":true,"message":"The new password must contain characters from at least 3 out of: Lowercase characters, Uppercase characters, Numbers, Symbols."},{"ruleName":"PasswordNotBanned","validationPassed":true,"message":"The new password must not be weak or commonly used."}]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  isValid
  1
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user password validate --password "cli365P@ssW0rd"

  Date: 2023-06-02

  Property | Value
  ---------|-------
  isValid | true
  ```

  </TabItem>
</Tabs>
