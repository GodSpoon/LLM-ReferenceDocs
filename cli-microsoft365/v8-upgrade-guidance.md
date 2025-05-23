-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# v8 Upgrade Guidance

The v8 of CLI for Microsoft 365 introduces several breaking changes. To help you upgrade to the latest version of CLI for Microsoft 365, we've listed those changes along with any actions you may need to take.

## Power Automate

### Adjusted output of `flow list` command

For this new major version, we've adjusted the output of the `flow list` command. The command now returns a list of flows in the given environment. When specifying the `--asAdmin` option, the command will return a slightly different result. We had to take this action due to the deprecation of the previous API.

Note that we also made some slight changes when you are not running the command as admin. The command will always give an output, even if no flows exist in your specified environment. We also removed a redundant property in the result. Instead of referencing the `displayName` property, you should now use `properties/displayName`.

#### What action do I need to take?

Please, check the documentation of the [flow list](./cmd/flow/flow-list.mdx) command to see the updated output and adjust your scripts accordingly.

## SharePoint

### Updated command output of `spo group member add`

Due to issues with the current endpoint, we have moved the `spo group member add` command to a new endpoint. This change is necessary to ensure the command's functionality and reliability. Because of the new endpoint, the command output has changed.

#### What action do I need to take?

The command is not backward compatible with the previous endpoint. This results in different command outputs. Users must update their scripts and automation tools to the new command output. More info can be found in the docs of the [spo group member add](./cmd/spo/group/group-member-add.mdx) command.
