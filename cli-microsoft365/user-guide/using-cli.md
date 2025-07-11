-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
title: Use the CLI
sidebar_position: 2
---

import AsciinemaPlayer from '../../src/components/AsciinemaPlayer';
import 'asciinema-player/dist/bundle/asciinema-player.css';

# Use the CLI for Microsoft 365

Information in this section will help you understand how the CLI for Microsoft 365 works and how you can use it most effectively.

## Start the CLI

To use CLI for Microsoft 365, execute specific commands directly from the command line.

<AsciinemaPlayer src="https://asciinema.org/a/445654.cast" rows={20} idleTimeLimit={3} preload={true} loop autoplay/>

<br/>

:::warning

When using the CLI for Microsoft 365, each CLI command must be prepended with `microsoft365` or `m365` for short. Without this, your shell will not know how the particular command should be executed.

:::

Using the CLI for Microsoft 365 directly from the command line is invaluable if you want to write scripts consisting of a number of CLI for Microsoft 365 and other commands combined together. Additionally, you keep the access to all system commands and other CLIs available on your computer.

## List available commands

To list commands available with the CLI for Microsoft 365 type `help` in the CLI prompt, or `m365 help` directly in your shell.

Commands in the CLI for Microsoft 365 are combined into groups. You can list the commands available in the particular group by typing `help <group>`, for example `help spo` to list all commands related to SharePoint Online, or `m365 help spo` directly in your shell.

<AsciinemaPlayer src="https://asciinema.org/a/445655.cast" rows={20} idleTimeLimit={3} preload={true} loop autoplay/>

## Get command help

Each command in the CLI for Microsoft 365 comes with help describing the command's purpose, available options and any other relevant details as well as related resources. To get the basic help information with command's description and available options, type `help <command>` or `m365 help <command>` in the shell, for example to get help for the `spo cdn get` command, type in the shell `m365 help spo cdn get`.

To get the complete help information including background information, examples and links to related information, use the `--help` option, for example `m365 spo cdn get --help`. This ability is also useful if you've already typed some options and don't want to lose your input but want to access the help, for example: `m365 spo cdn get --type Private --help`.

<AsciinemaPlayer src="https://asciinema.org/a/445656.cast" rows={20} idleTimeLimit={3} preload={true} loop autoplay/>

## Required and optional command options

Commands in the CLI for Microsoft 365 often contain options that determine what the particular command should do. Command options vary from the URL of the site for which you would like to retrieve more information, to the type of Microsoft 365 CDN that you would like to manage.

Some options are required and necessary for the particular command to execute, while other are optional. When listing available options for the particular command, CLI for Microsoft 365 follows the naming convention where required options are wrapped in angle brackets (`< >`) while optional options are wrapped in square brackets (`[ ]`). For example, in the `spo cdn origin add` command, the origin you want to add is required (`-r, --origin <origin>`), while the type of CDN for which this origin should be added is optional (`-t, --type [type]`) and its value defaults to `Public`.

## Boolean options (true/false)

Some options in the CLI expect boolean values like `true` or `false`. The CLI for Microsoft 365 has the following definition for booleans:

:::info[Definition of Booleans]

Booleans are case-insensitive and are represented by the following values.  
True: 1, yes, true, on  
False: 0, no, false, off

:::

This means that whenever you need to pass a boolean value to a command, you can use any of the values listed above. For example, to configure if Planner is allowed in your organization you can execute the following:

```sh
m365 planner tenant settings set --isPlannerAllowed true
m365 planner tenant settings set --isPlannerAllowed 1
m365 planner tenant settings set --isPlannerAllowed yes
m365 planner tenant settings set --isPlannerAllowed on
m365 planner tenant settings set --isPlannerAllowed TRUE

m365 planner tenant settings set --isPlannerAllowed false
m365 planner tenant settings set --isPlannerAllowed 0
m365 planner tenant settings set --isPlannerAllowed no
m365 planner tenant settings set --isPlannerAllowed off
m365 planner tenant settings set --isPlannerAllowed FALSE
```

Additionally, in PowerShell you can use boolean values `$true` and `$false` as well:

```PowerShell
m365 planner tenant settings set --isPlannerAllowed $true
m365 planner tenant settings set --isPlannerAllowed $false
```

