<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - SPFX Commands Reference

*This is an automatically generated condensed reference of all SPFX commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [package-generate](#package-generate)
- [project-azuredevops-pipeline-add](#project-azuredevops-pipeline-add)
- [project-doctor](#project-doctor)
- [project-externalize](#project-externalize)
- [project-github-workflow-add](#project-github-workflow-add)
- [project-permissions-grant](#project-permissions-grant)
- [project-rename](#project-rename)
- [project-upgrade](#project-upgrade)
- [spfx-doctor](#spfx-doctor)

---

## package-generate

### Syntax
```
m365 spfx package generate
```

### Example
```
m365 spfx package generate --webPartTitle "Amsterdam weather" --webPartDescription "Shows weather in Amsterdam" --name amsterdam-weather --html @amsterdam-weather.html --allowTenantWideDeployment --enableForTeams all

```

---

## project-azuredevops-pipeline-add

### Syntax
```
m365 spfx project azuredevops pipeline add [options]
```

### Example
```
m365 spfx project azuredevops pipeline add

m365 spfx project azuredevops pipeline add --loginMethod "user"

m365 spfx project azuredevops pipeline add --scope "sitecollection" --siteUrl "https://some.sharepoint.com/sites/someSite"

```

### Remarks
The `spfx project azuredevops pipeline add` will create a workflow .yml file in the `.azuredevops/pipelines` directory in your project. If such directory does not exist the command will automatically create it.

The command will not create the Azure DevOps pipeline. You will need to manually create it in Azure DevOps. The command will only create the workflow file which you can then push to your repo and create a new yaml pipline based on it.

For the `application` login method the command does not register an Entra application nor does it create the required certificate. In order to proceed, obtain (create) a self-signed certificate and register a new Entra application with certificate authentication. After that you will need to fill the following variables, or what is more preferable, create a dedicated variable group to store those properties:

This use case is perfect in a production context as it does not create any dependencies on an account

For the `user` login method you will need to fill the following variables, or what is more preferable, create a dedicated variable group to store those properties:

This method is perfect to test your workflow, in a dev context, for personal usage. It will not work for accounts with MFA.

:::info

Run this command in the SPFx solution folder.

:::



---

## project-doctor

### Syntax
```
m365 spfx project doctor [options]
```

### Example
```
m365 spfx project doctor --output md > "doctor-report.md"

m365 spfx project doctor --output text

m365 spfx project doctor --packageManager pnpm --output text

m365 spfx project doctor --output tour

```

### Remarks
The `spfx project doctor` command helps you validate that your SharePoint Framework project is set up correctly. The command automatically detects the version of your project using version information specified in the project's .yo-rc.json file or package.json (if no version information is included in .yo-rc.json). Based on the detected project version, the command executes several checks and reports any issues in the specified format.

This command doesn't change your project files. Instead, it gives you a report with all steps necessary to validate your project to the specified version of the SharePoint Framework. Changing project files is error-prone, especially when it comes to updating your solution's code. This is why at this moment, this command produces a report that you can use yourself to perform the necessary updates and verify that everything is working as expected.

:::info

Run this command in the folder where the project that you want to validate is located. This command doesn't change your project files.

:::



---

## project-externalize

### Syntax
```
m365 spfx project externalize [options]
```

### Example
```
m365 spfx project externalize --output md > "deps-report.md"

m365 spfx project externalize

```

### Remarks
:::info

Run this command in the folder where the project for which you want to externalize dependencies is located. This command doesn't change your project files.

:::

:::warning

This command is in preview and could change once it's officially released. If you see any room for improvement, we'd love to hear from you at [https://github.com/pnp/cli-microsoft365/issues](https://github.com/pnp/cli-microsoft365/issues).

:::

The `spfx project externalize` command helps you externalize your SharePoint Framework project dependencies using the [unpkg CDN](https://unpkg.com/).

This command doesn't change your project files. Instead, it gives you a report with all steps necessary to externalize your project dependencies. Externalizing project dependencies is error-prone, especially when it comes to updating your solution's code. This is why at this moment, this command produces a report that you can use yourself to perform the necessary changes and verify that everything is working as expected.

Supported SharePoint Framework versions are 1.0.0, 1.0.1, 1.0.2, 1.1.0, 1.1.1, 1.1.3, 1.2.0, 1.3.0, 1.3.1, 1.3.2, 1.3.4, 1.4.0, 1.4.1, 1.5.0, 1.5.1, 1.6.0, 1.7.0, 1.7.1, 1.8.0, 1.8.1, 1.8.2, 1.9.1.



---

## project-github-workflow-add

### Syntax
```
m365 spfx project github workflow add [options]
```

### Example
```
m365 spfx project github workflow add 

m365 spfx project github workflow add --manuallyTrigger --loginMethod "user"

m365 spfx project github workflow add --scope "sitecollection" --siteUrl "https://some.sharepoint.com/sites/someSite"

```

### Remarks
The `spfx project github workflow add` will create a workflow .yml file in the `.github/workflows` directory in your project. If such directory does not exist the command will automatically create it.

For the `application` login method the command does not register a Microsoft Entra application nor create the required certificate. In order for you to proceed you will need to first obtain (create) a self-signed certificate and register a new Microsoft Entra application with certificate authentication. After that in GitHub repo settings, you will need to create the following secrets:

This use case is perfect in a production context as it does not create any dependencies on an account

For the `user` login method you will need to create the following secrets in GitHub repo settings:

This method is perfect to test your workflow, in a dev context, for personal usage. It will not work for accounts with MFA.

The workflow will overwrite the existing .sppkg if it is already deployed in the app catalog. Overwriting your sppkg file on every deployment is required to make continuous delivery of the latest version of your app which is the aim of the continuous delivery pipeline.

:::info

Run this command in the SPFx solution folder.

:::



---

## project-permissions-grant

### Syntax
```
m365 spfx project permissions grant [options]
```

### Example
```
m365 spfx project permissions grant

```

### Remarks
:::info

Run this command in the folder where the project is located from where you want to grant the permissions.

:::

This command grant the permissions defined in: _package-solution.json_.



---

## project-rename

### Syntax
```
m365 spfx project rename [options]
```

### Example
```
m365 spfx project rename --newName contoso

m365 spfx project rename --newName contoso --generateNewId

```

### Remarks
:::info

Run this command in the folder where the project that you want to rename is located.

:::

This command will update the project name in: _package.json_, _.yo-rc.json_, _package-solution.json_, _deploy-azure-storage.json_ and _README.md_.



---

## project-upgrade

### Syntax
```
m365 spfx project upgrade [options]
```

### Example
```
m365 spfx project upgrade --toVersion 1.5.0 --output md > "upgrade-report.md"

m365 spfx project upgrade --toVersion 1.5.0 --output text

m365 spfx project upgrade --preview --output text

m365 spfx project upgrade --toVersion 1.12.1-rc.0 --output text

m365 spfx project upgrade --packageManager pnpm --output text

m365 spfx project upgrade --output text

m365 spfx project upgrade --shell powershell --output text

m365 spfx project upgrade --output tour

```

### Remarks
The `spfx project upgrade` command helps you upgrade your SharePoint Framework project to the specified version. If no version is specified, the command will upgrade to the latest version of the SharePoint Framework it supports (v1.21.1).

This command doesn't change your project files. Instead, it gives you a report with all steps necessary to upgrade your project to the specified version of the SharePoint Framework. Changing project files is error-prone, especially when it comes to updating your solution's code. This is why at this moment, this command produces a report that you can use yourself to perform the necessary updates and verify that everything is working as expected.

:::info

Run this command in the folder where the project that you want to upgrade is located. This command doesn't change your project files.

:::



---

## spfx-doctor

### Syntax
```
m365 spfx doctor [options]
```

### Example
```
m365 spfx doctor --output text

m365 spfx doctor --env sp2019 --output text

m365 spfx doctor --spfxVersion 1.11.0 --output text

m365 spfx doctor --spfxVersion 1.11.0 --output json

```

### Remarks
This commands helps you to verify if your environment meets all prerequisites for building solutions using a particular version of the SharePoint Framework.

The command starts by detecting the version of SharePoint Framework that you want to use. First, it looks at the current project. If you didn't run the command in the context of a SharePoint Framework project, the command will try to determine the SharePoint Framework version based on the SharePoint Framework Yeoman generator that you have installed either in the current directory or globally.

Based on the determined version of the SharePoint Framework, the command will look at other dependencies such as Node.js, npm, Yeoman, Gulp CLI and TypeScript to verify if their meet the requirements of that particular version of the SharePoint Framework.

If you miss any required tools or use a version that doesn't meet the SharePoint Framework requirements, the command will give you a list of recommendation how to address these issues.

Next to verifying the readiness of your environment to use a particular version of the SharePoint Framework, you can also check if the version of the SharePoint Framework that you use is compatible with the specific version of SharePoint. Supported versions are `sp2016`, `sp2019` and `spo`.

:::info

Checks ran by this command are based on what is officially supported by Microsoft. It's possible that using different package managers or packages versions will work just fine.

:::

:::info

This command supports only text or json output.

:::



---
