-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# external connection urltoitemresolver add

Adds a URL to item resolver to an external connection

## Usage

```sh
m365 external connection urltoitemresolver add [options]
```

## Options

```md definition-list
`-c, --externalConnectionId <externalConnectionId>`
: The ID of the external connection to which to add the resolver

`--baseUrls <baseUrls>`
: Comma-separated list of base URLs

`--urlPattern <urlPattern>`
: Regex pattern to match URLs

`-i, --itemId <itemId>`
: Pattern that matches captured matches from the URL with the external item ID

`-p, --priority <priority>`
: Integer that defines the resolution order
```
<Global />

## Examples

Adds a URL to item resolver to an existing connection

```sh
m365 external connection urltoitemresolver add --externalConnectionId "samplesolutiongallery" --baseUrls "https://adoption.microsoft.com" --urlPattern "/sample-solution-gallery/sample/(?<sampleId>[^/]+)" --itemId "{sampleId}" --priority 1
```

## Response

The command won't return a response on success.

## More information

- Microsoft Graph external connection activitySettings: [https://learn.microsoft.com/graph/api/resources/externalconnectors-activitysettings?view=graph-rest-1.0](https://learn.microsoft.com/graph/api/resources/externalconnectors-activitysettings?view=graph-rest-1.0)
