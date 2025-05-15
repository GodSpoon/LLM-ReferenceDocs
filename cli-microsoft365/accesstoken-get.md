<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# util accesstoken get

Gets access token for the specified resource

## Usage

```sh
m365 util accesstoken get [options]
```

## Options

```md definition-list
`-r, --resource <resource>`
: The resource for which to retrieve an access token

`--new`
: Retrieve a new access token to ensure that it's valid for as long as possible

`--decoded`
: Retrieve a decoded access token
```

<Global />

## Remarks

:::tip

Instead of specifying the full URL of the resource, you can use one of the following shorthand identifiers: `sharepoint`, `graph`.

:::

The `util accesstoken get` command returns an access token for the specified resource. If an access token has been previously retrieved and is still valid, the command will return the cached token. If you want to ensure that the returned access token is valid for as long as possible, you can force the command to retrieve a new access token by using the `--new` option.

## Examples

Get access token for the Microsoft Graph

```sh
m365 util accesstoken get --resource https://graph.microsoft.com
```

Get access token for SharePoint Online using the shorthand identifier

```sh
m365 util accesstoken get --resource sharepoint
```

Get access token for Microsoft Graph using the shorthand identifier

```sh
m365 util accesstoken get --resource graph
```

Get a new access token for SharePoint Online

```sh
m365 util accesstoken get --resource https://contoso.sharepoint.com --new
```

Get a decoded access token for SharePoint Online

```sh
m365 util accesstoken get --resource https://contoso.sharepoint.com --decoded
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  "EXAMPLE_SECRET_VALUE_PLACEHOLDER=.EXAMPLE_SECRET_VALUE_PLACEHOLDER"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=.EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=.EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  EXAMPLE_SECRET_VALUE_PLACEHOLDER=.EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ```

  </TabItem>
</Tabs>

### `decoded` response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "alg": "HS256",
    "typ": "JWT"
  }.{
    "sub": "1234567890",
    "name": "John Doe",
    "iat": 1516239022
  }.[signature]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
    {
    "alg": "HS256",
    "typ": "JWT"
  }.{
    "sub": "1234567890",
    "name": "John Doe",
    "iat": 1516239022
  }.[signature]
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  {
    "alg": "HS256",
    "typ": "JWT"
  }.{
    "sub": "1234567890",
    "name": "John Doe",
    "iat": 1516239022
  }.[signature]
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  {
    "alg": "HS256",
    "typ": "JWT"
  }.{
    "sub": "1234567890",
    "name": "John Doe",
    "iat": 1516239022
  }.[signature]
  ```

  </TabItem>
</Tabs>
