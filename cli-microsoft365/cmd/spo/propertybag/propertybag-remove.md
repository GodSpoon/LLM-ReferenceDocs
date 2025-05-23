-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo propertybag remove

Removes specified property from the property bag

## Usage

```sh
m365 spo propertybag remove [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site from which the property should be removed.

`-k, --key <key>`
: Key of the property to be removed. Case-sensitive.

`--folder [folder]`
: Site-relative URL of the folder from which to remove the property bag value.

`-f, --force`
: Don't prompt for confirming removal of property bag value.
```

<Global />

## Examples

Removes the value of the property from the property bag located the given site

```sh
m365 spo propertybag remove --webUrl https://contoso.sharepoint.com/sites/test --key key1
```

Removes the value of the property from the property bag located in the given site root folder

```sh
m365 spo propertybag remove --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder / --force
```

Removes the value of the property from the property bag located in the given site document library

```sh
m365 spo propertybag remove --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder '/Shared Documents'
```

Removes the value of the property from the property bag located in folder in the given site document library

```sh
m365 spo propertybag remove --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder '/Shared Documents/MyFolder'
```

Removes the value of the property from the property bag located in the given site list

```sh
m365 spo propertybag remove --webUrl https://contoso.sharepoint.com/sites/test --key key1 --folder /Lists/MyList
```

## Response

The command won't return a response on success.
