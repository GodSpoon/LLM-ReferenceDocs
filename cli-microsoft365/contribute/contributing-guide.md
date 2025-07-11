-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Contributing to the CLI for Microsoft 365

We love to accept contributions. If you want to get involved in helping us grow the CLI for Microsoft 365, whether that is suggesting or adding a new command, extending an existing command, or updating our documentation, we would love to hear from you.

Before you submit your first PR, please read the following guide. We'd hate to see you work on something that someone else is already working on, something that we agreed not to do, or something that doesn't match the project.

Sharing is caring!

## You have an idea for a new command

Awesome! Good ideas are invaluable for every product. Before you start hacking away, please check if there is no similar idea already listed in the [issue list](https://github.com/pnp/cli-microsoft365/issues). This ensures that your idea is unique and not being worked on. If you don't find a similar idea, create a new issue describing your idea. Once we agree on the feature scope and architecture, the feature will be ready for building. Don't hesitate to mention this in the issue if you'd like to build the feature yourself.

## You have a suggestion for improving an existing command

Nothing is perfect. If you have an idea for how to improve an existing command or the CLI itself, let us know by submitting an issue in the [issue list](https://github.com/pnp/cli-microsoft365/issues). We value your input. Some things are done for a reason, but some are not. Let's discuss what you think and see how the project could be improved for everyone.

## You've found a bug

Bugs happen. When you find a bug, please have a look at the [issue list](https://github.com/pnp/cli-microsoft365/issues) to validate if a similar bug has already been logged. This helps avoid duplicate bug reports. If you don't find a similar bug report, let us know what isn't working and provide steps to reproduce it. If we can't reproduce your bug, we will ask you for clarification, which will only delay the resolution.

## Fixing typos

Typos are embarrassing! Most PRs that fix typos will be accepted immediately. To make it easier to review the PR, please narrow the focus instead of sending a huge PR of fixes.

## DO's & DON'Ts

- **DO** follow the same project and test structure as the existing project.
- **DO** include tests when adding new functionality and features. When fixing bugs, start by adding a test that highlights how the current behavior is broken.
- **DO** keep discussions focused. When a new or related topic comes up, it's often better to create a new issue than to side-track the conversation.
- **DO NOT** submit PRs for coding style changes. These changes can cause unnecessary conflicts and make the review process more complicated.
- **DO NOT** surprise us with big PRs. Instead, file an issue and start a discussion so we can agree on a direction before you invest a large amount of time.
- **DO NOT** commit code you didn't write. We encourage you to contribute your own work to maintain

## Contribution paths

Before you start contributing, it's important to ensure that your environment is set up correctly. We recommend you to use GitHub Codespaces or our dev container described in this guide: [GitHub Codespaces & Visual Studio Remote Development Container](./github-codespaces-and-devcontainer.mdx). Alternatively, you can refer to the extensive guide on how to achieve this locally: [Setting up your environment](./environment-setup.mdx).

### Adding a new command

Once your environment is set up, you can learn how to add a new command to the CLI for Microsoft 365 by following these steps:

1. [New Command Sample](./new-command/step-by-step-guide.mdx)
2. [Command Logic](./new-command/build-command-logic.mdx)
3. [Unit Tests](./new-command/unit-tests.mdx)
4. [Help Page](./new-command/writing-the-docs.mdx)
5. [Submitting the Pull Request (PR)](./creating-the-pr.mdx)

### Adding a new script sample

Explore the process of adding a new script sample to the CLI for Microsoft 365 with the following steps:

1. [Adding a Script Sample](./script-sample/new-script-sample.mdx)
2. [Submitting the Pull Request (PR)](./creating-the-pr.mdx)
