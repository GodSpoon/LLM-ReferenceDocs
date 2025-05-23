-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# v5 Upgrade Guidance

The v5 of CLI for Microsoft 365 introduces several breaking changes. To help you upgrade to the latest version of CLI for Microsoft 365, we've listed those changes along with any actions you may need to take.

## Entra ID related commands migrated to Microsoft Graph

In CLI for Microsoft 365 we have commands that allow you to manage Entra apps. Some of these commands were using the Entra Graph API, which has been [deprecated](https://docs.microsoft.com/graph/migrate-azure-ad-graph-faq#EXAMPLE_SECRET_VALUE_PLACEHOLDER) since June 30, 2020 and which will be retired on June 30, 2022. To guarantee that the CLI for Microsoft 365 will keep working, we migrated the affected commands to use the Microsoft Graph. Here's the list of the affected commands:

- [entra oauth2grant list](./cmd/entra/oauth2grant/oauth2grant-list.mdx)
- [entra enterpriseapp get](./cmd/entra/enterpriseapp/enterpriseapp-get.mdx)

### What action do I need to take?

While the options of the commands haven't changed, the data returned by the command might be different. If you use either command in a script, please verify that the script is working as intended. Here are the differences in the data returned by the [entra oauth2grant list](https://docs.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER#EXAMPLE_SECRET_VALUE_PLACEHOLDER) and [entra enterpriseapp get](https://docs.microsoft.com/graph/EXAMPLE_SECRET_VALUE_PLACEHOLDER#serviceprincipal-property-differences) commands.

## In `entra oauth2grant list` renamed `clientId` to `spObjectId`

In the [entra oauth2grant list](./cmd/entra/oauth2grant/oauth2grant-list.mdx) command, we used to have the `clientId` option to specify the `objectId` of the service principal. The name was confusing and not self-explanatory, which is why we decided to rename it to `spObjectId`. The value of the option is the same. It's just the name of the property that changed.

### What action do I need to take?

If you use the `entra oauth2grant list` command, replace the `clientId` option with `spObjectId`.

## Extended `entra oauth2grant remove` with `confirm`

In CLI for Microsoft 365, removing an object is non-reversible. To prevent accidental removal, all remove commands include a prompt which can be suppressed using the `confirm` option. The `entra oauth2grant remove` command didn't show the prompt and used to delete the grant directly. To align the command with other commands in the CLI, we extended it with the `confirm` option and showing a confirmation prompt when the `confirm` option hasn't been specified.

### What action do I need to take?

If you use the `entra oauth2grant remove` command in your scripts, extend it with the `--confirm` option to suppress the prompt and ensure that the script will run without requiring user interaction.
