-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# teams funsettings set

Updates fun settings of a Microsoft Teams team

## Usage

```sh
m365 teams funsettings set [options]
```

## Options

```md definition-list
`-i, --teamId <teamId>`
: The ID of the Teams team for which to update settings

`--allowGiphy [allowGiphy]`
: Set to `true` to allow giphy and to `false` to disable it

`--giphyContentRating [giphyContentRating]`
: Settings to set content rating for giphy. Allowed values `Strict,Moderate`

`--allowStickersAndMemes [allowStickersAndMemes]`
: Set to `true` to allow stickers and memes and to `false` to disable them

`--allowCustomMemes [allowCustomMemes]`
: Set to `true` to allow custom memes and to `false` to disable them
```

<Global />

## Examples

Allow giphy usage within a given Microsoft Teams team, setting the content rating for giphy to Moderate

```sh
m365 teams funsettings set --teamId 83cece1e-938d-44a1-8b86-918cf6151957 --allowGiphy true --giphyContentRating Moderate
```

Disable usage of giphy within a given Microsoft Teams team

```sh
m365 teams funsettings set --teamId 83cece1e-938d-44a1-8b86-918cf6151957 --allowGiphy false
```

Allow usage of stickers and memes within a given Microsoft Teams team

```sh
m365 teams funsettings set --teamId 83cece1e-938d-44a1-8b86-918cf6151957 --allowStickersAndMemes true
```

Disable usage custom memes within a given Microsoft Teams team

```sh
m365 teams funsettings set --teamId 83cece1e-938d-44a1-8b86-918cf6151957 --allowCustomMemes false
```

## Response

The command won't return a response on success.
