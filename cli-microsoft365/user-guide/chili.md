-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
title: CLI assistant (chili) 🌶️
sidebar_position: 8
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# CLI assistant (chili) 🌶️

When you're new to CLI for Microsoft 365, it can feel overwhelming. There are so many commands and options to choose from. Where do you start? How do you know which commands to use? It's hard to search for things you don't know exist. So to make it easier, we introduce 🌶️ chili - a CLI docs assistant that helps you find the right commands for your tasks, powered by [Mendable AI](https://www.mendable.ai/).

## Before you start

We believe that 🌶️ chili should be available at your fingertips and super simple to run. That's why we recommend, that after installing CLI for Microsoft 365, you set up an alias for your shell. To add an alias, add to your shell profile:

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Set-Alias -Name m365? -Value m365_chili
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  alias "m365?"="m365_chili"
  ```

  </TabItem>
</Tabs>

:::tip

If you use our [Docker image](./run-cli-in-docker-container.mdx), you don't need to setup the alias manually. We setup the `m365?` alias for you in both bash and PowerShell.

:::

:::info

If you don't set up an alias, you can still use 🌶️ chili by running `m365_chili` instead of `m365?`.

:::

With this alias in place, you can ask 🌶️ chili anything by running:

```sh
m365? "how can I upgrade my SPFx project?"
```

You can also start chili without the initial prompt by running `m365?` and then typing your question.

Running this command will start the virtual assistant in the terminal. It will use the question you asked to search in CLI's documentation and answer your question, along with the list of sources from which it found the answer.

After you get an answer, you have the ability to follow up your conversation with additional questions or start from scratch. Start a new conversation to reset the assistant and ensure that it doesn't mix up the context of your questions.

## Options

### Debug mode

If the command isn't working as expected, you can start it in debug mode by running:

```sh
m365? --debug
```

or with a prompt:

```sh
m365? "how can I upgrade my SPFx project?" --debug
```

The command will now print additional information to the terminal, which you can use to troubleshoot the issue.

### Help

You can print the contents of this page directly in the terminal by running:

```sh
m365? --help
```

or short:

```sh
m365? -h
```
