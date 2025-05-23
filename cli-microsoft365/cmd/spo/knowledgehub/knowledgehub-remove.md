-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spo knowledgehub remove

Removes the Knowledge Hub Site setting for your tenant

## Usage

```sh
m365 spo knowledgehub remove [options]
```

## Options

```md definition-list
`-f, --force`
: Do not prompt for confirmation before removing the Knowledge Hub Site setting for your tenant.
```

<Global />

## Remarks

:::info

To use this command you must be either **SharePoint Administrator** or **Global Administrator**.

:::

## Examples

Removes the Knowledge Hub Site setting for your tenant.

```sh
m365 spo knowledgehub remove
```

Removes the Knowledge Hub Site setting for your tenant without confirmation.

```sh
m365 spo knowledgehub remove --force
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "The knowledge hub site setting was removed."
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  The knowledge hub site setting was removed.
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  The knowledge hub site setting was removed.
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  The knowledge hub site setting was removed.
  ```

  </TabItem>
</Tabs>
