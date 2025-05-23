-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo web clientsidewebpart list

Lists available client-side web parts

## Usage

```sh
m365 spo web clientsidewebpart list [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: URL of the site for which to retrieve the information
```

<Global />

## Examples

Lists all the available client-side web parts for the specified site

```sh
m365 spo web clientsidewebpart list --webUrl https://contoso.sharepoint.com
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  [ 
    {
      "Id": "9cc0f495-db64-4d74-b06b-a3de16231fe1",
      "Name": "9cc0f495-db64-4d74-b06b-a3de16231fe1",
      "Title": "Dashboard for Viva Connections"
    }
  ]
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Id                                    Name                                  Title
  ------------------------------------  ------------------------------------  ------------------------------
  9cc0f495-db64-4d74-b06b-a3de16231fe1  9cc0f495-db64-4d74-b06b-a3de16231fe1  Dashboard for Viva Connections
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Id,Name,Title
  9cc0f495-db64-4d74-b06b-a3de16231fe1,9cc0f495-db64-4d74-b06b-a3de16231fe1,Dashboard for Viva Connections
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spo web clientsidewebpart list --webUrl "https://contoso.sharepoint.com"

  Date: 4/10/2023

  ## Dashboard for Viva Connections (9cc0f495-db64-4d74-b06b-a3de16231fe1)

  Property | Value
  ---------|-------
  Id | 9cc0f495-db64-4d74-b06b-a3de16231fe1
  Name | 9cc0f495-db64-4d74-b06b-a3de16231fe1
  Title | Dashboard for Viva Connections        
  ```

  </TabItem>
</Tabs>
