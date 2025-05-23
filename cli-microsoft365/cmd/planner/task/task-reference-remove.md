-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# planner task reference remove

Removes the reference from the Planner task.

## Usage

```sh
m365 planner task reference remove [options]
```

## Options

```md definition-list
`-u, --url [url]`
: URL location of the reference. Specify either `alias` or `url` but not both.

`--alias [alias]`
: The alias of the reference. Specify either `alias` or `url` but not both.

`-i, --taskId <taskId>`
: ID of the task.

`-f, --force`
: Don't prompt for confirmation
```

<Global />

## Examples

Removes a reference with the url _https://www.microsoft.com_ from the Planner task with the id _2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2_

```sh
m365 planner task reference remove --url "https://www.microsoft.com" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2" 
```

Removes a reference with the alias _Parker_ from the Planner task with the id _2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2_

```sh
m365 planner task reference remove --alias "Parker" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2"
```

## Response

The command won't return a response on success.
