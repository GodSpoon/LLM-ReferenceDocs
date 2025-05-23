-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# v9 Upgrade Guidance

The v9 of CLI for Microsoft 365 introduces breaking change in default login method. To help you upgrade to the latest version of CLI for Microsoft 365, we've listed this change along with any actions you may need to take.

## CLI

### Updated login command default behavior

When running `m365 login` CLI will now first check if you defined the `appId` which is now required to your own single tenant Entra app registration.

#### What action do I need to take?

`appId` may be defined in several ways: as an option passed to the `login` command, as a `clientId` CLI setting, or as an environment variable. If you have not defined the `appId` in any of these ways, you will need to do so to continue using the CLI in your scripts.
