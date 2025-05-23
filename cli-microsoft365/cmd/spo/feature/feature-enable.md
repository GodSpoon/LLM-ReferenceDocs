-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# spo feature enable

Enables feature for the specified site or web

## Usage

```sh
m365 spo feature enable [options]
```

## Options

```md definition-list
`-u, --webUrl <webUrl>`
: The URL of the site or web for which to enable the feature.

`-i, --id <id>`
: The ID of the feature to enable.

`-s, --scope [scope]`
: Scope of the Feature to enable. Allowed values: `Site`, `Web`. Defaults to `Web`.

`--force`
: Specifies whether to overwrite an existing feature with the same feature identifier. This parameter is ignored if there are no errors.
```

<Global />

## Remarks

If the specified url doesn't refer to an existing site collection, you will get a `"404 FILE NOT FOUND"` error.

## Examples

Enable site feature.

```sh
m365 spo feature enable --webUrl https://contoso.sharepoint.com/sites/sales --id 915c240e-a6cc-49b8-8b2c-0bff8b553ed3 --scope Site
```

Enable web feature (with force to overwrite feature with same id).

```sh
m365 spo feature enable --webUrl https://contoso.sharepoint.com/sites/sales --id 00bfea71-5932-4f9c-ad71-1557e5751100 --scope Web --force
```

## Response

The command won't return a response on success.
