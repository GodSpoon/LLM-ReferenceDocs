-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# request

Executes the specified web request using CLI for Microsoft 365

## Usage

```sh
m365 request [options]
```

## Options

```md definition-list
`-u, --url <url>`
: The request URL.

`-m, --method [method]`
: The HTTP request method. Accepted values are `get`, `post`, `put`, `patch`, `delete`, `head`, `options`. The default value is `get`.

`-r, --resource [resource]`
: The resource uri for which the CLI should acquire a token from Microsoft Entra ID in order to access the service.

`-b, --body [body]`
: The request body. Optionally use `@example.json` to load the body from a file.

`-p, --filePath [filePath]`
: The file path to save the response to. This option can be used when downloading files.
```

<Global />

## Remarks

When executing a request, CLI will take care of the very basic configuration, and you'll need to specify all additional information, such as headers, method and body. CLI will take care for you of:

- applying compression and handling throttling,
- setting the `accept` to `application/json` if you don't specify it yourself,
- setting the `authorization` header to the bearer token obtained for the resource determined from the request URL

If you specify the `resource` option, the CLI will try to retrieve a valid token for the resource instead of determining the resource based on the url. The value doesn't have to be a URL. It can be also a URI like `app://<guid>`.

Specify additional headers by typing them as options, for example: `--content-type "application/json"`, `--if-match "*"`, `--x-requestdigest "somedigest"`.

You can simplify the request by using tokens for the `url` option. Following tokens are available:

- `@graph` resolves to `https://graph.microsoft.com/v1.0`
- `@graphbeta` resolves to `https://graph.microsoft.com/beta`
- `@spo` resolves to the current SharePoint URL if available. You can set a SharePoint URL using the [spo set](./spo/spo-set.mdx) command.

:::info

When building the request, depending on the shell you use, you might need to escape all `$` characters in the URL, request headers, and the body. If you don't do it, the shell will treat it as a variable and will remove the following word from the request, breaking the request.

:::

## Examples

Call the SharePoint Rest API using a GET request with a constructed URL containing expands, filters and selects.

```sh
m365 request --url "https://contoso.sharepoint.com/sites/project-x/_api/web/siteusers?\$filter=IsShareByEmailGuestUser eq true&\$expand=Groups&\$select=Title,LoginName,Email,Groups/LoginName" --accept "application/json;odata=nometadata"
```

Call the Microsoft Graph beta endpoint using a GET request.

```sh
m365 request --url "https://graph.microsoft.com/beta/me"
```

Call the SharePoint API to retrieve a form digest.

```sh
m365 request --method post --url "https://contoso.sharepoint.com/sites/project-x/_api/contextinfo"
```

Call the SharePoint API to update a site title using the @spo token.

```sh
m365 request --method post --url "@spo/sites/project-x/_api/web" --body '{ "Title": "New title" }' --content-type "application/json" --x-http-method "PATCH"
```

Call the Microsoft Graph to get a profile photo using the @graphbeta token.

```sh
m365 request --url '@graphbeta/me/photo/$value' --filePath ./profile-pic.jpg
```

## Response

The responses below are an example based on the `url` option with the value 'https://graph.microsoft.com/v1.0/me'. The output may differ based on the `url` options

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "businessPhones": [
      "123456789"
    ],
    "displayName": "John Doe",
    "givenName": "John",
    "jobTitle": null,
    "mail": "john.doe@contoso.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": null,
    "preferredLanguage": "en-US",
    "surname": "Doe",
    "userPrincipalName": "john.doe@contoso.onmicrosoft.com",
    "id": "1df1fffa-62b8-44a9-9c7c-49853f5b4ac6"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  @odata.context   : https://graph.microsoft.com/v1.0/$metadata#users/$entity
  businessPhones   : ["123456789"]
  displayName      : John Doe
  givenName        : John
  id               : 1df1fffa-62b8-44a9-9c7c-49853f5b4ac6
  jobTitle         : null
  mail             : john.doe@contoso.onmicrosoft.com
  mobilePhone      : null
  officeLocation   : null
  preferredLanguage: en-US
  surname          : Doe
  userPrincipalName: john.doe@contoso.onmicrosoft.com
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  @odata.context,businessPhones,displayName,givenName,jobTitle,mail,mobilePhone,officeLocation,preferredLanguage,surname,userPrincipalName,id
  https://graph.microsoft.com/v1.0/$metadata#users/$entity,"[""123456789""]",John Doe,John,,john.doe@contoso.onmicrosoft.com,,,en-US,Doe,john.doe@contoso.onmicrosoft.com,1df1fffa-62b8-44a9-9c7c-49853f5b4ac6
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # request --url "https://graph.microsoft.com/v1.0/me" --method "get"

  Date: 7/2/2023

  ## John Doe (1df1fffa-62b8-44a9-9c7c-49853f5b4ac6)

  Property | Value
  ---------|-------
  @odata.context | https://graph.microsoft.com/v1.0/$metadata#users/$entity
  businessPhones | ["494594133"]
  displayName | John Doe
  givenName | John
  jobTitle | null
  mail | john.doe@contoso.onmicrosoft.com
  mobilePhone | null
  officeLocation | null
  preferredLanguage | en-US
  surname | Doe
  userPrincipalName | john.doe@contoso.onmicrosoft.com
  id | 1df1fffa-62b8-44a9-9c7c-49853f5b4ac6
  ```

  </TabItem>
</Tabs>