## Values with quotes

In cases, when the option's value contains spaces, it should be wrapped in quotes. For example, to create a modern team site for the _CLI for Microsoft 365_ team, you would execute in the shell:

```sh
m365 spo site add --alias office365cli --title "CLI for Microsoft 365"
```

When the value, that you want to provide contains quotes, it needs to be wrapped in quotes as well, for example to pass a JSON value in the CLI prompt, you would execute:

```sh
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content '{"abc": "def"}'
```

## Values starting with a dash (-)

In cases, when the option's value starts with a dash (-), specify the option's value using the `=` operator. For example, to get a planner task with ID _-9rMKQooUjZdxgv1qQVZYABEuw_, execute in the shell:

```sh
m365 planner task get --id=-9rMKQooUjZdxgv1qQVZYABEuw
```

## Setting empty values

In cases, when the option's value is empty, specify the value using the `=` operator. For example, to pass an empty string argument to option `description`, you should execute:

```sh
m365 spo contenttype set --description=""
```

## Working with SharePoint URLs in `spo` commands

CLI for Microsoft 365 contains a number of commands for managing SharePoint Online. Each of these commands requires you to specify the site or web on which you want to execute the command. For example, to get information about a site collection located at `https://contoso.sharepoint.com/sites/contoso`, you'd execute:

```sh
m365 spo site get --url https://contoso.sharepoint.com/sites/contoso
```

If you executed an `spo` command previously, CLI for Microsoft 365 already knows the hostname of your SharePoint Online tenant. In such case, you can use a server-relative URL as well:

```sh
m365 spo site get --url /sites/contoso
```

If you try to use a server-relative URL but CLI for Microsoft 365 doesn't know of your SharePoint Online URL yet, you will see an error prompting you to either use an absolute URL or set the SPO URL using the `spo set` command:

```sh
m365 spo set --url https://contoso.sharepoint.com
```

You can also execute a command like `m365 spo site list` that will automatically detect your SharePoint Online tenant URL for you.

To check if CLI detected the SPO URL previously, use the `m365 spo get` command.

## Passing complex content into CLI options

When passing complex content into CLI options, such as JSON strings, you will need to properly escape nested quotes. The exact way to do it, depends on the shell that you're using. Alternatively, you can choose to pass complex content by storing the complex content in a file and passing the path to the file prefixed with an `@`, for example:

```sh
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content @themeScript.json
```

CLI for Microsoft 365 will load the contents from the specified file and use it in the command that you specified.

You can use the `@` token in any command, with any option that accepts a value.

`@` is a special character in PowerShell. If you use CLI for Microsoft 365 in PowerShell and want to use the `@` token, you'll need to escape with a backtick, for example:

```powershell
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content `@themeScript.json
```

## Escaping double quotes in PowerShell

PowerShell Versions 5 to 7.2 have an [issue with escaping double quotes](https://github.com/PowerShell/PowerShell/issues/1995). Command arguments are being parsed twice for tools like the CLI. Once by PowerShell and once by the CLI for Microsoft 365 executable that's being called by PowerShell. The result is that you need to escape quotes twice. The issue should be resolved from version 7.3.

As an example, see the following code: 

```PowerShell
m365 spo listitem set --webUrl "<some-url>" --id 1 --listTitle somelist --SomeField "{ `"test1`": `"test2`" }"
```

While correctly escaped, it would result in the following being saved to sharepoint: `{ test1: test2 }`. The double quotes are missing.

The following two methods resolve this:

### Method 1: Escaping twice

Escape the double quotes twice. Once for powershell using the backtick (`) and once for the executable, using a backslash.

```PowerShell
m365 spo listitem set --webUrl "<some-url>" --id 1 --listTitle somelist --SomeField "{ \`"test1\`": \`"test2\`" }"
```

### Method 2: Using verbatim strings with single quotes

Use single quotes to start a verbatim string. The double quotes need not be escaped for powershell using the backtick. However, they do need to be escaped for the executable, using a backslash.

```PowerShell
m365 spo listitem set --webUrl "<some-url>" --id 1 --listTitle somelist --SomeField '{ \"test1\": \"test2\" }'
```

:::info

Remember, instead of escaping, it's also possible to [feed complex content from a file](./using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER). 

