-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo folder set

Updates a folder

## Usage

```sh
m365 spo folder set [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site where the folder is located.

`--url <url>`
: The server- or site-relative decoded URL of the folder.

`-n, --name [name]`
: New name for the folder.

`--color [color]`
: Visual color of the folder. Valid values are a color name or a number. Check remarks for more info.
```

<Global />

## Remarks

When you specify a value for `color`, consider the following:

| Color        | Number value | String value |
|--------------|--------------|--------------|
| Yellow       | 0            | yellow       |
| Dark red     | 1            | darkRed      |
| Dark orange  | 2            | darkOrange   |
| Dark green   | 3            | darkGreen    |
| Dark teal    | 4            | darkTeal     |
| Dark blue    | 5            | darkBlue     |
| Dark purple  | 6            | darkPurple   |
| Dark pink    | 7            | darkPink     |
| Grey         | 8            | grey         |
| Light red    | 9            | lightRed     |
| Light orange | 10           | lightOrange  |
| Light green  | 11           | lightGreen   |
| Light teal   | 12           | lightTeal    |
| Light blue   | 13           | lightBlue    |
| Light purple | 14           | lightPurple  |
| Light pink   | 15           | lightPink    |

## Examples

Set the folder name to 'My Folder 2'

```sh
m365 spo folder set --webUrl https://contoso.sharepoint.com/sites/project-x --url '/Shared Documents/My Folder 1' --name 'My Folder 2'
```

Set the folder name to 'My folder 2'

```sh
m365 spo folder set --webUrl https://contoso.sharepoint.com/sites/project-x --url '/sites/project-x/Shared Documents/My Folder 1' --name 'My Folder 2'
```

Set the folder color to dark blue

```sh
m365 spo folder set --webUrl https://contoso.sharepoint.com --url '/ProjectFiles/Project-x' --color 5
```

Set the folder color to light teal

```sh
m365 spo folder set --webUrl https://contoso.sharepoint.com --url '/ProjectFiles/Project-x' --color lightTeal
```

## Response

The command won't return a response on success.
