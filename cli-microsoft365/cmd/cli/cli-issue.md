-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli issue

Returns, or opens a URL that takes the user to the right place in the CLI GitHub repo to create a new issue reporting bug, feedback, ideas, etc.

## Usage

```sh
m365 cli issue [options]
```

## Options

```md definition-list
`-t, --type <type>`
: The type of issue to raise. Supports `bug`, `command` and `sample`.
```

<Global />

## Remarks

If you are running the command in a docker container, or the Azure Cloud Shell the CLI won't be able to open the URL directly and you'll need to copy the URL to a new tab or browser instance yourself.

## Examples

Raise a new issue

```sh
m365 cli issue --type bug
```

Suggest a new command

```sh
m365 cli issue --type command
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "https://aka.ms/cli-m365/new-command"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  https://aka.ms/cli-m365/new-command
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  https://aka.ms/cli-m365/new-command
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  https://aka.ms/cli-m365/new-command
  ```

  </TabItem>
</Tabs>
