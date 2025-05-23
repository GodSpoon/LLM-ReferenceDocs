-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user registrationdetails list

Retrieves a list of the authentication methods registered for users

## Usage

```sh
m365 entra user registrationdetails list [options]
```

## Options

```md definition-list
`--isAdmin [isAdmin]`
: Filter for users who are admins. Allowed values are `true` or `false`. If not specified, returns all users.

`--userType [userType]`
: Filter for members or guest users. Allowed values are `member` or `guest`. If not specified, returns all users.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Filter users by selected method as default second-factor authentication. Allowed values are `push`, `oath`, `voiceMobile`, `voiceAlternateMobile`, `voiceOffice`, `sms` or `none`. Specify either one method or more methods separated by a comma.

`--systemPreferredAuthenticationMethods [systemPreferredAuthenticationMethods]`
: Filter users by most secure authentication methods registered for second-factor authentication. Allowed values are `push`, `oath`, `voiceMobile`, `voiceAlternateMobile`, `voiceOffice`, `sms` or `none`. Specify either one method or more methods separated by a comma.

`--isSelfServicePasswordResetRegistered [isSelfServicePasswordResetRegistered]`
: Filter for users who have registered for self-service password reset. Allowed values are `true` or `false`. If not specified, returns all users.

`--isSelfServicePasswordResetEnabled [isSelfServicePasswordResetEnabled]`
: Filter for users who have been enabled for self-service password reset. Allowed values are `true` or `false`. If not specified, returns all users.

`--isSelfServicePasswordResetCapable [isSelfServicePasswordResetCapable]`
: Filter for users who are ready to perform self-service password reset. Allowed values are `true` or `false`. If not specified, returns all users.

`--isMfaRegistered [isMfaRegistered]`
: Filter for users who are registered for multi-factor authentication. Allowed values are `true` or `false`. If not specified, returns all users.

`--isMfaCapable [isMfaCapable]`
: Filter for users who are ready to perform password reset or multi-factor authentication. Allowed values are `true` or `false`. If not specified, returns all users.

`--isPasswordlessCapable [isPasswordlessCapable]`
: Filter for user who have registered a password less strong authentication method. Allowed values are `true` or `false`. If not specified, returns all users.

`--EXAMPLE_SECRET_VALUE_PLACEHOLDER [EXAMPLE_SECRET_VALUE_PLACEHOLDER]`
: Filter for users who have enabled system preferred authentication method. Allowed values are `true` or `false`. If not specified, returns all users.

`--methodsRegistered [methodsRegistered]`
: Filter users by registered methods used during registration. Allowed values are `mobilePhone`, `email`, `fido2`, `microsoftAuthenticatorPush` or `softwareOneTimePasscode`. Specify either one method or more methods separated by a comma.

`--userIds [userIds]`
: Filter users by ids. Specify at most 20 ids separated by a comma.

`--userPrincipalNames [userPrincipalNames]`
: Filter users by user principal names. Specify at most 20 UPN separated by a comma.

`-p, --properties [properties]`
: Comma-separated list of properties to retrieve.
```

<Global />

## Remarks

Using the `--properties` option, you can specify a comma-separated list of registration details properties to retrieve from the Microsoft Graph. If you don't specify any properties, the command will retrieve user's account name, registered methods and timestamp of last update.

:::info

When multiple values are specified for `--EXAMPLE_SECRET_VALUE_PLACEHOLDER` option, the command returns registration details with at least one specified selected method as default second-factor authentication.

When multiple values are specified for `--systemPreferredAuthenticationMethods` option, the command returns registration details with at least one specified most secure authentication methods registered for second-factor authentication.

When multiple values are specified for `--registeredMethods` option, the command returns registration details with at least one specified registered methods used during registration.

:::

## Examples

Retrieve registration details for all users.

```sh
m365 entra user registrationdetails list
```

Retrieve user registration details and returns only specific properties.

```sh
m365 entra user registrationdetails list --properties 'id,isAdmin'
```

Retrieve registration details for admins.

```sh
m365 entra user registrationdetails list --isAdmin true
```

Retrieve registration details for guest users.

```sh
m365 entra user registrationdetails list --userType guest
```

Retrieve registration details for users who selected either sms or push authentication method as the default second-factor for performing multifactor authentication.

```sh
m365 entra user registrationdetails list --EXAMPLE_SECRET_VALUE_PLACEHOLDER 'sms,push'
```

Retrieve registration details for users with push authentication method as the most secure authentication method among the registered methods for second factor authentication determined by the system.

