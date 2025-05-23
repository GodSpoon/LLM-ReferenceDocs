-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
title: Use CLI for Microsoft 365 context
sidebar_position: 16
---

# Use CLI for Microsoft 365 context

CLI for Microsoft 365 context provides unique functionality to save options and their values in a central place. The options saved in the context may be used in any kind of command execution. This means you may provide fewer options or no options at all. Using a context will help you save on keystrokes.
It may be especially useful if you want to group all your script parameters in a single place.
A context is saved in a m365rc.json file in your working directory. It can be committed to Source Control along with your script files. It can be managed by executing commands.

## How to get started

To create an empty context we may execute the following command:

```powershell
m365 context init
```

To add or update an option in the context use the `m365 context option set` command. The `name` is used to define the option name and `value` is used to define its default value. For example, if we want to set the option `listTitle` to `test list`, we should execute:

```powershell
m365 context option set --name 'listTitle' --value 'test list'
```

To remove a specific option from the context we can run:

```powershell
m365 context option remove --name "listTitle"
```

In order to remove the full context we may execute the following command:

```powershell
m365 context remove
```

## How does it work

When a command is executed, the CLI will first check for the `.m365rc.json` file in the working directory. If present, the CLI will check if any of the options defined in it may be used for the currently executed command. If that's the case the CLI will execute this command with the option and its value taken from the context.

When an option is available in the context and also used in the command itself, the value defined in the command will take precedence.

## Example

Consider the below context:

```json
{
  "context": {
    "groupName": "Sales group",
    "listTitle": "Expense tracker"
  }
}
```

When we execute:

```powershell
m365 context option set --name "webUrl" --value "https://contoso.sharepoint.com/sites/sales"
```

The result of the above will be a new option added to the context:

```json
{
  "context": {
    "groupName": "Sales group",
    "listTitle": "Expense tracker",
    "webUrl": "https://contoso.sharepoint.com/sites/sales"
  }
}
```

Next, if we execute the following:

```powershell
m365 spo listitem list
```

As a result, we will get a list of items from `Expense tracker` list from `https://contoso.sharepoint.com/sites/sales` even though we did not specify any of the required options, those were taken from the context.

Now when we execute:

```powershell
m365 spo listitem list --listTitle "Issue tracker"
```

We will get all items from list `Issue tracker` from `https://contoso.sharepoint.com/sites/sales` site.

If we execute:

```powershell
m365 spo list get
```

The command will fail. Although the `webUrl` option will be used, which is the required one, but the `listTitle` will not be used as the command needs `title` option instead to get the specified list.

## Related commands

- [m365 context init](../cmd/context/context-init.mdx)
- [m365 context remove](../cmd/context/context-remove.mdx)
- [m365 context option set](../cmd/context/option/option-set.mdx)
- [m365 context option list](../cmd/context/option/option-list.mdx)
- [m365 context option remove](../cmd/context/option/option-remove.mdx)
