-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo feature disable

Disables a feature for the specified site or web

## Usage

```sh
m365 spo feature disable [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site or web for which to disable the feature.

`-i, --id <id>`
: The ID of the feature to disable.

`-s, --scope [scope]`
: Scope of the Feature to disable. Allowed values: `Site`, `Web`. Defaults to `Web`.

`--force`
: Specifies whether to continue if an error occurs when disabling the feature.
```

<Global />

## Remarks

If the specified url doesn't refer to an existing site collection, you will get a `"404 FILE NOT FOUND"` error.

## Examples

Disable site feature.

```sh
m365 spo feature disable --webUrl https://contoso.sharepoint.com/sites/salis --id 915c240e-a6cc-49b8-8b2c-0bff8b553ed3 --scope Site
```

Disable web feature (with force to ignore errors).

```sh
m365 spo feature disable --webUrl https://contoso.sharepoint.com/sites/salis --id 00bfea71-5932-4f9c-ad71-1557e5751100 --scope Web --force
```

## Response

The command won't return a response on success.
