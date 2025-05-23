-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# entra user hibp

Allows you to retrieve all accounts that have been pwned with the specified username

## Usage

```sh
m365 entra user hibp [options]
```

## Options

```md definition-list
`-n, --userName <userName>`
: The name of the user to retrieve information for.

`--apiKey, <apiKey>`
: Have I been pwned `API Key`. You can buy it from [https://haveibeenpwned.com/API/Key](https://haveibeenpwned.com/API/Key)

`--domain, [domain]`
: Limit the returned breaches only contain results with the domain specified.
```

<Global />

## Remarks

If the user with the specified user name doesn't involved in any breach, you will get a `No pwnage found` message when running in debug or verbose mode.

If `API Key` is invalid, you will get a `Required option apiKey not specified` error.

## Examples

Check if user with by a user name is in a data breach.

```sh
m365 entra user hibp --userName account-exists@hibp-integration-tests.com --apiKey _YOUR-API-KEY_
```

Check if user by a user name is in a data breach against the domain specified.

```sh
m365 entra user hibp --userName account-exists@hibp-integration-tests.com --apiKey _YOUR-API-KEY_ --domain adobe.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [
    {
      "Name": "Adobe",
      "Title": "Adobe",
      "Domain": "adobe.com",
      "BreachDate": "2013-10-04",
      "AddedDate": "2013-12-04T00:00Z",
      "ModifiedDate": "2022-05-15T23:52Z",
      "PwnCount": 152445165,
      "Description": "In October 2013, 153 million Adobe accounts were breached with each containing an internal ID, username, email, <em>encrypted</em> password and a password hint in plain text. The password cryptography was poorly done and many were quickly resolved back to plain text. The unencrypted hints also <a href=\"http://www.troyhunt.com/2013/11/adobe-credentials-and-serious.html\" target=\"_blank\" rel=\"noopener\">disclosed much about the passwords</a> adding further to the risk that hundreds of millions of Adobe customers already faced.",
      "DataClasses": [
        "Email addresses",
        "Password hints",
        "Passwords",
        "Usernames"
      ],
      "IsVerified": true,
      "IsFabricated": false,
      "IsSensitive": false,
      "IsRetired": false,
      "IsSpamList": false,
      "LogoPath": "https://haveibeenpwned.com/Content/Images/PwnedLogos/Adobe.png"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Name               Title               Domain                 BreachDate  AddedDate          ModifiedDate       PwnCount   Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       DataClasses                                         IsVerified  IsFabricated  IsSensitive  IsRetired  IsSpamList  LogoPath
  -----------------  ------------------  ---------------------  ----------  -----------------  -----------------  ---------  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  --------------------------------------------------  ----------  ------------  -----------  ---------  ----------  --------------------------------------------------------------------------
  Adobe              Adobe               adobe.com              2013-10-04  2013-12-04T00:00Z  2022-05-15T23:52Z  152445165  In October 2013, 153 million Adobe accounts were breached with each containing an internal ID, username, email, <em>encrypted</em> password and a password hint in plain text. The password cryptography was poorly done and many were quickly resolved back to plain text. The unencrypted hints also <a href="http://www.troyhunt.com/2013/11/adobe-credentials-and-serious.html" target="_blank" rel="noopener">disclosed much about the passwords</a> adding further to the risk that hundreds of millions of Adobe customers already faced.  Email addresses,Password hints,Passwords,Usernames  true        false         false        false      false       https://haveibeenpwned.com/Content/Images/PwnedLogos/Adobe.png
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Name,Title,Domain,BreachDate,AddedDate,ModifiedDate,PwnCount,Description,IsVerified,IsFabricated,IsSensitive,IsRetired,IsSpamList,LogoPath
  Adobe,Adobe,adobe.com,2013-10-04,2013-12-04T00:00Z,2022-05-15T23:52Z,152445165,"In October 2013, 153 million Adobe accounts were breached with each containing an internal ID, username, email, <em>encrypted</em> password and a password hint in plain text. The password cryptography was poorly done and many were quickly resolved back to plain text. The unencrypted hints also <a href=""http://www.troyhunt.com/2013/11/adobe-credentials-and-serious.html"" target=""_blank"" rel=""noopener"">disclosed much about the passwords</a> adding further to the risk that hundreds of millions of Adobe customers already faced.",1,,,,,https://haveibeenpwned.com/Content/Images/PwnedLogos/Adobe.png
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # entra user hibp --userName "account-exists@hibp-integration-tests.com" --apiKey "_YOUR-API-KEY_"

  Date: 2023-06-02

  ## Adobe

  Property | Value
  ---------|-------
  Name | Adobe
  Title | Adobe
  Domain | adobe.com
  BreachDate | 2013-10-04
  AddedDate | 2013-12-04T00:00Z
  ModifiedDate | 2022-05-15T23:52Z
  PwnCount | 152445165
  Description | In October 2013, 153 million Adobe accounts were breached with each containing an internal ID, username, email, <em>encrypted</em> password and a password hint in plain text. The password cryptography was poorly done and many were quickly resolved back to plain text. The unencrypted hints also <a href="http://www.troyhunt.com/2013/11/adobe-credentials-and-serious.html" target="\_blank" rel="noopener">disclosed much about the passwords</a> adding further to the risk that hundreds of millions of Adobe customers already faced.
  IsVerified | true
  IsFabricated | false
  IsSensitive | false
  IsRetired | false
  IsSpamList | false
  LogoPath | https://haveibeenpwned.com/Content/Images/PwnedLogos/Adobe.png
  ```

  </TabItem>
</Tabs>

## More information

- Have I been pwned API documentation: [https://haveibeenpwned.com/API/v3](https://haveibeenpwned.com/API/v3)