:::

## Handling errors in PowerShell

CLI for Microsoft 365 by default outputs errors to stderr. Unlike other shells, PowerShell works differently as it has six distinct output streams. This behavior can lead to unexpected results, such as PowerShell continuing execution even after setting $ErrorActionPreference = "Stop". For more information on PowerShell's output streams, see [handling output and errors](https://learn.microsoft.com/en-us/powershell/scripting/learn/shell/running-commands?view=powershell-7.5#handling-output-and-errors). To address these differences, you can use the following settings and helper function to ensure that CLI errors are treated as errors.

```PowerShell
# setting output to json
m365 cli config set --key output --value json
# changing error output to stdout
m365 cli config set --key errorOutput --value stdout 
# don't show help on command failure
m365 cli config set --key showHelpOnFailure --value false 
# don't print errors as plain text but as objects
m365 cli config set --key printErrorsAsPlainText --value false 

function Invoke-CLICommand {
  [cmdletbinding()]
  param(
    [parameter(Mandatory = $true, ValueFromPipeline = $true)] $input
  )

  $output = $input

  if ($null -eq $output) {
    return $null
  }

  $parsedOutput = $output | ConvertFrom-Json

  if ($parsedOutput -isnot [Array] -and $null -ne $parsedOutput.error) {
    throw $parsedOutput.error
  }

  return $parsedOutput
}
```

With the above settings and helper function, you can now use a `try/catch` block to gracefully handle errors that may occur when running CLI for Microsoft 365 commands in PowerShell.

```PowerShell
try {
  m365 spo list get --webUrl "https://contoso.sharepoint.com/sites/Marketing" --title "Non Existent" | Invoke-CLICommand
}
catch {
  Write-Host "Failed retrieving list." -ForegroundColor Red
  Write-Host "Error: $($_.Exception.Message)" -ForegroundColor Red
}
```

## `@meId` and `@meUserName` tokens

CLI for Microsoft 365 contains a number of commands that require you to provide a user ID or username. If you want to pass these values for the current user, instead of looking them up, you can use the built-in tokens. With the `@meId` token you can specify the ID of the current user. Using the `@meUserName` token you can specify the username of the current user.

For example:

```sh
m365 entra user get --id "@meId"
```

will execute as `m365 entra user get --id "d1a97db6-ab08-41a9-94fe-bfa104e83f69"`.

When you execute:

```sh
m365 entra user get --userName "@meUserName"
```

it will run as `m365 entra user get --userName "admin@contoso.onmicrosoft.com"`.

Both tokens are resolved based on the information stored in the access token. You can use the `@` token in any command, with any option that accepts a value.

## Verbose and debug mode

By default, commands output only the information returned by the corresponding Microsoft 365 API, whether the command result or error. You can choose for a more user-friendly output by using the `--verbose` option or setting the `CLIMICROSOFT365_VERBOSE` environment variable to `1`. For example: by default, when checking status of the Microsoft 365 Public CDN, you would see:

```sh
$ m365 spo cdn get
true
```

After adding the `--verbose` option, the output would change to:

```sh
$ m365 spo cdn get --verbose
Retrieving status of Public CDN...
Public CDN at https://contoso-admin.sharepoint.com is enabled
```

If you're experiencing problems when using the CLI for Microsoft 365, you can use the `--debug` option or set the `CLIMICROSOFT365_DEBUG` environment variable to `1`. On top of the output from the verbose mode, the debug mode will provide you with detailed information about all requests and responses from the Microsoft 365 APIs used by the command.

## Command completion

To help you use its commands, CLI for Microsoft 365 offers you the ability to autocomplete commands and options that you're typing in the prompt. Some additional setup, specific for the shell and terminal that you use, is required to enable command completion for CLI for Microsoft 365. For more information on configuring command completion for the CLI for Microsoft 365 see the [command completion](completion.mdx) article.

## Disable automatic checking for updates

Each time you run CLI for Microsoft 365, it will automatically check if there is a new version available and prompt you with update instructions if that's the case. If you use CLI for Microsoft 365 in CI/CD or in scripts and want to make it run faster, you can disable the check by setting the `CLIMICROSOFT365_NOUPDATE` environment variable to `1`.
