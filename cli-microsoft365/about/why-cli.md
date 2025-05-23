-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
sidebar_position: 1
---

# Why this CLI?

CLI for Microsoft 365 is a cross-platform CLI that allows users on any platform to manage various configuration settings of Microsoft 365.

- Intuitive! If you would like to `add` a new `SharePoint Online` `list` simply write `m365 spo list add` and if you need to do a different action like modifying the list or retrieving it simply change the verb to: `get`, `set`, `remove` etc. 
- Interactive by default. Starting to use a new CLI is never easy, that's why CLI for Microsoft 365 offers an interactive mode that actively asks (prompts) you for the required options of a command you want to run. You may also [configure autocomplete for commands](../user-guide/completion.mdx) and options that you're typing in the prompt for almost any terminal.
- Managing multiple [connections](../cmd/connection/connection-list)! CLI for Microsoft 365 allows you to sign in to multiple accounts and tenants and just switch between those connections. This means you no longer need to sign out and in when you want to switch to a different tenant.
- [Different output modes](../user-guide/cli-output-mode.mdx) allow you to choose how you want to see the results of your commands. You can choose between `json` which is optimized to be used in a script when the output of one command will be used as an input to another command, `text` which is perfect for human reading, and `csv` or even `md` (markdown) which is suitable to create a report based outcome.
- Runs on any device in any shell. CLI for Microsoft 365 runs on Node.js and you can run it on any device and in any shell.  
- You may use it in CI/CD pipelines. It integrates easily with Azure DevOps and natively with GitHub workflows. CLI has dedicated [GitHub actions](../user-guide/github-actions) which you may use directly in GitHub workflow and it allows you to scaffold a pipeline for [Azure DevOps](../cmd/spfx/project/project-azuredevops-pipeline-add) and [GitHub workflows](../cmd/spfx/project/project-github-workflow-add).
- ***[Manage SharePoint Framework solutions](../cmd/spfx/spfx-doctor)***. CLI for Microsoft 365 will help you setup your local environment for SPFx development and will help you with common tasks when developing SPFx solutions, like validating its correctness or getting guidance on how to upgrade it.
- Make [CLI for Microsoft 365 your own](../user-guide/configuring-cli). CLI for Microsoft 365 offers a variety of settings that will allow you to customize it for your specific use case or needs. If going over the settings is challenging, then you will love the [m365 setup](../cmd/setup) command that will help you customize CLI for common use cases like setting it to be tailored to be run in a script.
- AI, of course, we have AI! CLI for Microsoft 365 comes along with an [AI assistant chili 🌶️](../user-guide/chili) that will help you find the right commands for your tasks.
- How many CLIs allow you to run them as an API in your app? Exactly! [CLI for Microsoft 365 can be used as an API](../user-guide/use-cli-api) in your Node.js app.
- You may filter and sort the output of every command. [Filtering and sorting](../user-guide/filter-cli-data.mdx) is a powerful feature that allows you to get only the data you need and in the order you want.
- Using the [verbose and debug modes](../user-guide/using-cli/#verbose-and-debug-mode) you may get more details about the command execution making everything super transparent what CLI for Microsoft 365 is performing under the hood.
- CLI for Microsoft 365 offers a variety of commands from many different areas of Microsoft 365, for example:
  - [Entra ID](../cmd/entra/administrativeunit/administrativeunit-add)
  - [OneDrive](../cmd/onedrive/onedrive-list)
  - [OneNote](../cmd/onenote/notebook/notebook-add)
  - [Outlook](../cmd/outlook/mail/mail-send)
  - [Planner](../cmd/planner/bucket/bucket-add)
  - [Power Apps](../cmd/pa/app/app-export)
  - [Power Automate](../cmd/flow/flow-disable)
  - [Power Platform](../cmd/pp/aibuildermodel/aibuildermodel-get)
  - [SharePoint Embedded](../cmd/spe/containertype/containertype-add)
  - [SharePoint Online](../cmd/spo/spo-get)
  - [Teams](../cmd/teams/app/app-install)
  - [Viva engage](../cmd/viva/engage/engage-search)
  - and many more...

  Benefits of combining all these areas into single tool:
  - **Consistency**: Manage all areas in the same way, rather than having to learn how each tool for each area works.
  - **Interoperability**: Login once, manage everything, and easily pass values from one command in one area to another in another area.
  - **Convenience**: Install, manage, and learn a single tool.

Interested in more? Start with our [user guide](../user-guide/using-cli.mdx) and learn how to use the CLI for Microsoft 365.

## Why not another approach or a different CLI?

### Why not just do things manually?

Using CLI for Microsoft 365 is not about replacing the UI, it's about making your life easier. If you need to do a repetitive task, like creating a new SharePoint list every time a new project is started, you can create a script and automate this task with CLI for Microsoft 365. This way you can save time and avoid human errors.

### Why not just write your own CLI or some custom console app tailored to your needs?

You could, but why reinvent the wheel? CLI for Microsoft 365 is a powerful tool that is being actively developed and maintained by a team of experts. It's open-source and free to use. It's also cross-platform and works on any device. It's a great tool that can help you manage your Microsoft 365 tenant more efficiently.

### Why not use SharePoint Online Management Shell?

SharePoint Online Management Shell is a great tool, but it's limited to SharePoint Online and only works with Windows PowerShell. Additionally, it only supports SharePoint administration tasks, so you can only use it to run admin-related commands. In contrast, CLI for Microsoft 365 offers a variety of commands from many different areas of Microsoft 365. It's a more comprehensive tool that can help you manage your Microsoft 365 tenant more efficiently.

### Why not Microsoft Graph CLI or Microsoft Graph PowerShell SDK?

Microsoft Graph CLI and Microsoft Graph PowerShell SDK are amazing, but they are limited to Microsoft Graph API. CLI for Microsoft 365 integrates not only Microsoft Graph but also SharePoint (REST API and CSOM), Azure, Planner, Power Platform, and other APIs. It's a more comprehensive tool that can help you manage your Microsoft 365 tenant more efficiently. Each command documentation is 'handcrafted' not generated code which makes it more human-readable and easier to understand. Last but not least, CLI for Microsoft 365 has commands which are scenario-based and are not just wrappers around Graph API.

### Why not use PnP PowerShell instead?

If you use PowerShell, PnP PowerShell is a convenient solution that you can use to manage different parts of Microsoft 365. CLI for Microsoft 365 offers additional flexibility with the ability to run it in any shell. CLI for Microsoft 365 also offers unique commands to manage SPFx solutions. Whether you're a beginner or an advanced user, and want to use CLI for daily interactive use or scripting, you can configure CLI for Microsoft 365 to your needs making an invaluable tool in your toolbox. CLI for Microsoft 365 offers interactive mode by default which will actively prompt you for required options. CLI for Microsoft 365 is also more intuitive since all commands are grouped into areas like `spo` for SharePoint Online or `entra` for Entra ID, which makes it easier to find the command or operation you are looking for.
