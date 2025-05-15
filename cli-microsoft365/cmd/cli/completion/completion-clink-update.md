-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# cli completion clink update

Updates command completion for Clink (cmder)

## Usage

```sh
m365 cli completion clink update [options]
```

## Options

<Global />

## Remarks

This commands updates the list of commands and their options used by command completion in Clink (cmder). You should run this command each time after upgrading the CLI for Microsoft 365.

:::info

Before running this command, change the working directory to where your shell stores completion plugins. For cmder, it's `%CMDER_ROOT%endor