```sh
m365 entra user registrationdetails list --systemPreferredAuthenticationMethods push
```

Retrieve registration details for users who have used either Microsoft Authenticator app or mobile phone during registration.

```sh
m365 entra user registrationdetails list --methodsRegistered 'microsoftAuthenticatorPush,mobilePhone'
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "id": "61b0c52f-a902-4769-9a09-c6628335b00a",
      "userPrincipalName": "AdeleV@contoso.onmicrosoft.com",
      "userDisplayName": "Adele Vance",
      "userType": "member",
      "isAdmin": false,
      "isSsprRegistered": false,
      "isSsprEnabled": false,
      "isSsprCapable": false,
      "isMfaRegistered": false,
      "isMfaCapable": false,
      "isPasswordlessCapable": false,
      "methodsRegistered": [],
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "systemPreferredAuthenticationMethods": [],
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": "none",
      "lastUpdatedDateTime": "2024-01-23T19:37:43.7170699Z"
    },
    {
      "id": "ebd27dbd-75f2-4ef8-bd51-102c3faf62ec",
      "userPrincipalName": "john.doe@contoso.onmicrosoft.com",
      "userDisplayName": "John Doe",
      "userType": "member",
      "isAdmin": false,
      "isSsprRegistered": false,
      "isSsprEnabled": false,
      "isSsprCapable": false,
      "isMfaRegistered": true,
      "isMfaCapable": true,
      "isPasswordlessCapable": false,
      "methodsRegistered": [
        "microsoftAuthenticatorPush",
        "softwareOneTimePasscode"
      ],
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": false,
      "systemPreferredAuthenticationMethods": [],
      "EXAMPLE_SECRET_VALUE_PLACEHOLDER": "push",
      "lastUpdatedDateTime": "2024-01-23T19:37:43.7165489Z"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  userPrincipalName                                methodsRegistered                                                     lastUpdatedDateTime
  -----------------------------------------------  --------------------------------------------------------------------  ----------------------------
  AdeleV@contoso.onmicrosoft.com                                                                                          2024-01-23T19:37:43.7170699Z
  john.doe@contoso.onmicrosoft.com                  microsoftAuthenticatorPush,softwareOneTimePasscode                    2024-01-23T19:37:43.7165489Z
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  id,userPrincipalName,userDisplayName,userType,isAdmin,isSsprRegistered,isSsprEnabled,isSsprCapable,isMfaRegistered,isMfaCapable,isPasswordlessCapable,EXAMPLE_SECRET_VALUE_PLACEHOLDER,EXAMPLE_SECRET_VALUE_PLACEHOLDER,lastUpdatedDateTime
  61b0c52f-a902-4769-9a09-c6628335b00a,AdeleV@contoso.onmicrosoft.com,Adele Vance,member,,,,,,,,,none,2024-01-23T19:37:43.7170699Z
  ebd27dbd-75f2-4ef8-bd51-102c3faf62ec,john.doe@contoso.onmicrosoft.com,John Doe,member,,,,,1,1,,,push,2024-01-23T19:37:43.7165489Z
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user registrationdetails list

  Date: 1/27/2024

  ## 61b0c52f-a902-4769-9a09-c6628335b00a

  Property | Value
  ---------|-------
  id | 61b0c52f-a902-4769-9a09-c6628335b00a
  userPrincipalName | AdeleV@contoso.onmicrosoft.com
  userDisplayName | Adele Vance
  userType | member
  isAdmin | false
  isSsprRegistered | false
  isSsprEnabled | false
  isSsprCapable | false
  isMfaRegistered | false
  isMfaCapable | false
  isPasswordlessCapable | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | none
  lastUpdatedDateTime | 2024-01-23T19:37:43.7170699Z

  ## ebd27dbd-75f2-4ef8-bd51-102c3faf62ec

  Property | Value
  ---------|-------
  id | ebd27dbd-75f2-4ef8-bd51-102c3faf62ec
  userPrincipalName | john.doe@contoso.onmicrosoft.com
  userDisplayName | John Doe
  userType | member
  isAdmin | false
  isSsprRegistered | false
  isSsprEnabled | false
  isSsprCapable | false
  isMfaRegistered | true
  isMfaCapable | true
  isPasswordlessCapable | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
  EXAMPLE_SECRET_VALUE_PLACEHOLDER | push
  lastUpdatedDateTime | 2024-01-23T19:37:43.7165489Z
  ```

  </TabItem>
</Tabs>
