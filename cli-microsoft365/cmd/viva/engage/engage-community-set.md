-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# viva engage community set

Updates an existing Viva Engage community

## Usage

```sh
m365 viva engage community set [options]
```

## Options

```md definition-list
`-i, --id [id]`
: The id of the community. Specify either `id`, `displayName` or `entraGroupId`, but not multiple.

`-d, --displayName [displayName]`
: The name of the community. Specify either `id`, `displayName` or `entraGroupId`, but not multiple.

`--entraGroupId [entraGroupId]`
: The id of the Microsoft Entra group associated with the community. Specify either `id`, `displayName` or `entraGroupId`, but not multiple.

`--newDisplayName [newDisplayName]`
: New name for the community. The maximum length is 255 characters.

`--description [description]`
: The description of the community. The maximum length is 1024 characters.

`--privacy [privacy]`
: Defines the privacy level of the community. The possible values are: `public`, and `private`.
```

<Global />

## Examples

Update info about the community specified by id

```sh
m365 viva engage community set --id EXAMPLE_SECRET_VALUE_PLACEHOLDER --newDisplayName 'Developers' --description 'Community for all devs' --privacy public
```

Update info about the community specified by name

```sh
m365 viva engage community set --displayName 'Developrs' --newDisplayName 'Developers'
```

Update info about the community specified by Entra group id

```sh
m365 viva engage community set --entraGroupId '0bed8b86-5026-4a93-ac7d-56750cc099f1' --newDisplayName 'Developers'
```

## Response

The command won't return a response on success.
