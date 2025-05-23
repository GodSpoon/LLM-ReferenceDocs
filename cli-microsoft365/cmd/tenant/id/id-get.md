-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant id get

Gets Microsoft 365 tenant ID for the specified domain

## Usage

```sh
m365 tenant id get [options]
```

## Options

```md definition-list
`-d, --domainName [domainName]`
: The domain name for which to retrieve the Microsoft 365 tenant ID
```

<Global />

## Remarks

If no domain name is specified, the command will return the tenant ID of the tenant to which you are currently logged in.

## Examples

Get Microsoft 365 tenant ID for the specified domain

```sh
m365 tenant id get --domainName contoso.com
```

Get Microsoft 365 tenant ID of the the tenant to which you are currently logged in

```sh
m365 tenant id get
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "e65b162c-6f87-4eb1-a24e-1b37d3504663"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  e65b162c-6f87-4eb1-a24e-1b37d3504663
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  e65b162c-6f87-4eb1-a24e-1b37d3504663
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  e65b162c-6f87-4eb1-a24e-1b37d3504663
  ```

  </TabItem>
</Tabs>
