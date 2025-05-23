-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# docs

Returns the CLI for Microsoft 365 docs webpage URL

## Usage

```sh
m365 docs [options]
```

## Options

<Global />

## Remarks

Configure `autoOpenLinksInBrowser` using [cli config set](../cmd/cli/config/config-set.mdx) to automatically open the webpage in the default browser.

## Examples

Returns the CLI for Microsoft 365 docs webpage URL

```sh
m365 docs
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "https://pnp.github.io/cli-microsoft365/"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  https://pnp.github.io/cli-microsoft365/
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  https://pnp.github.io/cli-microsoft365/
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  https://pnp.github.io/cli-microsoft365/
  ```

  </TabItem>
</Tabs>
