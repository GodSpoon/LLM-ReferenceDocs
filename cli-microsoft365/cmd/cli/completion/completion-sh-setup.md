-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# cli completion sh setup

Sets up command completion for Zsh, Bash and Fish

## Usage

```sh
m365 cli completion sh setup [options]
```

## Options

<Global />

## Examples

Set up command completion for Zsh, Bash or Fish

```powershell
m365 cli completion sh setup
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "Command completion successfully registered. Restart your shell to load the completion"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Command completion successfully registered. Restart your shell to load the completion
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Command completion successfully registered. Restart your shell to load the completion
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Command completion successfully registered. Restart your shell to load the completion
  ```

  </TabItem>
</Tabs>

## More information

- Command completion: [https://pnp.github.io/cli-microsoft365/user-guide/completion/](https://pnp.github.io/cli-microsoft365/user-guide/completion/)
