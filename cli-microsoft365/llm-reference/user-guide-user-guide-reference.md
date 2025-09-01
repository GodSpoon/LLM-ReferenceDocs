<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - User Guide - user-guide

*This is an automatically generated condensed reference of the user-guide section of the Microsoft 365 CLI User Guide, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [azuredevops-pipeline](#azuredevops-pipeline)
- [chili](#chili)
- [cli-certificate-caveats](#cli-certificate-caveats)
- [cli-output-mode](#cli-output-mode)
- [completion](#completion)
- [configuring-cli](#configuring-cli)
- [connecting-microsoft-365](#connecting-microsoft-365)
- [filter-cli-data](#filter-cli-data)
- [github-actions](#github-actions)
- [installing-cli](#installing-cli)
- [manage-microsoft-365-apps](#manage-microsoft-365-apps)
- [run-cli-in-docker-container](#run-cli-in-docker-container)
- [use-cli-api](#use-cli-api)
- [using-cli](#using-cli)
- [using-cli-context](#using-cli-context)
- [using-cli-vs-code-extension](#using-cli-vs-code-extension)
- [using-own-identity](#using-own-identity)
- [using-proxy-url](#using-proxy-url)

---

## azuredevops-pipeline

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Automate your CI/CD workflow using CLI for Microsoft 365 in Azure DevOps Pipelines
sidebar_position: 13

## Automate your CI/CD workflow using CLI for Microsoft 365 in Azure DevOps Pipelines

CLI for Microsoft 365 may also be used in Azure DevOps pipelines with ease. In the current guide, we will go over a quite popular scenario of creating a pipeline that will allow you to build, package, and deploy our SPFx solution to your tenant. This guidance assumes you already have a project/repo created on Azure DevOps and you have basic knowledge of the platform functionalities.

### Creating a new YAML workflow

The first thing that we will need is a YAML file that will define our pipeline. This should be kept as one of the files in our repositories to which we plan to add the Azure DevOps pipeline. The file may be stored in any folder in the repository, but for Azure DevOps it is recommended to store your pipelines in `.azuredevops/pipelines` folder. Let's create a new file in this location. Let's name it `deploy-spfx-solution.yml`. So after you've done the previous steps your SPFx project folder structure should look like this:

![Project structure](../images/azure-devops-pipeline-tutorial/project-structure.png)

Now let's add the following content to the file:

```
name: Deploy Solution
trigger:
  branches:
    include:
      - main
pool:
  vmImage: ubuntu-latest
variables:
  - name: CertificateBase64Encoded
    value: ""
  - name: CertificatePassword
    value: ""
  - name: EntraAppId
    value: ""
  - name: TenantId
    value: ""
  - name: SharePointBaseUrl
    value: ""
  - name: PackageName
    value: ""
stages:
  - stage: Build_and_Deploy
    jobs:
      - job: Build_and_Deploy
        steps:
          - task: NodeTool@0
            displayName: Use Node.js
            inputs:
              versionSpec: 22.x
          - task: Npm@1
            displayName: Run npm install
            inputs:
              command: install
          - task: Gulp@0
            displayName: Gulp bundle
            inputs:
              gulpFile: ./gulpfile.js
              targets: bundle
              arguments: --ship
          - task: Gulp@0
            displayName: Gulp package
            inputs:
              targets: package-solution
              arguments: --ship
          - task: Npm@1
            displayName: Install CLI for Microsoft 365
            inputs:
              command: custom
              verbose: false
              customCommand: install -g @pnp/cli-microsoft365
          - script: >
              
              m365 login --authType certificate --certificateBase64Encoded '$(CertificateBase64Encoded)' --password '$(CertificatePassword)' --appId '$(EntraAppId)' --tenant '$(TenantId)' 

              m365 spo set --url '$(SharePointBaseUrl)' 

              m365 spo app add --filePath '$(Build.SourcesDirectory)/sharepoint/solution/$(PackageName)' --overwrite 

              m365 spo app deploy --name '$(PackageName)' --appCatalogScope 'tenant'
            displayName: CLI for Microsoft 365 Deploy App

```

This YAML file will define a pipeline that will build, bundle, and package your SPFx solution and then deploy it to your tenant using the CLI for Microsoft 365. Let's go over the file and explain what each part does:

```
name: Deploy Solution
trigger:
  branches:
    include:
      - main
pool:
  vmImage: ubuntu-latest
```

The above part of the YAML file defines the name of the pipeline and the trigger that will start the pipeline. In this case, the pipeline will be triggered on every push to the `main` branch which is a quite typical use case. The last line defines the image that will be used to run the pipeline. In this case, we are using `ubuntu-latest` image.

Now let's move a bit forward. The `variables` section of the YAML file defines the variables that will be used in the pipeline. In general, this is not the best approach to keep the variables values as part of your YAML file, but for the sake of simplicity, we will keep them here. Later on we will show you how to store the variables in Azure DevOps Library.

Next, let's go over the stages and steps of the pipeline:

```
- task: NodeTool@0
  displayName: Use Node.js
  inputs:
    versionSpec: 22.x
- task: Npm@1
  displayName: Run npm install
  inputs:
    command: install
```

The above part is just a standard setup of the Node version we will be using. Currently v22 as this is the latest version we may use for the currently latest version of SPFx which as of now is 1.21.1. Next we are running `npm install` to install all the dependencies of the project.

```
- task: Gulp@0
  displayName: Gulp bundle
  inputs:
    gulpFile: ./gulpfile.js
    targets: bundle
    arguments: --ship
- task: Gulp@0
  displayName: Gulp package
  inputs:
    targets: package-solution
    arguments: --ship
```

The next two steps are just the standard gulp tasks that are used to bundle and package the SPFx solution. Now let's get to the part where it gets interesting:

```
- task: Npm@1
  displayName: Install CLI for Microsoft 365
  inputs:
    command: custom
    verbose: false
    customCommand: install -g @pnp/cli-microsoft365
- script: >
    
    m365 login --authType certificate --certificateBase64Encoded '$(CertificateBase64Encoded)' --password '$(CertificatePassword)' --appId '$(EntraAppId)' --tenant '$(TenantId)' 

    m365 spo set --url '$(SharePointBaseUrl)' 

    m365 spo app add --filePath '$(Build.SourcesDirectory)/sharepoint/solution/$(PackageName)' --overwrite 

    m365 spo app deploy --name '$(PackageName)' --appCatalogScope 'tenant'
  displayName: CLI for Microsoft 365 Deploy App
```

The above part installs the latest version of the CLI for Microsoft 365 and then executes a few commands in a script task.
The first command is of course the authentication. In this case, we will be signing in as an app using a certificate with a password. 
The next command sets the URL of the root SharePoint site for use in SPO commands. 
Then we are using the `spo app add` command to add the SPFx package to, in this case, tenant app catalog. 
The last command, `spo app deploy` deploys the app to the tenant app catalog to make it available for installation and present in the SharePoint online store.

### Adding an Azure DevOps pipeline

Adding your YAML file and committing and pushing it to your repo is not enough to make it an Azure DevOps pipeline. In order to make it a pipeline you will need to go over a few manual steps in the Azure DevOps portal.
Creating a new pipeline in Azure DevOps is a one-time operation and then every time you update the YAML definition Azure DevOps will automatically pick up the changes. In order to create a new pipeline go pipelines page in your Azure DevOps project

![Azure DevOps Navigation](../images/azure-devops-pipeline-tutorial/ado-menu.png)

Next in the top right corner of the page click the `New pipeline` button. After that, follow the form by selecting the location of your repo, next the branch on which the YAML file is present, and then select the option to create a new pipeline based on `Existing Azure Pipelines YAML file`

![Azure DevOps create pipeline steps](../images/azure-devops-pipeline-tutorial/ado-pipeline-manual-steps.png)

After that just confirm the create process and you should see your pipeline in the list of pipelines for your repository.

### Setting up the authentication

The next thing we need is to set up the authentication for the CLI for Microsoft 365. In order to for CLI for Microsoft 365 to be able to deploy an SPFx package from Azure DevOps build artifacts to your SharePoint Online tenant it will need to authenticate as an app, yes as an app, otherwise we would need to use user credentials, and most probably confirm the MFA popup for authentication every time the pipeline runs which is for sure a no go. First, we will need to create an app registration in Entra ID portal and then create a certificate and upload it to the app registration. After that we will need to grant the app registration the necessary permissions in order to be able to deploy the SPFx package to the tenant app catalog. We could do that all manually but luckily for us we may do all that with just a few lines of code using CLI for Microsoft 365.

First, let's create a new certificate which we will need to add to our app registration and later on use in the pipeline for authentication. There are many ways to go about it but if you are using PowerShell you may use the following script to create a new certificate:

```
$cert = New-SelfSignedCertificate -NotBefore $(Get-Date).AddDays(-1) -NotAfter $(Get-Date).AddYears(1) -FriendlyName "CI-CD-Certificate" -CertStoreLocation cert:\CurrentUser\My -Subject "CN=CICDCertificate" -KeyAlgorithm RSA -KeyLength 2048 -KeyExportPolicy Exportable
$cert | Export-Certificate -Type cer -FilePath "temp/CI-CD-Certificate.cer" -Force
```

The above creates a `CI-CD-Certificate.cer` certificate file.
Next, let's get the base64 encoded version of the certificate so that later on we may use it in the pipeline:

```
$password = ConvertTo-SecureString -String $passwordString -Force -AsPlainText
$cert | Export-PfxCertificate -FilePath "temp/CI-CD-Certificate.pfx" -Password $password
$pfxBytes = Get-Content "temp/CI-CD-Certificate.pfx" -AsByteStream -Raw
[System.Convert]::ToBase64String($pfxBytes) | Out-File "temp/CertificateBase64String.txt"
```

The above script will create a `CI-CD-Certificate.pfx` file and then get the base64 encoded version of the certificate and store it in a `CertificateBase64String.txt` file.

Now let's create a new app registration in Entra ID portal and add the certificate to and the necessary permissions. We may do all that with a single line of code:

```
m365 entra app add --name "My CI/CD App Reg" --apisApplication "https://microsoft.sharepoint-df.com/Sites.FullControl.All" --certificateFile ./temp/CI-CD-Certificate.cer --certificateDisplayName "CICD Certificate" --grantAdminConsent
```

That's it. You may go to your Entra ID portal and check if the app registration was created with the necessary permissions and certificate.

### Using Azure DevOps Library

After we created our app registration we could just update the YAML file of the pipeline with the values of the variables that we need to use in the pipeline. But that is not the best approach as the certificate password and the certificate base 64 encoded string will be just visible in the YAML file as plain text and also be part of your git history. In order to avoid that we may use Azure DevOps Library to store the values of the variables in a secure way and use the library in our pipeline. Let's go over the steps of how to do that.

First, we will need to go to Azure DevOps Pipelines Library page and click on the `+ Variable group` button. After that, we will only need to specify the name of our group and we may start by adding variables to it. There are many things you may leverage to make your variables secure like integrating with Azure key vault or specifying a security Azure DevOps group that will only have edit access to the variable group. For the sake of simplicity we will just add the variables to the group and the ones that are considered confidential, like password, we will mark them as secret.

![Azure DevOps Library](../images/azure-devops-pipeline-tutorial/ado-library.png)

After we added all of our variables to the group we may go back to our YAML file and remove all of the variables we specified in the variables section and replace them with the following:

```
variables:
  - group: 'MyVariableGroup'
```

And that's it. Now you may use the variables in your pipeline and they will be stored in a secure way in the Azure DevOps Library.

### Additional support in scaffolding your workflow

If you need help in setting up your workflow we have a command that will do exactly that for your SPFx project. The [m365 project github workflow add](../cmd/spfx/project/project-github-workflow-add) command will add a GitHub workflow to your SPFx project that will build, package, and deploy your solution to your tenant.

---

## chili

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: CLI assistant (chili) 🌶️
sidebar_position: 8

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## CLI assistant (chili) 🌶️

When you're new to CLI for Microsoft 365, it can feel overwhelming. There are so many commands and options to choose from. Where do you start? How do you know which commands to use? It's hard to search for things you don't know exist. So to make it easier, we introduce 🌶️ chili - a CLI docs assistant that helps you find the right commands for your tasks, powered by [Mendable AI](https://www.mendable.ai/).

### Before you start

We believe that 🌶️ chili should be available at your fingertips and super simple to run. That's why we recommend, that after installing CLI for Microsoft 365, you set up an alias for your shell. To add an alias, add to your shell profile:

```
Set-Alias -Name m365? -Value m365_chili
```

```
alias "m365?"="m365_chili"
```

:::tip

If you use our [Docker image](./run-cli-in-docker-container.mdx), you don't need to setup the alias manually. We setup the `m365?` alias for you in both bash and PowerShell.

:::

:::info

If you don't set up an alias, you can still use 🌶️ chili by running `m365_chili` instead of `m365?`.

:::

With this alias in place, you can ask 🌶️ chili anything by running:

```
m365? "how can I upgrade my SPFx project?"
```

You can also start chili without the initial prompt by running `m365?` and then typing your question.

Running this command will start the virtual assistant in the terminal. It will use the question you asked to search in CLI's documentation and answer your question, along with the list of sources from which it found the answer.

After you get an answer, you have the ability to follow up your conversation with additional questions or start from scratch. Start a new conversation to reset the assistant and ensure that it doesn't mix up the context of your questions.

### Options

#### Debug mode

If the command isn't working as expected, you can start it in debug mode by running:

```
m365? --debug
```

or with a prompt:

```
m365? "how can I upgrade my SPFx project?" --debug
```

The command will now print additional information to the terminal, which you can use to troubleshoot the issue.

#### Help

You can print the contents of this page directly in the terminal by running:

```
m365? --help
```

or short:

```
m365? -h
```

---

## cli-certificate-caveats

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Caveats when working with the CLI and certificate login
sidebar_position: 11

## Caveats when working with the CLI and certificate login

### I get error "AADSTS700027 Client assertion contains an invalid signature" when I login the CLI with certificate, what am I doing wrong

There is an article ["Using your own Microsoft Entra identity"](./using-own-identity.mdx) dedicated to using the CLI with your own identity, and you should have a look at it and see if it can help you. Many of the cases we've seen in the GitHub issues list are that people forget to set the `CLIMICROSOFT365_ENTRAAPPID` or `CLIMICROSOFT365_TENANT` environment variables. Setting these variables could be as easy as adding them before your command on the bash command line like `CLIMICROSOFT365_ENTRAAPPID=value1 CLIMICROSOFT365_TENANT=value2 m365 command` (see [#1532](https://github.com/pnp/cli-microsoft365/issues/1532) or [#1496](https://github.com/pnp/cli-microsoft365/issues/1496#issuecomment-625549739)). If you are Windows user the syntax should be like `set CLIMICROSOFT365_ENTRAAPPID=value1` and `set CLIMICROSOFT365_TENANT=value2` then your cli command ([#1121](https://github.com/pnp/cli-microsoft365/issues/1121#issuecomment-533609882)).

### I get "Error: AADSTS700025: Client is public so 'client_assertion' should not be presented"

If you want to authenticate the CLI using and certificate, you shouldn't treat the application as a public client. You should set the default client type your Microsoft Entra application to "NO." More information can be found in this issue [#948](https://github.com/pnp/cli-microsoft365/issues/948#issuecomment-487145809).

### What is the minimum set of Microsoft Entra app permissions to execute SharePoint commands with a certificate CLI login

When you decide to use the CLI with your own Microsoft Entra app to execute SharePoint CLI commands, you need to grant it at least the  Microsoft Graph `Sites.Read.All` permission, and then any other scopes required by the commands you'd like to execute. For example, if you'd like to list all the sites within your tenant using the `m365 spo site list` command, then the minimum permissions for your app would be Microsoft Graph `Sites.Read.All` and SharePoint `Sites.Manage.All`.

[![Microsoft Entra application permissions highlighted in Microsoft Entra ID](../images/cli-certificate-caveats/EXAMPLE_SECRET_VALUE_PLACEHOLDER)](../images/cli-certificate-caveats/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

### I get an error: 403, "AccessDenied Either scp or roles claim need to be present in the token" when executing a CLI for Microsoft 365 SharePoint command. What does it mean

It means that the Microsoft Entra application that the CLI is running under does not have Microsoft Graph `Sites.Read.All` application permission granted. If you are trying to use the CLI with a certificate login and SharePoint, you would have to allow Microsoft Graph `Sites.Read.All` application permissions to the Microsoft Entra app.

### I am using CLI with a certificate, but when I execute the `spo site add` I get error "Insufficient privileges to complete the operation."

This error can occur when you use the CLI with a certificate login and try to create a new SharePoint Team site that uses Microsoft 365 group (WebTemplate: #GROUP). Getting this error is a known issue with the CLI and the SharePoint APIs, but there is a workaround. The workaround is to use the `m365 entra m365group add` command to create Team Sites.

If your goal is to create team sites, you can use the `m365 entra m365group add` command. The command is calling a Microsoft API that creates a Microsoft 365 group with a SharePoint site collection associated with the group. When creating a Microsoft 365 Group, the Microsoft 365 APIs create a site collection with it. The `mailNickname` property is the last portion of the site URL of the SharePoint Online site collection (yourtentantName.sharepoint.com/sites/mailNickname). You can combine the `m365 entra m365group add` command with `m365 spo site set` to change additional properties of the site not available in the `m365 entra m365group add` command.

#### What are the minimum permissions required to use the `m365 entra m365group add` command

You would need the Microsoft Graph `Group.Create` and `User.Read.All` application permissions.

[![Microsoft Entra application permissions](../images/cli-certificate-caveats/EXAMPLE_SECRET_VALUE_PLACEHOLDER)](../images/cli-certificate-caveats/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

#### What are the minimum permissions required to use the `m365 entra m365group add` command and the `m365 spo site set` command

[![Microsoft Entra application permissions](../images/cli-certificate-caveats/min-permissions-team-site.png)](../images/cli-certificate-caveats/min-permissions-team-site.png)

You would need the Microsoft Graph `Group.Create` and `User.Read.All` application permissions together with SharePoint `Sites.FullControl.All` application permission.

#### Will the `spo site add` command and CLI certificate login work for creating Communication sites and Classic sites

Yes, it will. There is a known issue with creating modern Team sites, but the workaround above should sort that as well.

#### Why not make the Team Sites being created by just executing `spo site add`

We are discussing this with the rest of the CLI team, and we might implement a fallback to the Microsoft Graph Group APIs to create the site in case of a CLI certificate login. So, it will use the same APIs as the `entra m365group add` command uses. Until this is implemented in the CLI we recommend to use the workaround described earlier.

#### There is a well-documented API from Microsoft. Why does the CLI not use it to create the modern Team Sites

There is a well-documented API for the creation of modern sites indeed. Unfortunately, the document mentions that we cannot create a new Team site based on Microsoft 365 Group.

[![API limitations highlighted in the API docs](../images/cli-certificate-caveats/doc-not-apply-to-team-sites.png)](../images/cli-certificate-caveats/doc-not-apply-to-team-sites.png)

---

## cli-output-mode

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: CLI output mode
sidebar_position: 5

## CLI for Microsoft 365 output mode

CLI for Microsoft 365 commands can present their output either as plain-text, JSON, or as CSV. Following is information on these three output modes along with information when to use which.

### Choose the command output mode

All commands in CLI for Microsoft 365 can present their output as plain-text, JSON, CSV or Markdown. By default, all commands use the JSON output mode, but by setting the `--output`, or `-o` for short, option to `text`, you can change the output mode for that command to text. By setting the output option to `csv`, you can change the output mode for that command to CSV. By setting the output option to `md`, you can change the output mode for that command to Markdown. By setting the output option to `none`, no output is returned at all, not even errors.

### JSON output mode

By default, all commands in CLI for Microsoft 365 present their output as JSON strings. This is invaluable when building scripts using the CLI, where the output of one command, has to be processed by another command.

#### Simple values

Simple values in JSON output, are returned as-is. For example, if the Microsoft 365 Public CDN is enabled on the currently connected tenant, executing the `spo cdn get` command, will return `true`:

```
$ m365 spo cdn get --output json
true
```

#### Objects

If the command returns an object, that object will be formatted as a JSON string. For example, getting information about a specific app, will return output similar to:

```
$ m365 spo app get -i EXAMPLE-GUID-PLACEHOLDER
{
  "AppCatalogVersion": "1.0.0.0",
  "CanUpgrade": false,
  "CurrentVersionDeployed": false,
  "Deployed": false,
  "ID": "EXAMPLE-GUID-PLACEHOLDER",
  "InstalledVersion": "",
  "IsClientSideSolution": true,
  "Title": "spfx-140-online-client-side-solution"
}
```

#### Arrays

If the command returns information about multiple objects, the command will return a JSON array with each array item representing one object. For example, getting the list of available apps, will return output similar to:

```
$ m365 spo app list --output json
[
  {
    "AppCatalogVersion": "1.0.0.0",
    "CanUpgrade": false,
    "CurrentVersionDeployed": false,
    "Deployed": false,
    "ID": "EXAMPLE-GUID-PLACEHOLDER",
    "InstalledVersion": "",
    "IsClientSideSolution": true,
    "Title": "spfx-140-online-client-side-solution"
  },
  {
    "AppCatalogVersion": "1.0.0.0",
    "CanUpgrade": false,
    "CurrentVersionDeployed": false,
    "Deployed": false,
    "ID": "EXAMPLE-GUID-PLACEHOLDER",
    "InstalledVersion": "",
    "IsClientSideSolution": true,
    "Title": "spfx-134-client-side-solution"
  }
]
```

Even if the array contains only one item, for consistency it will be returned as a one-element JSON array:

```
$ m365 spo app list --output json
[
  {
    "AppCatalogVersion": "1.0.0.0",
    "CanUpgrade": false,
    "CurrentVersionDeployed": false,
    "Deployed": false,
    "ID": "EXAMPLE-GUID-PLACEHOLDER",
    "InstalledVersion": "",
    "IsClientSideSolution": true,
    "Title": "spfx-140-online-client-side-solution"
  }
]
```

:::tip

Some `list` commands return different output in text and JSON mode. For readability, in the text mode they only include a few properties, so that the output can be formatted as a table and will fit on the screen. In JSON mode however, they will include all available properties so that it's possible to process the full set of information about the particular object. For more details, refer to the help of the particular command.

:::

#### Verbose and debug output in JSON mode

When executing commands in JSON output mode with the `--verbose` or `--debug` flag, the verbose and debug logging statements will be also formatted as JSON and will be added to the output. When processing the command output, you would have to determine yourself which of the returned JSON objects represents the actual command result and which are additional verbose and debug logging statements.

### Text output mode

Optionally, you can have all CLI for Microsoft 365 commands return their output as plain-text. Depending on the command output, the value is presented as-is or formatted for readability.

#### Simple values

If the command output is a simple value, such as a number, boolean or a string, the value is returned as-is. For example, if the Microsoft 365 Public CDN is enabled on the currently connected tenant, executing the `spo cdn get` command, will return `true`:

```
$ m365 spo cdn get --output text
true
```

#### Objects

If the command returns information about an object such as a site, list or an app, that contains a number of properties, the output in text mode is formatted as key-value pairs. For example, getting information about a specific app, will return output similar to:

```
$ m365 spo app get -i EXAMPLE-GUID-PLACEHOLDER --output text
AppCatalogVersion     : 1.0.0.0
CanUpgrade            : false
CurrentVersionDeployed: false
Deployed              : false
ID                    : EXAMPLE-GUID-PLACEHOLDER
InstalledVersion      :
IsClientSideSolution  : true
Title                 : spfx-140-online-client-side-solution
```

#### Arrays

If the command returns information about multiple objects, the output is formatted as a table. For example, getting the list of available apps, will return output similar to:

```
$ m365 spo app list --output text
Title                                 ID                                    Deployed  AppCatalogVersion
------------------------------------  ------------------------------------  --------  -----------------
spfx-140-online-client-side-solution  EXAMPLE-GUID-PLACEHOLDER  false     1.0.0.0
spfx-134-client-side-solution         EXAMPLE-GUID-PLACEHOLDER  false     1.0.0.0
```

If only one app is returned, it will be displayed as key-value pairs:

```
$ m365 spo app list --output text
AppCatalogVersion: 1.0.0.0
Deployed         : false
ID               : EXAMPLE-GUID-PLACEHOLDER
Title            : spfx-140-online-client-side-solution
```

### CSV output mode

Optionally, you can have all CLI for Microsoft 365 commands return their output as comma-separated values. Depending on the command output, the value is presented as-is or formatted for readability.

#### Simple values

If the command output is a simple value, such as a number, boolean or a string, the value is returned as-is. For example, if the Microsoft 365 Public CDN is enabled on the currently connected tenant, executing the `spo cdn get` command, will return `true`:

```
$ m365 spo cdn get --output csv
true
```

#### Objects

If the command returns information about an object such as a site, list or an app, that contains a number of properties, the output in CSV mode is formatted as comma-separated values. For example, getting information about a specific app, will return output similar to the following:

```
$ m365 spo app get -i EXAMPLE-GUID-PLACEHOLDER --output csv
AppCatalogVersion,CanUpgrade,CurrentVersionDeployed,Deployed,ID,InstalledVersion,IsClientSideSolution,Title
1.0.0.0,false,false,false,EXAMPLE-GUID-PLACEHOLDER,,true,spfx-140-online-client-side-solution
```

#### Arrays

If the command returns information about multiple objects, the output is formatted as multiple lines of comma-separated values. For example, getting the list of available apps will return output similar to the following:

```
$ m365 spo app list --output csv
Title,ID,Deployed,AppCatalogVersion
spfx-140-online-client-side-solution,EXAMPLE-GUID-PLACEHOLDER,false,1.0.0.0
spfx-134-client-side-solution,EXAMPLE-GUID-PLACEHOLDER,false,1.0.0.0
```

### Markdown output mode

Using the Markdown output mode is convenient if you need to create documentation for your Microsoft 365 tenant.

:::tip

When using the Markdown output, you'll typically want to store the output in a file or in the clipboard. To redirect the output to a file, execute `m365 spo site list --output markdown > sites.md`. To copy the output to the clipboard, on macOS execute `m365 spo site list --output markdown | pbcopy`, and on Windows execute `m365 spo site list --output markdown | clip`.

:::

#### Simple values

If the command output is a simple value, such as a number, boolean or a string, the value is returned as-is. For example, if the Microsoft 365 Public CDN is enabled on the currently connected tenant, executing the `spo cdn get` command, will return `true`:

```
$ m365 spo cdn get --output md
true
```

#### Objects

If the command returns information about an object such as a site, a list or an app, the output in Markdown mode is formatted as a simple report.

```
$ m365 spo app get --id EXAMPLE-GUID-PLACEHOLDER --output md
# spo app get --id "EXAMPLE-GUID-PLACEHOLDER"

Date: 04/12/2022

## spfx-teams-client-side-solution (EXAMPLE-GUID-PLACEHOLDER)

Property | Value
---------|-------
AadAppId | EXAMPLE-GUID-PLACEHOLDER
AadPermissions | null
AppCatalogVersion | 1.0.0.0
CanUpgrade | false
CDNLocation | SharePoint Online
ContainsTenantWideExtension | false
CurrentVersionDeployed | true
Deployed | true
ErrorMessage | No errors.
ID | EXAMPLE-GUID-PLACEHOLDER
InstalledVersion | 
IsClientSideSolution | true
IsEnabled | true
IsPackageDefaultSkipFeatureDeployment | true
IsValidAppPackage | true
ProductId | EXAMPLE-GUID-PLACEHOLDER
ShortDescription | spfx-teams description
SkipDeploymentFeature | true
StoreAssetId | 
ThumbnailUrl | 
Title | spfx-teams-client-side-solution
```

The report consists of a title section, which shows the information about the executed command and the date when the command was executed.

```
# spo app get --id "EXAMPLE-GUID-PLACEHOLDER"

Date: 04/12/2022

...
```

Then, the report shows information for the retrieved object. The object-specific information starts with a heading, which contains the object's display name and ID.

```
# spo app get --id "EXAMPLE-GUID-PLACEHOLDER"

Date: 04/12/2022

## spfx-teams-client-side-solution (EXAMPLE-GUID-PLACEHOLDER)

...
```

CLI for Microsoft 365 tries to retrieve the object's display name from the following properties in the following order: `title`, `Title`, `displayName`, `DisplayName`, `name`, and `Name`. If the object doesn't have any of these properties, the display name will be  `undefined`.

The display name is followed by the object's ID in parentheses, which CLI tries to resolve from the following properties in the following order: `id`, `Id`, `ID`, `uniqueId`, `UniqueId`, `objectId`, `ObjectId`, `url`, `Url`, `URL`. If the object doesn't have any of these properties, the ID will be displayed as `undefined`.

The heading is followed by a table showing all retrieved object's properties and their values:

```
# spo app get --id "EXAMPLE-GUID-PLACEHOLDER"

Date: 04/12/2022

## spfx-teams-client-side-solution (EXAMPLE-GUID-PLACEHOLDER)

Property | Value
---------|-------
AadAppId | EXAMPLE-GUID-PLACEHOLDER
AadPermissions | null
AppCatalogVersion | 1.0.0.0
CanUpgrade | false
CDNLocation | SharePoint Online
...
```

If the value of a property is an object, it will be JSON-serialized and displayed as a string, for example see the value of the `CurrentChangeToken` property for a site:

```
$ m365 spo site get --url /sites/Retail --output md
# spo site get --url "https://contoso.sharepoint.com/sites/Retail"

Date: 04/12/2022

## undefined (EXAMPLE-GUID-PLACEHOLDER)

Property | Value
---------|-------
AllowCreateDeclarativeWorkflow | false
AllowDesigner | true
AllowMasterPageEditing | false
AllowRevertFromTemplate | false
AllowSaveDeclarativeWorkflowAsTemplate | false
AllowSavePublishDeclarativeWorkflow | false
AllowSelfServiceUpgrade | true
AllowSelfServiceUpgradeEvaluation | true
AuditLogTrimmingRetention | 90
ChannelGroupId | EXAMPLE-GUID-PLACEHOLDER
Classification | 
CompatibilityLevel | 15
CurrentChangeToken | {"StringValue":"1;1;EXAMPLE-GUID-PLACEHOLDER;638057455441300000;64815409"}
DisableAppViews | false
DisableCompanyWideSharingLinks | false
DisableFlows | false
ExternalSharingTipsEnabled | false
GeoLocation | EUR
GroupId | EXAMPLE-GUID-PLACEHOLDER
HubSiteId | EXAMPLE-GUID-PLACEHOLDER
Id | EXAMPLE-GUID-PLACEHOLDER
SensitivityLabelId | null
SensitivityLabel | EXAMPLE-GUID-PLACEHOLDER
IsHubSite | false
LockIssue | null
MaxItemsPerThrottledOperation | 5000
MediaTranscriptionDisabled | false
NeedsB2BUpgrade | false
ResourcePath | {"DecodedUrl":"https://contoso.sharepoint.com/sites/Retail"}
PrimaryUri | https://contoso.sharepoint.com/sites/Retail
ReadOnly | false
RequiredDesignerVersion | 15.0.0.0
SandboxedCodeActivationCapability | 2
ServerRelativeUrl | /sites/Retail
ShareByEmailEnabled | true
ShareByLinkEnabled | false
ShowUrlStructure | false
TrimAuditLog | true
UIVersionConfigurationEnabled | false
UpgradeReminderDate | 1899-12-30T00:00:00
UpgradeScheduled | false
UpgradeScheduledDate | 1753-01-01T00:00:00
Upgrading | false
Url | https://contoso.sharepoint.com/sites/Retail
WriteLocked | false
```

#### Arrays

If the command returns information about multiple objects, the output is formatted as a report, where each object is displayed in a separate section, for example:

```
$ m365 spo site list --output md
# spo site list 

Date: 04/12/2022

## Retail (https://contoso.sharepoint.com/sites/Retail)

Property | Value
---------|-------
\_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
\_ObjectIdentity\_ | EXAMPLE-GUID-PLACEHOLDER\|EXAMPLE-GUID-PLACEHOLDER:EXAMPLE-GUID-PLACEHOLDER<br>SiteProperties<br>https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fRetail
AllowDownloadingNonWebViewableFiles | false
AllowEditing | false
AllowSelfServiceUpgrade | true
AnonymousLinkExpirationInDays | 0
AuthContextStrength | null
AuthenticationContextName | null
AverageResourceUsage | 0
BlockDownloadLinksFileType | 0
BlockDownloadMicrosoft365GroupIds | null
BlockDownloadPolicy | false
CommentsOnSitePagesDisabled | false
CompatibilityLevel | 15
ConditionalAccessPolicy | 0
CurrentResourceUsage | 0
DefaultLinkPermission | 0
DefaultLinkToExistingAccess | false
DefaultLinkToExistingAccessReset | false
DefaultShareLinkRole | 0
DefaultShareLinkScope | 0
DefaultSharingLinkType | 0
DenyAddAndCustomizePages | 2
Description | null
DisableAppViews | 0
DisableCompanyWideSharingLinks | 0
DisableFlows | 0
ExcludeBlockDownloadPolicySiteOwners | false
ExcludedBlockDownloadGroupIds | []
ExternalUserExpirationInDays | 0
GroupId | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
GroupOwnerLoginName | null
HasHolds | false
HubSiteId | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
IBMode | null
IBSegments | []
IBSegmentsToAdd | null
IBSegmentsToRemove | null
IsGroupOwnerSiteAdmin | false
IsHubSite | false
IsTeamsChannelConnected | false
IsTeamsConnected | true
LastContentModifiedDate | /Date(2022,9,18,13,22,1,233)/
Lcid | 1033
LimitedAccessFileType | 0
LockIssue | null
LockState | Unlock
LoopDefaultSharingLinkRole | 0
LoopDefaultSharingLinkScope | 0
LoopOverrideSharingCapability | false
LoopSharingCapability | 0
MediaTranscription | 0
OverrideBlockUserInfoVisibility | 0
OverrideSharingCapability | false
EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
Owner | 
OwnerEmail | null
OwnerLoginName | null
OwnerName | null
PWAEnabled | 1
ReadOnlyAccessPolicy | false
ReadOnlyForUnmanagedDevices | false
RelatedGroupId | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
RequestFilesLinkEnabled | false
RequestFilesLinkExpirationInDays | 0
RestrictedAccessControl | false
RestrictedToRegion | 3
SandboxedCodeActivationCapability | 0
SensitivityLabel | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
SensitivityLabel2 | null
SetOwnerWithoutUpdatingSecondaryAdmin | false
SharingAllowedDomainList | null
SharingBlockedDomainList | null
SharingCapability | 1
SharingDomainRestrictionMode | 0
SharingLockDownCanBeCleared | false
SharingLockDownEnabled | false
EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
SiteDefinedSharingCapability | 1
SocialBarOnSitePagesDisabled | false
Status | Active
StorageMaximumLevel | 26214400
StorageQuotaType | null
StorageUsage | 1
StorageWarningLevel | 25574400
TeamsChannelType | 0
Template | GROUP#0
TimeZoneId | 13
Title | Retail
TitleTranslations | null
Url | https://contoso.sharepoint.com/sites/Retail
UserCodeMaximumLevel | 300
UserCodeWarningLevel | 200
WebsCount | 0

## Mark 8 Project Team (https://contoso.sharepoint.com/sites/Mark8ProjectTeam)

Property | Value
---------|-------
\_ObjectType\_ | EXAMPLE_SECRET_VALUE_PLACEHOLDER
\_ObjectIdentity\_ | EXAMPLE-GUID-PLACEHOLDER\|EXAMPLE-GUID-PLACEHOLDER:EXAMPLE-GUID-PLACEHOLDER<br>SiteProperties<br>https%3a%2f%2fcontoso.sharepoint.com%2fsites%2fMark8ProjectTeam
AllowDownloadingNonWebViewableFiles | false
AllowEditing | false
AllowSelfServiceUpgrade | true
AnonymousLinkExpirationInDays | 0
AuthContextStrength | null
AuthenticationContextName | null
AverageResourceUsage | 0
BlockDownloadLinksFileType | 0
BlockDownloadMicrosoft365GroupIds | null
BlockDownloadPolicy | false
CommentsOnSitePagesDisabled | false
CompatibilityLevel | 15
ConditionalAccessPolicy | 0
CurrentResourceUsage | 0
DefaultLinkPermission | 0
DefaultLinkToExistingAccess | false
DefaultLinkToExistingAccessReset | false
DefaultShareLinkRole | 0
DefaultShareLinkScope | 0
DefaultSharingLinkType | 0
DenyAddAndCustomizePages | 2
Description | null
DisableAppViews | 0
DisableCompanyWideSharingLinks | 0
DisableFlows | 0
ExcludeBlockDownloadPolicySiteOwners | false
ExcludedBlockDownloadGroupIds | []
ExternalUserExpirationInDays | 0
GroupId | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
GroupOwnerLoginName | null
HasHolds | false
HubSiteId | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
IBMode | null
IBSegments | []
IBSegmentsToAdd | null
IBSegmentsToRemove | null
IsGroupOwnerSiteAdmin | false
IsHubSite | false
IsTeamsChannelConnected | false
IsTeamsConnected | true
LastContentModifiedDate | /Date(2022,9,7,12,52,20,347)/
Lcid | 1033
LimitedAccessFileType | 0
LockIssue | null
LockState | Unlock
LoopDefaultSharingLinkRole | 0
LoopDefaultSharingLinkScope | 0
LoopOverrideSharingCapability | false
LoopSharingCapability | 0
MediaTranscription | 0
OverrideBlockUserInfoVisibility | 0
OverrideSharingCapability | false
EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
Owner | 
OwnerEmail | null
OwnerLoginName | null
OwnerName | null
PWAEnabled | 1
ReadOnlyAccessPolicy | false
ReadOnlyForUnmanagedDevices | false
RelatedGroupId | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
RequestFilesLinkEnabled | false
RequestFilesLinkExpirationInDays | 0
RestrictedAccessControl | false
RestrictedToRegion | 3
SandboxedCodeActivationCapability | 0
SensitivityLabel | /Guid(EXAMPLE-GUID-PLACEHOLDER)/
SensitivityLabel2 | null
SetOwnerWithoutUpdatingSecondaryAdmin | false
SharingAllowedDomainList | null
SharingBlockedDomainList | null
SharingCapability | 1
SharingDomainRestrictionMode | 0
SharingLockDownCanBeCleared | false
SharingLockDownEnabled | false
EXAMPLE_SECRET_VALUE_PLACEHOLDER | false
SiteDefinedSharingCapability | 1
SocialBarOnSitePagesDisabled | false
Status | Active
StorageMaximumLevel | 26214400
StorageQuotaType | null
StorageUsage | 1
StorageWarningLevel | 25574400
TeamsChannelType | 0
Template | GROUP#0
TimeZoneId | 13
Title | Mark 8 Project Team
TitleTranslations | null
Url | https://contoso.sharepoint.com/sites/Mark8ProjectTeam
UserCodeMaximumLevel | 300
UserCodeWarningLevel | 200
WebsCount | 0

...
```

:::note

Special Markdown characters, and new line characters in the names and values of properties are escaped so that they're displayed correctly in the table.

:::

### Processing command output with JMESPath

CLI for Microsoft 365 supports filtering, sorting and querying data returned by its commands using [JMESPath](http://jmespath.org/) queries. Queries can be specified using the `--query` option on each command and are applied just before the data retrieved by the command is sent to the console. While you can apply JMESPath queries in all output modes, they are the most powerful in combination with JSON output where the data is unfiltered and the complete data set is sent to output.

For example, you can retrieve the list of all SharePoint site collections in your tenant, by executing:

```
$ m365 spo site list --output text
Title                                Url
-----------------------------------  -------------------------------------------------------------------------
Digital Initiative Public Relations  https://contoso.sharepoint.com/sites/DigitalInitiativePublicRelations
Leadership Team                      https://contoso.sharepoint.com/sites/leadership
Mark 8 Project Team                  https://contoso.sharepoint.com/sites/Mark8ProjectTeam
Operations                           https://contoso.sharepoint.com/sites/operations
Retail                               https://contoso.sharepoint.com/sites/Retail
Sales and Marketing                  https://contoso.sharepoint.com/sites/SalesAndMarketing
```

To retrieve information only about sites matching a specific title or URL, you could execute:

```
$ m365 spo site list --query "[?Title == 'Retail']" --output text
Title: Retail
Url  : https://contoso.sharepoint.com/sites/Retail
```

To make the output more readable, you could pass it to a JSON processor such as [jq](https://stedolan.github.io/jq/):

```
$ m365 spo site list --output json --query "[?Template == 'GROUP#0'].{Title: Title, Url: Url}" | jq
[
  {
    "Title": "Mark 8 Project Team",
    "Url": "https://contoso.sharepoint.com/sites/Mark8ProjectTeam"
  },
  {
    "Title": "Operations",
    "Url": "https://contoso.sharepoint.com/sites/operations"
  },
  {
    "Title": "Digital Initiative Public Relations",
    "Url": "https://contoso.sharepoint.com/sites/DigitalInitiativePublicRelations"
  },
  {
    "Title": "Retail",
    "Url": "https://contoso.sharepoint.com/sites/Retail"
  },
  {
    "Title": "Leadership Team",
    "Url": "https://contoso.sharepoint.com/sites/leadership"
  },
  {
    "Title": "Sales and Marketing",
    "Url": "https://contoso.sharepoint.com/sites/SalesAndMarketing"
  }
]
```

### When to use which output mode

Generally, you will use the text output when interacting with the CLI yourself. When building scripts using the CLI for Microsoft 365, you will use the default JSON output mode, because processing JSON strings is much more convenient and reliable than processing plain-text output.

### Sample script

Using the JSON output mode allows you to build scripts using the CLI for Microsoft 365. The CLI works on any platform, but as there is no common way to work with objects and command output on all platforms and shells, we chose JSON as the format to serialize objects in the CLI for Microsoft 365.

Following, is a sample script, that you could build using the CLI for Microsoft 365 in Bash:

```
m365 # get all apps available in the tenant app catalog
apps=$(m365 spo app list --output json)

# get IDs of all apps that are not deployed
notDeployedAppsIds=($(echo $apps | jq -r '.[] | select(.Deployed == false) | {ID} | .[]'))

# deploy all not deployed apps
for appId in $notDeployedAppsIds; do
  m365 spo app deploy -i $appId
done
```

_First, you use the CLI for Microsoft 365 to get the list of all apps from the tenant app catalog using the [spo app list](../cmd/spo/app/app-list.mdx) command. You set the output type to JSON and store it in a shell variable `apps`. Next, you parse the JSON string using [jq](https://stedolan.github.io/jq/) and get IDs of apps that are not deployed. Finally, for each ID you run the [spo app deploy](../cmd/spo/app/app-deploy.mdx) CLI for Microsoft 365 command passing the ID as a command argument. Notice, that in the script, both `spo` commands are prepended with `m365` and executed as separate commands directly in the shell._

The same could be accomplished in PowerShell as well:

```
# get all apps available in the tenant app catalog
$apps = m365 spo app list --output json | ConvertFrom-Json

# get all apps that are not yet deployed and deploy them
$apps | ? Deployed -eq $false | % { m365 spo app deploy -i $_.ID }
```

Because PowerShell offers native support for working with JSON strings and objects, the same script written in PowerShell is simpler than the one in Bash. At the end of the day it's up to you to choose if you want to use the CLI for Microsoft 365 in Bash, PowerShell or some other shell. Both Bash and PowerShell are available on multiple platforms, and if you have a team using different platforms, writing scripts using CLI for Microsoft 365 in Bash or PowerShell will let everyone in your team use them.

### Hiding all output

When setting the value of the output option to `none`, no output is returned at all. This includes command output, errors, validation errors and help documentation. This can be useful when running the CLI for Microsoft 365 in an environment where console output is problematic.

An example of how to run a command with output --none can be found below:

```
m365 spo listitem set --webUrl https://contoso.sharepoint.com --listTitle 'Projects' --id 5 --Title 'Updated title' --output none
```

---

## completion

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Command completion
sidebar_position: 9

## Command completion

To help you use its commands, CLI for Microsoft 365 offers you the ability to autocomplete commands and options that you're typing in the prompt. Some additional setup, specific for the shell and terminal that you use, is required to enable command completion for CLI for Microsoft 365.

### Clink (cmder)

On Windows, the CLI for Microsoft 365 offers support for completing commands in [cmder](http://cmder.app) and other shells using [Clink](https://mridgers.github.io/clink/).

#### Enable Clink completion

To enable completion:

---

## configuring-cli

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Configure CLI
sidebar_position: 7

import CLISettings from '/docs/_clisettings.mdx';

## Configure CLI for Microsoft 365

You can configure CLI for Microsoft 365 to your personal preferences using its settings. Settings are stored on the disk in the current user's folder: `C:\Users\user\.config

---

## connecting-microsoft-365

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Log in to Microsoft 365 
sidebar_position: 3

import AsciinemaPlayer from '../../src/components/AsciinemaPlayer';
import 'asciinema-player/dist/bundle/asciinema-player.css';

## Log in to Microsoft 365

Before you can use CLI for Microsoft 365 commands to manage your tenant, you have to log in to Microsoft 365. Following section explains how you can log in and check the Microsoft 365 login status.

### Microsoft 365 services

Using the CLI for Microsoft 365 you can manage different areas of an Microsoft 365 tenant. Currently, commands for working with SharePoint Online, Microsoft Entra ID, Microsoft Graph and the Azure Management Service are available, but more commands for other services will be added in the future.

Commands in the CLI for Microsoft 365 are organized into services. For example, all commands that manage SharePoint Online begin with `spo` (`spo app list`, `spo cdn get`, etc.) and commands for working with the Microsoft Entra ID begin with `entra`. After logging in to Microsoft 365, you can communicate with any Microsoft 365 service supported by the CLI for Microsoft 365 and it will automatically retrieve the necessary access token.

#### Log in to Microsoft 365

CLI for Microsoft 365 offers you a number of ways to log in to Microsoft 365.

The default way to log in to Microsoft 365 using the CLI for Microsoft 365 is through the device code flow. To log in to Microsoft 365, use the `login` command.

When logging in, you need to specify the `appId` and `tenant` of your Microsoft Entra application registration. This is required to authenticate your own application registration to access your tenant on your behalf.

:::info

If you don't have an application registration yet, you can create one using the [m365 setup](../cmd/setup.mdx) command. This command will guide you through the process of creating a new application registration and granting it the necessary permissions in your tenant. It will also set the `appId` and `tenant` environment variables for you, allowing you to log in to Microsoft 365 without specifying these values when using the `login` command.

Alternatively, you can manually set the `CLIMICROSOFT365_ENTRAAPPID` and `CLIMICROSOFT365_TENANT` environment variables to avoid specifying the `appId` and `tenant` values during login.

For more details on creating an application registration or setting the environment variables, refer to the article: [Use your own Microsoft Entra identity](./using-own-identity.mdx).

:::

After executing the `login` command, you will be prompted to navigate to _https://aka.ms/devicelogin_ in your web browser and enter the login code presented to you by the CLI for Microsoft 365 in the command line. After entering the code, you will see the prompt that you are about to authenticate your own application registration to access your tenant on your behalf. After accepting the prompt, you can go back to the CLI for Microsoft 365 and you will be logged.

The default method to log in to Microsoft 365 using the CLI for Microsoft 365 is through the device code flow, which you can initiate by executing the `login` command. However, if possible, opt for browser authentication as it is more convenient and provides the same security benefits. If you are logging in from a different system (e.g., inside a Docker container, Azure Cloud Shell, etc.) where the CLI cannot open a browser, use the device code flow instead. The device code flow is interactive and requires user interaction, which might be limiting if you want to use the CLI for Microsoft 365 in a fully automated continuous deployment setup that doesn't involve user interaction.

An alternative way to log in to Microsoft 365 in the CLI for Microsoft 365 is by using a user name and password. To use this way of authenticating, set the `authType` option to `password` and specify your credentials using the `userName` and `password` options.

To log in to Microsoft 365 using your user name and password, execute:

```
m365 login --authType password --userName user@contoso.com --password pass@word1
```

Using credentials to log in to Microsoft 365 is convenient in automation scenarios where you cannot authenticate interactively. The downside of this way of authenticating is, that it doesn't allow you to use any of the advanced security features that Microsoft Entra ID offers. If your account for example uses multi-factor authentication, logging in to Microsoft 365 using credentials will fail.

:::warning

When logging in to Microsoft 365 using credentials, CLI for Microsoft 365 will persist not only the retrieved access and refresh token, but also the credentials you specified when logging in. This is necessary for the CLI to be able to retrieve a new refresh token, in case the previously retrieved refresh token expired or has been invalidated.

:::

Generally, you should use the default device code flow. If you need to use a non-interactive authentication flow, you can authenticate using a certificate or credentials of an account that has sufficient privileges in your tenant and doesn't have multi-factor authentication or other advanced security features enabled.

Another way to log in to Microsoft 365 in the CLI for Microsoft 365 is by using a certificate. To use this authentication method, set the `CLIMICROSOFT365_ENTRAAPPID` environment variable to the ID of the Microsoft Entra application that you want to use to authenticate the CLI for Microsoft 365 and the `CLIMICROSOFT365_TENANT` environment variable to the ID of your Microsoft Entra ID directory. When calling the login command, set the `authType` option to `certificate` and specify the path to the certificate private key using the `certificateFile` option. Optionally, you can specify the certificate's thumbprint using the `thumbprint` option. If not specified, CLI will automatically calculate it from the specified certificate.

To log in to Microsoft 365 using a Personal Information Exchange (.pfx) file, execute:

```
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pfx --password 'pass@word1'
```

To log in to Microsoft 365 using a Privacy Enhanced Mail (PEM) certificate, execute:

```
m365 login --authType certificate --certificateFile /Users/user/dev/localhost.pem
```

Logging in to Microsoft 365 using a certificate is convenient for automation scenarios where you cannot authenticate interactively but also don't want to use credentials.

Because there is no user context when logging in using a certificate, you will typically create a new Microsoft Entra application, specific to your organization and grant it the required permissions.

:::warning

You should keep in mind, that because the CLI for Microsoft 365 will be accessing these APIs with app-only context, you need to grant the correct application permissions rather than delegated permissions that would be used in other authentication methods.

:::

Logging in using a certificate gives the CLI for Microsoft 365 app-only access to Microsoft 365 services. Not all operations support app-only access so it is possible, that some CLI commands will fail when executed while logged in to Microsoft 365 using a certificate.

:::warning

When logging in to Microsoft 365 using a certificate, CLI for Microsoft 365 will persist not only the retrieved access token but also the contents of the certificate's private key and its thumbprint. This is necessary for the CLI to be able to retrieve a new access token in case of the previously retrieved access token expired or has been invalidated.

:::

Generally, you should use the default device code flow. If you need to use a non-interactive authentication flow, to for example integrate the CLI for Microsoft 365 in your build pipeline, you can login using a certificate or user credentials.

:::warning

PFX files exported from a Windows key store will not work as they are protected with either a password or Active Directory account. The private key must either be exported from the protected .pfx or newly created using 3rd party tools like OpenSSL (https://www.openssl.org/).

:::

Create a new self signed certificate:

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout privateKey.key -out certificate.cer
```

Create a new Personal Information Exchange (.pfx) file

```
openssl pkcs12 -export -out protected.pfx -inkey privateKey.key -in certificate.cer -password pass:"pass@word1"
```

At this point the `protected.pfx` file can be used to log in the CLI for Microsoft 365 following the instructions above for logging in using a .pfx file.

If login with the .pfx file does not work then extract the private key from a protected .pfx and unprotect it:

```
openssl pkcs12 -in protected.pfx -out privateKeyWithPassphrase.pem -nodes
```

At this point the `privateKeyWithPassphrase.pem` file can be used to log in the CLI for Microsoft 365 following the instructions above for logging in using a PEM certificate.

CLI for Microsoft 365 also supports login using a secret. To use this authentication method, set the `CLIMICROSOFT365_ENTRAAPPID` environment variable to the ID of the Microsoft Entra application that you want to use to authenticate the CLI for Microsoft 365 and the `CLIMICROSOFT365_TENANT` environment variable to the ID of your Microsoft Entra ID directory. When calling the login command, set the `authType` option to `secret` and specify the client secret value.

To log in to Microsoft 365 using a secret, execute:

```
m365 login --authType secret --secret topSeCr3t@007
```

Logging in to Microsoft 365 using a secret is convenient for automation scenarios where you cannot authenticate interactively but also don't want to use credentials.

Because there is no user context when logging in using a secret, you will typically create a new Microsoft Entra application, specific to your organization and grant it the required permissions.

:::warning

You should keep in mind, that because the CLI for Microsoft 365 will be accessing these APIs with app-only context, you need to grant the correct application permissions rather than delegated permissions that would be used in other authentication methods.

:::

Logging in using a secret gives the CLI for Microsoft 365 app-only access to Microsoft 365 services. Not all operations support app-only access so it is possible, that some CLI commands will fail when executed while logged in to Microsoft 365 using a secret.

:::warning

Currently, SharePoint does not support authentication using Microsoft Entra app ID and Secret. CLI for Microsoft 365 commands that call the SharePoint APIs will fail while logged in to Microsoft 365 using a Secret.

:::

:::warning

When logging in to Microsoft 365 using a secret, CLI for Microsoft 365 will persist not only the retrieved access token but also the secret. This is necessary for the CLI to be able to retrieve a new access token in case of the previously retrieved access token expired or has been invalidated.

:::

In all the examples above, we make use of the `CLIMICROSOFT365_ENTRAAPPID` and `CLIMICROSOFT365_TENANT` environment variables. If you don't want to set these environment variables, you can specify the options `appId` and `tenant` when logging in to Microsoft 365.

Below would be the command to log in to Microsoft 365 using a Personal Information Exchange (.pfx) file, execute:

```
m365 login --appId EXAMPLE-GUID-PLACEHOLDER --tenant EXAMPLE-GUID-PLACEHOLDER -authType certificate --certificateFile /Users/user/dev/localhost.pfx --password 'pass@word1'
```

Yet another way to log in to Microsoft 365 in the CLI for Microsoft 365 is by using a an interactive browser authentication. To use this authentication method, call the login command with the `authType` option set to `browser`:

```
m365 login --authType browser
```

This option is especially useful if you have conditional access policies configured in your tenant but you can also use it instead of the default device code flow.

#### Check login status

To see if you're logged in to Microsoft 365 and if so, with which account, use the `status` command.

If you're logged in to Microsoft 365 using a certificate, the `status` command will show the name of the Microsoft Entra application used to log in.

#### Log out from Microsoft 365

To log out from Microsoft 365, use the `logout` command. Executing the `logout` command removes all connection information such as user name, refresh or access tokens stored on your computer.

#### Working with SharePoint Online

CLI for Microsoft 365 automatically detects the URL of your SharePoint Online tenant when executing SharePoint commands. All you need to do is to log in to Microsoft 365 with your account. Commands, that operate on specific site collections or sites, allow you to specify the URL of the site on which you want to perform the operation and you can execute them without having to specifically connect or login to the given site. CLI for Microsoft 365 will automatically retrieve the necessary access token to execute the given command.

:::info

Some SharePoint commands in the CLI for Microsoft 365 require access to tenant-level resources. To execute these commands, you have to have permissions to access the tenant admin site.

:::

### Authorize with Microsoft 365

To authorize for communicating with Microsoft 365 API, the CLI for Microsoft 365 uses the OAuth 2.0 protocol. When using the default device code flow, you authenticate with Microsoft Entra ID in the web browser. After authenticating, CLI for Microsoft 365 will attempt to retrieve a valid access token for the specified Microsoft 365 service. If you have insufficient permissions to access the particular service, authorization will fail with an adequate error.

If you authenticate using credentials, the authentication and authorization are a part of the same request that CLI for Microsoft 365 issues towards Microsoft Entra ID. If either authentication or authorization fails, you will see a corresponding error message explaining what went wrong.

### Logging in to Microsoft 365 via a proxy

All communication between the CLI for Microsoft 365 and Microsoft 365 APIs happens via web requests. If you're behind a proxy, you should set up an environment variable to allow CLI for Microsoft 365 to log in to Microsoft 365. More information about the necessary configuration steps is available at [https://github.com/request/request#EXAMPLE_SECRET_VALUE_PLACEHOLDER](https://github.com/request/request#EXAMPLE_SECRET_VALUE_PLACEHOLDER).

### Persisted connections

After logging in to Microsoft 365, the CLI for Microsoft 365 will persist that connection information until you explicitly log out from Microsoft 365. This is necessary to support building scripts using the CLI for Microsoft 365, where each command is executed independently of other commands. Persisted connection contains information about the user name used to establish the connection as well as the retrieved refresh- and access tokens. To secure this information from unprivileged access, it's stored securely in the password store specific to the platform on which you're using the CLI. For more information, see the separate article dedicated to [persisting connection information](../concepts/persisting-connection.mdx) in the CLI for Microsoft 365.

---

## filter-cli-data

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Filter CLI data
sidebar_position: 6

## Filter CLI for Microsoft 365 data

CLI for Microsoft 365 supports filtering, sorting, and querying data using [JMESPath](http://jmespath.org/) queries. By specifying the `--query` option on each command you can create complex queries.

There are two types of data returned by the CLI for Microsoft 365 when retrieving data as JSON. In most cases, it returns an array of items, but some of the older commands the response is encapsulated in a `value` object. For both scenario's you can use JMESPath to filter, but the queries are a bit different.

### Testing JMESPath queries

You can test your queries using the [JMESPath](http://jmespath.org/) interactive homepage. You can execute a CLI for Microsoft 365 command, get the JSON response and paste it on the homepage and test your queries from there if you do not want to test them while writing scripts. It is a great way to learn what's possible!

### Basic array filters

Let's start with a basic command and return some results using the following command: `m365 spo site list`. To simplify the testing most of the properties are removed, but the result would look similarly to:

```
[{
    "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "AllowDownloadingNonWebViewableFiles": true,
    "AllowEditing": false,
    "Title": "Demo 1",
    "Status": "Active",
    "StorageMaximumLevel": 26214400,
    "StorageQuotaType": null
 },
 {
    "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "AllowDownloadingNonWebViewableFiles": false,
    "AllowEditing": false,
    "Title": "A Demo 2",
    "Status": "Active",
    "StorageMaximumLevel": 26214400,
    "StorageQuotaType": null
 },
 {
    "_ObjectType_": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "AllowDownloadingNonWebViewableFiles": true,
    "AllowEditing": false,
    "Title": "Sample 1",
    "Status": "Active",
    "StorageMaximumLevel": 26214400,
    "StorageQuotaType": null
}]
```

Using JMESPath queries you can do basic filtering as well as more complex scenario's like `starts_with` or `ends_with`.

Besides filtering, you can also scope what will be returned as a result:

Or you can combine both a filter query and scope the results:

### Other array filters

Some of the commands return complex types. Querying or filtering based on values in complex types can be done with JMESPath as well. The query, however, will look different. Executing the following command `m365 flow environment list --output json` will return a complex type and the result will be similar to the sample below:

```
[
  {
    "name": "EXAMPLE-GUID-PLACEHOLDER",
    "location": "europe",
    "type": "Microsoft.ProcessSimple/environments",
    "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE-GUID-PLACEHOLDER",
    "properties": {
      "displayName": "Contoso Dev Environment",
      "createdTime": "2021-06-18T16:36:20.5687306Z",
      "createdBy": {
        "id": "SYSTEM",
        "displayName": "SYSTEM",
        "type": "NotSpecified"
      },
      "lastModifiedTime": "2021-06-18T16:40:32.7592868Z",
      "provisioningState": "Succeeded",
      "creationType": "Developer",
      "environmentSku": "Developer",
      "environmentType": "NotSpecified",
      "states": {
        "management": {
          "id": "Ready"
        },
        "runtime": {
          "id": "Enabled"
        }
      },
      "isDefault": false,
      "azureRegionHint": "westeurope",
      "runtimeEndpoints": {
        "microsoft.BusinessAppPlatform": "https://europe.api.bap.microsoft.com",
        "microsoft.CommonDataModel": "https://europe.api.cds.microsoft.com",
        "microsoft.PowerApps": "https://europe.api.powerapps.com",
        "microsoft.Flow": "https://europe.api.flow.microsoft.com",
        "microsoft.PowerAppsAdvisor": "https://europe.api.advisor.powerapps.com",
        "microsoft.ApiManagement": "https://management.EUR.azure-apihub.net"
      },
      "environmentFeatures": {
        "isOpenApiEnabled": false
      }
    },
    "displayName": "Contoso Dev Environment"
  },
  {
    "name": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "location": "europe",
    "type": "Microsoft.ProcessSimple/environments",
    "id": "/providers/Microsoft.ProcessSimple/environments/EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "properties": {
      "displayName": "contoso (default)",
      "createdTime": "2016-10-28T10:32:54.1945519Z",
      "createdBy": {
        "id": "EXAMPLE-GUID-PLACEHOLDER",
        "displayName": "Garth Fort",
        "type": "NotSpecified"
      },
      "lastModifiedTime": "2020-07-28T08:58:12.5785779Z",
      "lastModifiedBy": {
        "id": "EXAMPLE-GUID-PLACEHOLDER",
        "displayName": "Garth Fort",
        "email": "garthf@contoso.nl",
        "type": "User",
        "tenantId": "EXAMPLE-GUID-PLACEHOLDER",
        "userPrincipalName": "garthf@contoso.nl"
      },
      "provisioningState": "Succeeded",
      "creationType": "DefaultTenant",
      "environmentSku": "Default",
      "environmentType": "NotSpecified",
      "states": {
        "management": {
          "id": "NotSpecified"
        },
        "runtime": {
          "id": "Enabled"
        }
      },
      "isDefault": true,
      "azureRegionHint": "westeurope",
      "runtimeEndpoints": {
        "microsoft.BusinessAppPlatform": "https://europe.api.bap.microsoft.com",
        "microsoft.CommonDataModel": "https://europe.api.cds.microsoft.com",
        "microsoft.PowerApps": "https://europe.api.powerapps.com",
        "microsoft.Flow": "https://europe.api.flow.microsoft.com",
        "microsoft.PowerAppsAdvisor": "https://europe.api.advisor.powerapps.com",
        "microsoft.ApiManagement": "https://management.EUR.azure-apihub.net"
      },
      "environmentFeatures": {
        "isOpenApiEnabled": false
      }
    },
    "displayName": "contoso (default)"
  }
]
```

:::info

All JMESPath queries are case sensitive

:::

### Ordering the dataset

Besides filtering, there are several use cases where it makes sense to order the returned result set. Lets say you want to retrieve SharePoint Online user activity, something that can be achieved using the following command `m365 spo report activityuserdetail --period D7 --output json`. You then might want to filter, but perhaps you want to also sort the result set based on dates or activity. The returned result looks similar to the `json` sample:

```
[
  {
    "Report Refresh Date": "2021-06-15",
    "User Principal Name": "garthf@contoso.com",
    "Is Deleted": "False",
    "Deleted Date": "",
    "Last Activity Date": "2020-07-07",
    "Viewed Or Edited File Count": "0",
    "Synced File Count": "0",
    "Shared Internally File Count": "0",
    "Shared Externally File Count": "0",
    "Visited Page Count": "0",
    "Assigned Products": "OFFICE 365 E3",
    "Report Period": "7"
  },
  {
    "Report Refresh Date": "2021-06-15",
    "User Principal Name": "sands@contoso.com",
    "Is Deleted": "False",
    "Deleted Date": "",
    "Last Activity Date": "",
    "Viewed Or Edited File Count": "152",
    "Synced File Count": "0",
    "Shared Internally File Count": "0",
    "Shared Externally File Count": "0",
    "Visited Page Count": "0",
    "Assigned Products": "OFFICE 365 E3",
    "Report Period": "7"
  },
  {
    "Report Refresh Date": "2021-06-15",
    "User Principal Name": "janets@contoso.com",
    "Is Deleted": "True",
    "Deleted Date": "2021-05-15",
    "Last Activity Date": "",
    "Viewed Or Edited File Count": "0",
    "Synced File Count": "0",
    "Shared Internally File Count": "0",
    "Shared Externally File Count": "0",
    "Visited Page Count": "0",
    "Assigned Products": "OFFICE 365 E3",
    "Report Period": "7"
  }
]
```

Combining sorting and filtering makes for a powerful cross-platform way of presenting your data. You are not dependent on `PowerShell` or `Bash` to get the result you are looking for.

For complete list of filter options check out the [JMESPath Examples](https://jmespath.org/examples.html).

---

## github-actions

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Automate your CI/CD workflow using CLI for Microsoft 365 in GitHub Workflows
sidebar_position: 12

## Automate your CI/CD workflow using CLI for Microsoft 365 GitHub Actions

[GitHub Actions](https://github.com/features/actions) help you automate your software development workflows in the same place you store code and collaborate on pull requests and issues. You can write individual tasks, called actions, and combine them to create a custom workflow.

### Actions

We have built and published actions to the [GitHub Marketplace](https://github.com/marketplace?type=actions) that will enable you to easily install and execute CLI for Microsoft 365 commands from within your own custom workflows.

#### CLI for Microsoft 365 Login

This action performs two roles, firstly it installs the CLI for Microsoft 365 into your build host agent and secondly, it creates a connection to your Microsoft 365 tenant which can then be used by other actions.

:::info

This action is required to be executed in a step before any other CLI for Microsoft 365 actions

:::

#### CLI for Microsoft 365 Deploy App

This action simplifies the installation and deployment of a SharePoint Framework app to either a tenant level or site collection level app catalog.

#### CLI for Microsoft 365 Run Script

This action provides the ability to execute an inline script or script file using either `bash` or `PowerShell` as the executing shell.

### Tutorial

#### Creating a basic workflow which authenticates with an Microsoft 365 tenant

We are going to assume that you have a GitHub repository already created, which you are also the owner of.

When connecting to any system or service, we need to make sure that the account details used to connect are kept in a safe and secure way. GitHub provides a way of storing these credentials in encrypted form in your repository, which can then be reused in your custom workflows.

First you will need to need to navigate, in your browser, to your repository on GitHub.com and go to the `Settings` tab, from here choose the `Secrets` item on the left hand menu.

You may have two options when registering secrets in order to log in to your tenant:

Using the `Add new secret` link, enter the `ADMIN_USERNAME` into the `Name` field and the username of the account that you are to use to connect to your Microsoft 365 tenant with, e.g. `user@tenant.onmicrosoft.com`. *Note: This account should not be protected with multi-factor authentication*

Repeat the above step to also store the account password which should be named `ADMIN_PASSWORD`.

Using the `Add new secret` link, enter the `APP_ID` into the `Name` field and the (client) id of the Microsoft Entra application to connect to your Microsoft 365 tenant with, e.g. `EXAMPLE-GUID-PLACEHOLDER`.

Repeat the above step to also store the application's encoded certificate which should be named `CERTIFICATE_ENCODED` and the tenant id which should be named `TENANT_ID`. If your certificate is encrypted with a password, then repeat one last time the previous step with a secret called `CERTIFICATE_PASSWORD`.

Now that we have secured the account credentials, we can start to create the workflow.

Select `Actions` tab and you will be presented with the `Get started with GitHub Actions` page. This will display a selection of templates to start your workflow from, however, for the purpose of this tutorial we will create a new workflow from scratch.

To do that, click the `Setup a workflow yourself` button which is placed on the far right of the page.

You will be presented with a screen displaying a file editor which has the below `yaml`. The `YAML` file represents a custom workflow and is sometimes referred to as `Build Definition as Code`.

```
name: CI

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v1
    - name: Run a one-line script
      run: echo Hello, world!
    - name: Run a multi-line script
      run: |
        echo Add other actions to build,
        echo test, and deploy your project.
```

The above configuration defines a simple workflow named `CI` that is triggered on the `push` of new code to the repository, it contains a single `build` that is executed on an `ubuntu` hosted agent and has multiple steps that, execute a single line script and multi line script, both printing text to the logs.

We will update the initial configuration as shown below, replacing the existing steps with the `CLI for Microsoft 365 Login` action instead.

```
  name: CI

  on: [push]

  jobs:
    build:

      runs-on: ubuntu-latest

      steps:

      - name: Login to tenant
        uses: pnp/action-cli-login@v3.0.1
        with:
          ADMIN_USERNAME:  ${{ secrets.ADMIN_USERNAME }}
          ADMIN_PASSWORD:  ${{ secrets.ADMIN_PASSWORD }}
```

```
  name: CI

  on: [push]

  jobs:
    build:

      runs-on: ubuntu-latest

      steps:

      - name: Login to tenant
        uses: pnp/action-cli-login@v3.0.1
        with:
          APP_ID: ${{ secrets.APP_ID }}
          CERTIFICATE_ENCODED: ${{ secrets.CERTIFICATE_ENCODED }}
          CERTIFICATE_PASSWORD: ${{ secrets.CERTIFICATE_PASSWORD }}
          TENANT: ${{ secrets.TENANT_ID }}
```

The `uses` property tells the build agent to use the `CLI for Microsoft 365` GitHub Action for the step, this will automatically become available when the workflow is triggered, no installation is required.

The action accepts an admin username and password (or an application id / encoded certificate), which are used to authenticate with your Microsoft 365 tenant, these credentials are provided by an environment variable called `secrets` which contains properties exposing the secured credentials that we saved earlier.

Lastly, we need to commit the `main.yaml` file to the repository, click the `Start Commit` button and click `Commit new file`. You may want enter a custom commit message at this point, however the default will be fine for this tutorial.

As we setup the workflow to be triggered on the `push` of new code to the repository, the `CI` workflow is automatically run when we initially created the workflow in the repository.

Select the `Actions` tab, this time you will be presented with a table that displays the `CI` run either in progress or completed, click on the run called `CI` in the table to view the workflow output logs.

You will see that all steps have a green tick, expanding the `Login tenant` step will display further detail generated from the `CLI for Microsoft 365 Login` action, with the last log confirming that the login was successful.

Congratulations! You have just setup your first custom workflow in a GitHub repository and successfully logged into Microsoft 365 using the `Microsoft 365 Login` action.

![CI Successful build](../images/github-actions-tutorial-success.png "CI Successful Build")

Sometimes, you would like to use the next (beta) version or a previous one of the CLI (because of a bug that is currently being addressed or to leverage a new feature to come).

The `CLI for Microsoft 365 Login` action provides an optional input to specify a version tag which can be `latest` (default if not specified), `next` or a specific one (`5.9.0`).

```
  name: CI

  on: [push]

  jobs:
    build:

      runs-on: ubuntu-latest

      steps:

      - name: Login to tenant
        uses: pnp/action-cli-login@v3.0.1
        with:
          APP_ID: ${{ secrets.APP_ID }}
          CERTIFICATE_ENCODED: ${{ secrets.CERTIFICATE_ENCODED }}
          CERTIFICATE_PASSWORD: ${{ secrets.CERTIFICATE_PASSWORD }}
          TENANT: ${{ secrets.TENANT_ID }}
          CLI_VERSION: next
```

Depending on the context, you will need to specify the tenant id.

The `CLI for Microsoft 365 Login` allows you to indicate the targeting tenant (default `common`). It can be `organization` (if using a Microsoft Entra app which is multitenant) or a tenant id.

```
  name: CI

  on: [push]

  jobs:
    build:

      runs-on: ubuntu-latest

      steps:

      - name: Login to tenant
        uses: pnp/action-cli-login@v3.0.1
        with:
          APP_ID: ${{ secrets.APP_ID }}
          CERTIFICATE_ENCODED: ${{ secrets.CERTIFICATE_ENCODED }}
          CERTIFICATE_PASSWORD: ${{ secrets.CERTIFICATE_PASSWORD }}
          TENANT: EXAMPLE-GUID-PLACEHOLDER
```

### How-To Guides

These guides presuppose some familiarity with using GitHub Actions and CLI for Microsoft 365.

#### Deploy an app using the CLI for Microsoft 365 Deploy App action

Create a `.yaml` file within the `.github/workflow` folder with the below build definition to deploy an app to a tenant level app catalog.

```
name: SPFx CI/CD with CLI for Microsoft 365

on: [push]

jobs:
  build:
    ##
    ## Build code omitted
    ##

  deploy:
    needs: build
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [10.x]

    steps:

    ##
    ## Code to get the package omitted
    ##

    - name: Login to tenant
      uses: pnp/action-cli-login@v3.0.1
      with:
        APP_ID: ${{ secrets.APP_ID }}
        CERTIFICATE_ENCODED: ${{ secrets.CERTIFICATE_ENCODED }}
        CERTIFICATE_PASSWORD: ${{ secrets.CERTIFICATE_PASSWORD }}
        TENANT: ${{ secrets.TENANT_ID }}

    - name: Deploy app to tenant app catalog
      id: M365clideploy
      uses: pnp/action-cli-deploy@v5.0.0
      with:
        APP_FILE_PATH: sharepoint/solution/spfx-m365-cli-action.sppkg
        SKIP_FEATURE_DEPLOYMENT: true
        OVERWRITE: true

    - name: Get the id of the app deployed
      run: echo "The id of the app deployed is ${{ steps.M365clideploy.outputs.APP_ID }}"
```

Alternatively, you can deploy the app to a site collection based app catalog by using the below step in replacement of the `Deploy app to tenant app catalog` step.

```
- name: Deploy app to a site collection app catalog
  id: M365clideploy
  uses: pnp/action-cli-deploy@v5.0.0
  with:
    APP_FILE_PATH: sharepoint/solution/spfx-m365-cli-action.sppkg
    SCOPE: sitecollection
    SITE_COLLECTION_URL: https://contoso.sharepoint.com/sites/teamsite
```

#### Execute an inline script using the CLI for Microsoft 365 Run Script action

Add this step to a `.yaml` build file contained within the `.github/workflows` folder to send an email from SharePoint to a user by executing the `spo mail send` command as an inline script.

```
- name: Send email
      uses: pnp/action-cli-runscript@v3.0.0
      with:
        M365_CLI_SCRIPT: m365 spo mail send --webUrl https://contoso.sharepoint.com/sites/teamsite --to 'user@contoso.onmicrosoft.com' --subject 'Deployment done' --body '<h2>CLI for Microsoft 365</h2> <p>The deployment is complete.</p> <br/> Email sent via CLI for Microsoft 365 GitHub Action.'
```

#### Execute a script file using the CLI for Microsoft 365 Run Script action

Add the respective script file to your repository and this step to a `.yaml` build file contained within the `.github/workflows` folder to create lists by executing the commands contained within the script file.

```
- name: Create lists
      uses: pnp/action-cli-runscript@v3.0.0
      with:
        M365_CLI_SCRIPT_PATH: ./script/lists.ps1 
```

### Reference

#### CLI for Microsoft 365 Login

View on [GitHub Marketplace](https://github.com/marketplace/actions/cli-for-microsoft-365-login)

#### Microsoft 365 Deploy App

View on [GitHub Marketplace](https://github.com/marketplace/actions/cli-for-microsoft-365-deploy-app)

The `APP_ID` of the app that has been deployed.

#### Microsoft 365 Run Script

View on [GitHub Marketplace](https://github.com/marketplace/actions/cli-for-microsoft-365-run-script)

:::warning

One of `M365_CLI_SCRIPT_PATH` / `M365_CLI_SCRIPT` is mandatory, in case both are defined `M365_CLI_SCRIPT_PATH` gets preference.

:::

### Contributions and Issues

Due to the requirement that a GitHub action must be located within its own repository, these actions are not managed within the main CLI for Microsoft 365 repository.

If you have any ideas or issues regarding any of the actions, please raise them within the issue list of their respective repositories.

---

## installing-cli

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Install the CLI
sidebar_position: 1

import AsciinemaPlayer from '../../src/components/AsciinemaPlayer';
import 'asciinema-player/dist/bundle/asciinema-player.css';

## Install the CLI for Microsoft 365

Thank you for your interest in the CLI for Microsoft 365. Following information will help you install the CLI for Microsoft 365 and keep it up to date.

### Prerequisites

To use the CLI for Microsoft 365 you need Node.js. The CLI has been tested with Node.js versions 18 and higher, but we recommend you to use the Node.js LTS version available at the moment. For more information on installing Node.js for your platform visit [https://nodejs.org](https://nodejs.org).

CLI for Microsoft 365 works on Windows, macOS and Linux and you can use it with any shell on these platforms.

### Install the CLI for Microsoft 365

CLI for Microsoft 365 is distributed as a Node.js package and published on [npmjs.com](https://www.npmjs.com). You can install it using your Node package manager, such as npm or Yarn.

To install the CLI for Microsoft 365, in the command line execute:

```
npm install -g @pnp/cli-microsoft365
```

If you're using Yarn, you can install the CLI for Microsoft 365 by executing:

```
yarn global add @pnp/cli-microsoft365
```

:::tip

We are regularly publishing beta versions of the CLI for Microsoft 365 with latest features and fixes. If you want to use the beta version of the CLI, add `@next` to the package name when installing the CLI, for example `npm install -g @pnp/cli-microsoft365@next`. Please note, that you can have installed either the beta version or the public version of the CLI but not both.

:::

### Check the installed version

To check which version of the CLI for Microsoft 365 you have installed on your computer, execute in the command line:

```
m365 version
```

Alternatively, you can check the version of the Node.js package you have installed, by executing:

```
npm ls -g --depth=0
```

The version of the CLI is the same as the version of the Node.js package distributing the CLI, so by using either of the commands you can control which version of the CLI you have installed.

### Check if a new version is available

We are continuously evolving the CLI for Microsoft 365 and adding more features to it. You can download new versions of the CLI from npmjs.com. To check, if a new version of the CLI for Microsoft 365 is available, execute in the command line:

```
npm outdated -g
```

For each package that you have installed globally, npm will show the version you have currently installed as well as the latest version available on npm.

If you want to check if a new beta version of the CLI for Microsoft 365 is available, execute in the command line `npm view @pnp/cli-microsoft365`. Next, compare the version listed as the `@next` tag with the version you have installed. Beta versions of the CLI for Microsoft 365 are tagged with source code commits so that it's easy for the team to debug it in case of any issues.

```
$ npm view @pnp/cli-microsoft365

{ name: '@pnp/cli-microsoft365',
  description: 'CLI for managing Microsoft 365 configuration',
  // highlight-start
  'dist-tags': { next: '0.5.0-beta.fe510b6', latest: '0.4.0' },
  // highlight-end
  versions:
  [ '0.1.0-beta.b35346a',
    '0.1.0-beta.b7db425',
    '0.1.0-beta.b85510d',
    '0.1.1-beta.25b1725',
    ...
```

### Update the CLI

To update the CLI, execute in the command line:

```
npm install -g @pnp/cli-microsoft365@latest
```

This will download and install the latest public version of the CLI for Microsoft 365. If you want to update to the latest beta version of the CLI, replace `@latest` with `@next`.

:::info

New version of the CLI for Microsoft 365 often contains new commands. Don't forget to update command completion for your terminal to get suggestions for the latest commands added in the CLI. For more information see the article on [command completion](completion.mdx).

:::

### Uninstall the CLI

:::warning

Before uninstalling the CLI, log out from Microsoft 365 using the `logout` command. CLI for Microsoft 365 persists connection information on your computer and if you don't log out before uninstalling the CLI, this information will be left on your computer and you will have to remove it manually. For more information see the article on [persisting connection information](../concepts/persisting-connection.mdx)

:::

To uninstall the CLI for Microsoft 365, execute in the command line:

```
npm uninstall -g @pnp/cli-microsoft365
```

This command will remove all CLI for Microsoft 365 files from your computer.

If you have configured command completion for the CLI for Microsoft 365 in your terminal, remove the completion following instructions specific to your terminal, to avoid errors in your terminal.

---

## manage-microsoft-365-apps

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Manage Microsoft 365 apps with the CLI 
sidebar_position: 15

## Manage Microsoft 365 apps with the CLI for Microsoft 365

When developing Microsoft 365 apps, you need to register them with the Microsoft cloud. You do this by creating a Microsoft Entra application registration. An application registration contains information about your app such as its name, type (for example if it's a client app or a web app) or API permissions. Typically, you manage these settings through the Azure portal. CLI for Microsoft 365 contains a set of commands that simplify managing application registrations for your Microsoft 365 apps. What's more, using CLI for Microsoft 365 you can automate create Microsoft Entra apps to allow developers in your team share their configuration without blocking each other.

### Step 1: Create Microsoft Entra application registration

You start bringing your app to Microsoft 365 by creating an application registration in Microsoft Entra ID. Using CLI for Microsoft 365, you can do this using the `m365 entra app add` command. For example, if you're building a single-page application, you'd execute:

```
m365 entra app add --name 'My single-page app' --platform spa --redirectUris 'https://myspa.azurewebsites.net,http://localhost'
```

With this one command, CLI for Microsoft 365 will create a new Microsoft Entra application registration and configure its authentication mode to a single-page application with the specified two redirect URLs.

:::tip

There are many settings that you can configure for application registrations, so be sure to check the [documentation for the `m365 entra app add` command](../cmd/entra/app/app-add.mdx) for more examples.

:::

This one-liner is great to share with your dev team so that each developer can create their own application registration that they can manage as they work on the app. If your app's configuration is complex, you can also choose to export the existing manifest and create a new application registration from it! But there's more.

### Step 2: Store information about your Microsoft Entra app in your project

As you work with Microsoft 365 apps, you'll be creating quite a few application registrations in Microsoft Entra ID. Over time, it might be hard for you to keep track of which one is which and where you need to apply changes.

To help you, CLI for Microsoft 365 offers you two things. First, when creating a application registration for your Microsoft 365 app, store a reference to it. You do this, by extending the `m365 entra app add` command with the `--save` flag:

```
m365 entra app add --name 'My single-page app' --platform spa --redirectUris 'https://myspa.azurewebsites.net,http://localhost' --save
```

When you use the `--save` flag, CLI for Microsoft 365 will create the `.m365rc.json` file in the current working directory and write to it the ID and name of the newly created application registration. If the file exists already, CLI for Microsoft 365 will add the new information to it. That way you can track which application registration belongs to your project without having to manually locate them in the Azure Portal! And if you're building complex solutions with multiple Microsoft Entra apps, you can keep track of all of them in one place too!

After you stored the reference to your Microsoft Entra apps in your projects, you're ready to use the `app` commands from CLI for Microsoft 365.

### Step 3: Manage Microsoft Entra application registrations for Microsoft 365 apps

CLI for Microsoft 365 exposes a set of `app` commands (`m365 app *`) that let you manage your Microsoft 365 app projects. For example, using the [`m365 app permission list`](../cmd/app/permission/permission-list.mdx) command, you can easily retrieve API permissions for your Entra app.

See the list of `app` commands in the **Commands** section of this documentation for the complete reference of supported operations.

---

## run-cli-in-docker-container

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Run CLI in a Docker Container
sidebar_position: 4

## Run CLI for Microsoft 365 in a Docker Container

You can use Docker to run a standalone Linux container with CLI for Microsoft 365 and PowerShell pre-installed, with command completion (tab) automatically configured for you in both `bash` and `pwsh`, without having to install any of the required dependencies on your host machine. We've also included some useful utilities in the container for you such as `curl` and `jq`.

### Prerequisites

To use the published Docker images, you will first need to have Docker installed and configured on your host machine. Please refer to the Docker documentation on how to [install Docker](https://docs.docker.com/get-docker/) on Windows, Mac and Linux.

### Install and run latest

To install and run the latest version of CLI for Microsoft 365, use the `docker run` command and specify the CLI docker image name.

```
docker run --rm -it m365pnp/cli-microsoft365:latest
```

Executing this command for the first time will download the image onto your machine and start the container and invoke an interactive session automatically `(-it)`, displaying a bash shell prompt.

You can exit from the prompt by closing the terminal window or typing `exit`. When you exit the container it will be automatically stopped to free up system resources `(--rm)`.

Alternatively, you can use PowerShell as the default shell by passing `pwsh` into the `docker run` command after the image name.

```
docker run --rm -it m365pnp/cli-microsoft365:latest pwsh
```

:::info

Authentication information is not persisted in the Docker container. When you exit from the container, you will need to authenticate with your Microsoft 365 tenant the next time you run the container.

:::

### Install and run beta

We regularly release beta versions of the CLI, to install and run the latest beta release use the `next` tag.

```
docker run --rm -it m365pnp/cli-microsoft365:next
```

### Install and run specific versions

We have published Docker images for every minor release of v3 of CLI for Microsoft 365 to date.

To install and run a specific version of the CLI, state the version number as a tag after the image name.

```
docker run --rm -it m365pnp/cli-microsoft365:3.0.0
```

You can also install and run specific beta versions of the CLI, state the beta version as a tag after the image name.

```
docker run --rm -it m365pnp/cli-microsoft365:3.4.0-beta.0dbd08d
```

### Using JMESPath Terminal to author JMESPath queries

One of the best ways to learn the JMESPath language is to experiment by creating your own JMESPath expressions, to make this easier for you we have bundled the JMESPath Terminal library to make it easy for you to see the results of your JMESPath expressions immediately as you type.

The JMESPath Terminal accepts piped JSON input in both `bash` and `pwsh` prompts, for example, executing `m365 tenant serviceannouncement health list | jpterm` will pipe the response output from the command into a JMESPath Terminal interactive session.

![JMESPath Terminal](../images/run-cli-in-docker-container/jpterm-example.png)

:::info

For more information on how to use JMESPath Terminal, please consult the [documenation](https://github.com/jmespath/jmespath.terminal).

:::

### Execute script in container

In scenarios where you may already have a script that uses the CLI for Microsoft 365 and you want to execute it within the container, you can use a volume mount to share files on your host machine with the Docker container.

For example, lets say we have a script called `test.sh` and we want to execute that script inside the container. We can do this by mapping the current working directory on our host machine to the working directory in the container `(-v)`, pass `bash` as the shell we want to use and the name of the file that we want to execute as additional arguments.

```
docker run -it -v ${PWD}:/home/cli-microsoft365/scripts m365pnp/cli-microsoft365:latest bash scripts/test.sh
```

Alternatively, if we want to execute a PowerShell script, you can do this in the same way.

```
docker run -it -v ${PWD}:/home/cli-microsoft365/scripts m365pnp/cli-microsoft365:latest pwsh scripts/test.ps1
```

:::info

We have created a non-root user called `cli-microsoft365` inside the container.  When the container starts, the working directory is set to the home directory of this user, hence the need to add `/home/cli-microsoft365` to the volume mapping.

:::

### Set Environment Variables

In scenarios where you need to set environment variables, for example, you want to use a custom Microsoft Entra identity identity when logging into your Microsoft 365 tenant using the CLI. You can set these variables by passing them in as options arguments `(-e)` into the `docker run` command.

```
docker run --rm -it -e "CLIMICROSOFT365_ENTRAAPPID=EXAMPLE-GUID-PLACEHOLDER" -e "CLIMICROSOFT365_TENANT=EXAMPLE-GUID-PLACEHOLDER" m365pnp/cli-microsoft365:latest
```

### Combining script and environment variables

Combining scripts and environment variables is a powerful way to run the CLI in Docker, we can set environment variables which we can reference in the script that is executed in the running container and also.

```
docker run --rm -it -v ${PWD}:/home/cli-microsoft365/scripts -e "CLIMICROSOFT365_ENTRAAPPID=EXAMPLE-GUID-PLACEHOLDER" -e "CLIMICROSOFT365_TENANT=EXAMPLE-GUID-PLACEHOLDER" -e "M365_USER=user@contoso.com" -e "M365_PASSWORD=password" m365pnp/cli-microsoft365:next pwsh scripts/script.ps1
```

We can reference the environment variables passed in to the `docker run` command and use them in the script, in this example, passing the username and password variables into the `m365 login` command to login in to Microsoft 365 using password authentication.

```
m365 login --authType password --userName $env:M365_USER --password $env:M365_PASSWORD
```

### Update Docker Image

We will be regularly updating the images of the `latest` and `next` tags, to ensure you have the most upto date version of these images, you can update your local image using `docker pull` specifying the version you want to update using the relevant tag.

```
docker pull m365pnp/cli-microsoft365:latest
```

### Uninstall Docker Image

If you would like to remove an image from your host machine, you can use the `rmi` command, specifying the version you wish to remove as a tag after the image name.

```
docker rmi m365pnp/cli-microsoft365:latest
```

### Published Tags

See the list of available tags on the m365pnp/cli-microsoft365 repository on [Docker Hub](https://hub.docker.com/repository/docker/m365pnp/cli-microsoft365/).

---

## use-cli-api

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Use CLI programmatically
sidebar_position: 16

## Use CLI for Microsoft 365 programmatically

Typically, you'll work with CLI for Microsoft 365 in a command line. You'll either call specific commands or build automation scripts to combine multiple tasks. But if  you're building software, you might want to use CLI for Microsoft 365 from your code.

### Integrate CLI for Microsoft 365 in your app

If you build apps in Node.js, you can integrate CLI for Microsoft 365 using its API. This API lets you call any of the CLI's commands. The following examples show how you could call several CLI for Microsoft 365 commands in a Node.js app:

```
import { executeCommand } from '@pnp/cli-microsoft365';

try {
  // m365 status --output text
  const status = await executeCommand('status', { output: 'text' });

  if (status.stdout === 'Logged out') {
    // m365 login --output text
    await executeCommand('login', { output: 'text' }, {
      stdout: message => console.log(message)
    });
  }
  
  // m365 spo site list
  const siteList = await executeCommand('spo site list', {});
  const sites = JSON.parse(siteList.stdout);

  if (sites.length === 0) {
    throw new Error('No sites found');
  }
  
  const siteUrl = sites[0].Url;
  // m365 spo web get --webUrl https://contoso.sharepoint.com/sites/project-x --withGroups
  const siteInfo = await executeCommand('spo web get', { webUrl: siteUrl, withGroups: true });

  console.log(siteInfo.stdout);
  
} catch(err) {
  console.error(err);
}
```

You start with importing the `executeCommand` function from CLI for Microsoft 365. CLI doesn't expose all of its logic externally, but rather just the function that allows you to run CLI's commands. This could change in the future.

Next, you execute a command by passing the command's name without the `m365` prefix, and its options. After the command completed its execution, it resolves a Promise with the command's output. The `stdout` property contains the main command output. The `stderr` property would contain verbose, debug and error output that in command line would be sent to stderr. The output in the Promise is a string in the format specified in the `output` option passed to `executeCommand`.

In some cases, like when calling the `login` command, you might need to get the command output while it executes. In the case of the `login` command, it will contain the instructions to complete the device login flow. You can get this output by passing to the `executeCommand` function a third argument with listeners attached to stdout and stderr output.

```
executeCommand('login', { output: 'text' }, {
  stdout: message => console.log(message)
});
```

:::info

You shouldn't use both listeners and output from Promises. All command output is sent to the registered listeners and exposed in the end through the resolved Promise. If you would send output from both the listener and Promise to the console, you'd end up with the same output printed twice. In the code sample above you see that for all commands you work with the output from Promises but for the `login` command you use a listener because you want to get login instructions while the command is still running.

:::

---

## using-cli

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Use the CLI
sidebar_position: 2

import AsciinemaPlayer from '../../src/components/AsciinemaPlayer';
import 'asciinema-player/dist/bundle/asciinema-player.css';

## Use the CLI for Microsoft 365

Information in this section will help you understand how the CLI for Microsoft 365 works and how you can use it most effectively.

### Start the CLI

To use CLI for Microsoft 365, execute specific commands directly from the command line.

:::warning

When using the CLI for Microsoft 365, each CLI command must be prepended with `microsoft365` or `m365` for short. Without this, your shell will not know how the particular command should be executed.

:::

Using the CLI for Microsoft 365 directly from the command line is invaluable if you want to write scripts consisting of a number of CLI for Microsoft 365 and other commands combined together. Additionally, you keep the access to all system commands and other CLIs available on your computer.

### List available commands

To list commands available with the CLI for Microsoft 365 type `help` in the CLI prompt, or `m365 help` directly in your shell.

Commands in the CLI for Microsoft 365 are combined into groups. You can list the commands available in the particular group by typing `help <group>`, for example `help spo` to list all commands related to SharePoint Online, or `m365 help spo` directly in your shell.

### Get command help

Each command in the CLI for Microsoft 365 comes with help describing the command's purpose, available options and any other relevant details as well as related resources. To get the basic help information with command's description and available options, type `help <command>` or `m365 help <command>` in the shell, for example to get help for the `spo cdn get` command, type in the shell `m365 help spo cdn get`.

To get the complete help information including background information, examples and links to related information, use the `--help` option, for example `m365 spo cdn get --help`. This ability is also useful if you've already typed some options and don't want to lose your input but want to access the help, for example: `m365 spo cdn get --type Private --help`.

### Required and optional command options

Commands in the CLI for Microsoft 365 often contain options that determine what the particular command should do. Command options vary from the URL of the site for which you would like to retrieve more information, to the type of Microsoft 365 CDN that you would like to manage.

Some options are required and necessary for the particular command to execute, while other are optional. When listing available options for the particular command, CLI for Microsoft 365 follows the naming convention where required options are wrapped in angle brackets (`< >`) while optional options are wrapped in square brackets (`[ ]`). For example, in the `spo cdn origin add` command, the origin you want to add is required (`-r, --origin <origin>`), while the type of CDN for which this origin should be added is optional (`-t, --type [type]`) and its value defaults to `Public`.

### Boolean options (true/false)

Some options in the CLI expect boolean values like `true` or `false`. The CLI for Microsoft 365 has the following definition for booleans:

:::info[Definition of Booleans]

Booleans are case-insensitive and are represented by the following values.  
True: 1, yes, true, on  
False: 0, no, false, off

:::

This means that whenever you need to pass a boolean value to a command, you can use any of the values listed above. For example, to configure if Planner is allowed in your organization you can execute the following:

```
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

```
m365 planner tenant settings set --isPlannerAllowed $true
m365 planner tenant settings set --isPlannerAllowed $false
```

### Values with quotes

In cases, when the option's value contains spaces, it should be wrapped in quotes. For example, to create a modern team site for the _CLI for Microsoft 365_ team, you would execute in the shell:

```
m365 spo site add --alias office365cli --title "CLI for Microsoft 365"
```

When the value, that you want to provide contains quotes, it needs to be wrapped in quotes as well, for example to pass a JSON value in the CLI prompt, you would execute:

```
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content '{"abc": "def"}'
```

### Values starting with a dash (-)

In cases, when the option's value starts with a dash (-), specify the option's value using the `=` operator. For example, to get a planner task with ID _-9rMKQooUjZdxgv1qQVZYABEuw_, execute in the shell:

```
m365 planner task get --id=-9rMKQooUjZdxgv1qQVZYABEuw
```

### Setting empty values

In cases, when the option's value is empty, specify the value using the `=` operator. For example, to pass an empty string argument to option `description`, you should execute:

```
m365 spo contenttype set --description=""
```

### Working with SharePoint URLs in `spo` commands

CLI for Microsoft 365 contains a number of commands for managing SharePoint Online. Each of these commands requires you to specify the site or web on which you want to execute the command. For example, to get information about a site collection located at `https://contoso.sharepoint.com/sites/contoso`, you'd execute:

```
m365 spo site get --url https://contoso.sharepoint.com/sites/contoso
```

If you executed an `spo` command previously, CLI for Microsoft 365 already knows the hostname of your SharePoint Online tenant. In such case, you can use a server-relative URL as well:

```
m365 spo site get --url /sites/contoso
```

If you try to use a server-relative URL but CLI for Microsoft 365 doesn't know of your SharePoint Online URL yet, you will see an error prompting you to either use an absolute URL or set the SPO URL using the `spo set` command:

```
m365 spo set --url https://contoso.sharepoint.com
```

You can also execute a command like `m365 spo site list` that will automatically detect your SharePoint Online tenant URL for you.

To check if CLI detected the SPO URL previously, use the `m365 spo get` command.

### Passing complex content into CLI options

When passing complex content into CLI options, such as JSON strings, you will need to properly escape nested quotes. The exact way to do it, depends on the shell that you're using. Alternatively, you can choose to pass complex content by storing the complex content in a file and passing the path to the file prefixed with an `@`, for example:

```
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content @themeScript.json
```

CLI for Microsoft 365 will load the contents from the specified file and use it in the command that you specified.

You can use the `@` token in any command, with any option that accepts a value.

`@` is a special character in PowerShell. If you use CLI for Microsoft 365 in PowerShell and want to use the `@` token, you'll need to escape with a backtick, for example:

```
m365 spo sitescript add --title "Contoso" --description "Contoso theme script" --content `@themeScript.json
```

### Escaping double quotes in PowerShell

PowerShell Versions 5 to 7.2 have an [issue with escaping double quotes](https://github.com/PowerShell/PowerShell/issues/1995). Command arguments are being parsed twice for tools like the CLI. Once by PowerShell and once by the CLI for Microsoft 365 executable that's being called by PowerShell. The result is that you need to escape quotes twice. The issue should be resolved from version 7.3.

As an example, see the following code:

```
m365 spo listitem set --webUrl "<some-url>" --id 1 --listTitle somelist --SomeField "{ `"test1`": `"test2`" }"
```

While correctly escaped, it would result in the following being saved to sharepoint: `{ test1: test2 }`. The double quotes are missing.

The following two methods resolve this:

#### Method 1: Escaping twice

Escape the double quotes twice. Once for powershell using the backtick (`) and once for the executable, using a backslash.

```
m365 spo listitem set --webUrl "<some-url>" --id 1 --listTitle somelist --SomeField "{ \`"test1\`": \`"test2\`" }"
```

#### Method 2: Using verbatim strings with single quotes

Use single quotes to start a verbatim string. The double quotes need not be escaped for powershell using the backtick. However, they do need to be escaped for the executable, using a backslash.

```
m365 spo listitem set --webUrl "<some-url>" --id 1 --listTitle somelist --SomeField '{ \"test1\": \"test2\" }'
```

:::info

Remember, instead of escaping, it's also possible to [feed complex content from a file](./using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER).

:::

### Handling errors in PowerShell

CLI for Microsoft 365 by default outputs errors to stderr. Unlike other shells, PowerShell works differently as it has six distinct output streams. This behavior can lead to unexpected results, such as PowerShell continuing execution even after setting $ErrorActionPreference = "Stop". For more information on PowerShell's output streams, see [handling output and errors](https://learn.microsoft.com/en-us/powershell/scripting/learn/shell/running-commands?view=powershell-7.5#handling-output-and-errors). To address these differences, you can use the following settings and helper function to ensure that CLI errors are treated as errors.

```
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

```
try {
  m365 spo list get --webUrl "https://contoso.sharepoint.com/sites/Marketing" --title "Non Existent" | Invoke-CLICommand
}
catch {
  Write-Host "Failed retrieving list." -ForegroundColor Red
  Write-Host "Error: $($_.Exception.Message)" -ForegroundColor Red
}
```

### `@meId` and `@meUserName` tokens

CLI for Microsoft 365 contains a number of commands that require you to provide a user ID or username. If you want to pass these values for the current user, instead of looking them up, you can use the built-in tokens. With the `@meId` token you can specify the ID of the current user. Using the `@meUserName` token you can specify the username of the current user.

For example:

```
m365 entra user get --id "@meId"
```

will execute as `m365 entra user get --id "EXAMPLE-GUID-PLACEHOLDER"`.

When you execute:

```
m365 entra user get --userName "@meUserName"
```

it will run as `m365 entra user get --userName "admin@contoso.onmicrosoft.com"`.

Both tokens are resolved based on the information stored in the access token. You can use the `@` token in any command, with any option that accepts a value.

### Verbose and debug mode

By default, commands output only the information returned by the corresponding Microsoft 365 API, whether the command result or error. You can choose for a more user-friendly output by using the `--verbose` option or setting the `CLIMICROSOFT365_VERBOSE` environment variable to `1`. For example: by default, when checking status of the Microsoft 365 Public CDN, you would see:

```
$ m365 spo cdn get
true
```

After adding the `--verbose` option, the output would change to:

```
$ m365 spo cdn get --verbose
Retrieving status of Public CDN...
Public CDN at https://contoso-admin.sharepoint.com is enabled
```

If you're experiencing problems when using the CLI for Microsoft 365, you can use the `--debug` option or set the `CLIMICROSOFT365_DEBUG` environment variable to `1`. On top of the output from the verbose mode, the debug mode will provide you with detailed information about all requests and responses from the Microsoft 365 APIs used by the command.

### Command completion

To help you use its commands, CLI for Microsoft 365 offers you the ability to autocomplete commands and options that you're typing in the prompt. Some additional setup, specific for the shell and terminal that you use, is required to enable command completion for CLI for Microsoft 365. For more information on configuring command completion for the CLI for Microsoft 365 see the [command completion](completion.mdx) article.

### Disable automatic checking for updates

Each time you run CLI for Microsoft 365, it will automatically check if there is a new version available and prompt you with update instructions if that's the case. If you use CLI for Microsoft 365 in CI/CD or in scripts and want to make it run faster, you can disable the check by setting the `CLIMICROSOFT365_NOUPDATE` environment variable to `1`.

---

## using-cli-context

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Use CLI for Microsoft 365 context
sidebar_position: 17

## Use CLI for Microsoft 365 context

CLI for Microsoft 365 context provides unique functionality to save options and their values in a central place. The options saved in the context may be used in any kind of command execution. This means you may provide fewer options or no options at all. Using a context will help you save on keystrokes.
It may be especially useful if you want to group all your script parameters in a single place.
A context is saved in a m365rc.json file in your working directory. It can be committed to Source Control along with your script files. It can be managed by executing commands.

### How to get started

To create an empty context we may execute the following command:

```
m365 context init
```

To add or update an option in the context use the `m365 context option set` command. The `name` is used to define the option name and `value` is used to define its default value. For example, if we want to set the option `listTitle` to `test list`, we should execute:

```
m365 context option set --name 'listTitle' --value 'test list'
```

To remove a specific option from the context we can run:

```
m365 context option remove --name "listTitle"
```

In order to remove the full context we may execute the following command:

```
m365 context remove
```

### How does it work

When a command is executed, the CLI will first check for the `.m365rc.json` file in the working directory. If present, the CLI will check if any of the options defined in it may be used for the currently executed command. If that's the case the CLI will execute this command with the option and its value taken from the context.

When an option is available in the context and also used in the command itself, the value defined in the command will take precedence.

### Example

Consider the below context:

```
{
  "context": {
    "groupName": "Sales group",
    "listTitle": "Expense tracker"
  }
}
```

When we execute:

```
m365 context option set --name "webUrl" --value "https://contoso.sharepoint.com/sites/sales"
```

The result of the above will be a new option added to the context:

```
{
  "context": {
    "groupName": "Sales group",
    "listTitle": "Expense tracker",
    "webUrl": "https://contoso.sharepoint.com/sites/sales"
  }
}
```

Next, if we execute the following:

```
m365 spo listitem list
```

As a result, we will get a list of items from `Expense tracker` list from `https://contoso.sharepoint.com/sites/sales` even though we did not specify any of the required options, those were taken from the context.

Now when we execute:

```
m365 spo listitem list --listTitle "Issue tracker"
```

We will get all items from list `Issue tracker` from `https://contoso.sharepoint.com/sites/sales` site.

If we execute:

```
m365 spo list get
```

The command will fail. Although the `webUrl` option will be used, which is the required one, but the `listTitle` will not be used as the command needs `title` option instead to get the specified list.

### Related commands

---

## using-cli-vs-code-extension

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Use CLI for Microsoft 365 VS Code extension
sidebar_position: 14

## Use CLI for Microsoft 365 VS Code extension

If you like using Visual Studio Code to write scripts as your day-to-day tool then you might want to try the CLI for Microsoft 365 Visual Studio Code extension to boost your productivity. 
It provides various features that may be helpful when creating scripts using CLI for Microsoft 365.

You may download the Visual Studio Code extension directly from the [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=EXAMPLE_SECRET_VALUE_PLACEHOLDER) or install it from the VS Code extension gallery.

As of this writing, this extension has the following features.

### Integrated docs for every CLI for Microsoft 365 command

The extension allows you to browse CLI for Microsoft 365 docs about every command inside Visual Studio Code.

![Docs view](../images/cli-vs-code-extension/docs.png)

No more switching between your IDE and browser is needed. 
With a single click, you can open the docs page in your default browser, or open a sample gallery showing all samples using the command.

### Sample gallery

The sample gallery allows you to browse all samples available for CLI for Microsoft 365 directly from CLI and PnP Script samples.
From the samples gallery, you may go to the sample location or create a file prefilled with the CLI for Microsoft 365 sample script. 
It is possible to search for samples by title, authors, and commands used in samples.

![samples view](../images/cli-vs-code-extension/samples.png)

### Snippets with all possible commands

The extension provides coding snippets for every CLI for Microsoft 365 command.
The command is added with all obligatory parameters.
It is possible to quickly cycle between parameters using your `tab` key.
Each CLI command snippet is also provided with the same description as may be found in the docs which is a great help to quickly understand the command's functionality.

![snippets](../images/cli-vs-code-extension/snippets.png)

---

## using-own-identity

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Use your own Microsoft Entra identity
sidebar_position: 10

## Use your own Microsoft Entra identity

When you use the CLI for Microsoft 365 to connect to your tenant for the first time, you can either start with the [m365 setup](../cmd/setup.mdx) command or define the `appId` and `tenant` options directly during login.

To simplify the process of creating an Microsoft Entra application registration with all the necessary permission scopes, you can use the [m365 setup](../cmd/setup.mdx) command. This command can set up an application registration with a wide range of permissions, including those that require administrative consent. This makes it easy to get started with the CLI and try out commands across many CLI for Microsoft 365 workloads in your tenant without having to manually manage permissions for different commands in Azure.

While this approach is convenient for development and test environments, using these levels of permissions against production environments may be inconvenient. Administrators might be uncomfortable granting such permissions to an application within their environment. Therefore, it's important to carefully consider the permissions you grant when setting up your application registration for production use.

In this scenario, administrators will want to provide their own Microsoft Entra application registration to use with the CLI to enable greater control over the permissions that are granted.

This tutorial will walk you through how to create your own Microsoft Entra application with permissions restricted to only read information about SharePoint Online Site Collections and how to use this custom application with the CLI for Microsoft 365.

### Register Microsoft Entra application in your tenant

We first need to register a new Microsoft Entra application in your tenant, to do this we will need to navigate to the [Azure Portal](https://portal.azure.com).

Select `Microsoft Entra ID` from the global menu, select `app registrations` in the Microsoft Entra ID blade and then select the `New registration` action button to open the `Register an application` form.

[![New application registration](../images/using-own-identity/new-app-registration.png)](../images/using-own-identity/new-app-registration.png)

In the form, enter a name for your new application, for the purpose of this tutorial let's use `Custom PnP CLI for M365`. You can always change this later if you want. Leave the `Supported account types` and `Redirect URI` values as they are and select the `Register` button at the foot of the form to create your custom application.

[![Register an application](../images/using-own-identity/register-an-application.png)](../images/using-own-identity/register-an-application.png)

After the application has been created, you will be presented with the blade for your application displaying an overview of some properties of the application. At this point it is a good idea to take note of two key pieces of information that we will need later.

[![Client and Tenant ID](../images/using-own-identity/client-and-tenantid.png)](../images/using-own-identity/client-and-tenantid.png)

Take a copy of both the `Application (client) ID` and `Directory (tenant) ID` values and save them to a place for you to refer back to them later.

### Configure Authentication settings

We next need to configure our new application so that it can be used with the CLI for Microsoft 365. To do this we need to select `Authentication` in the `Custom PnP CLI for M365` blade menu.

This will present you with three sections: `Platform configuration`, `Supported account type` and `Advanced settings`.

Select the `Add a platform` button to open up the `Configure platforms` menu and under the `Mobile and desktop applications` heading, select `Mobile and desktop applications`. This will open another menu called `Configure Desktop + Devices` displaying a section called `Redirect URIs` and a list of checkboxes with some pre-defined URIs.

[![Configure platforms](../images/using-own-identity/configure-platforms.png)](../images/using-own-identity/configure-platforms.png)

Select the first option in the list, `https://login.microsoftonline.com/common/oauth2/nativeclient` and select the `Configure` button at the foot of the menu.

[![Configure Desktop + Devices](../images/using-own-identity/configure-desktop-and-devices.png)](../images/using-own-identity/configure-desktop-and-devices.png)

This will refresh the `Authentication` blade and will display the Redirect URI we just chose from the menu.

[![Mobile and desktop applications](../images/using-own-identity/mobile-and-desktop-applications.png)](../images/using-own-identity/mobile-and-desktop-applications.png)

:::info

This Redirect URI is specific to the use of authentication methods that do not use a web interface for authenticating users and are therefore called `Native Clients`. This is the category that the CLI for Microsoft 365 falls into.

:::

Moving on, we can skip over the `Supported account type` section, as this is defaulted to `Accounts in this organizational directory only (<tenant> only - Single tenant)` meaning, that only users within the current tenant directory can use this application. In the `Advanced settings` section, we need to enable the `Allow public client flows` toggle, as we are using the `Device code flow` method to authenticate to our tenant using the CLI for Microsoft 365.

[![Advanced settings](../images/using-own-identity/advanced-settings.png)](../images/using-own-identity/advanced-settings.png)

To make sure all these changes are applied, select the `Save` button before moving on.

### Configure API Permissions

Now that we have configured the application to work with the CLI for Microsoft 365, we next need to grant what permissions the CLI will have within our tenant. Select the `API permissions` in the `Custom PnP CLI for M365` blade menu.

You will see a section called `Configured permissions` with one permission already granted. This is the default permission which allows the application to sign in the user account used when authenticating to the Microsoft Graph.

[![Configured permissions](../images/using-own-identity/configured-permissions.png)](../images/using-own-identity/configured-permissions.png)

Select the `Add a permission` button to open the `Request API permissions` menu. As we are only interested in granting our application access to SharePoint Online for the purpose of this tutorial, select `SharePoint` in the list of APIs that are available.

[![Request API permissions](../images/using-own-identity/request-api-permissions.png)](../images/using-own-identity/request-api-permissions.png)

This opens the menu with two options: `Delegated permissions` or `Application permissions`. As we are going to be communicating with the SharePoint Online APIs as the authenticated user, select `Delegated permissions`. This will display a list of available permissions that we can choose from.

For the purpose of this tutorial we only want to grant read access to SharePoint Online, so expand the `AllSites` grouping and select the `AllSites.Read` permission. Next, select the `Add permissions` button to apply these permissions.

[![SharePoint Online Delegated permissions](../images/using-own-identity/spo-delegated-permissions.png)](../images/using-own-identity/spo-delegated-permissions.png)

:::warning

Note that the `AllSites.Read` permission does not directly grant the signed-in user access to all sites in SharePoint Online. As we authenticate as the signed-in user, that user must still have access to the SharePoint sites that we want to return information about, otherwise the SharePoint Online API calls will fail with a `401 Unauthorized` error.

:::

You will be presented with the `Configured permissions` section again but this time the `AllSites.Read` permission will be shown under the `SharePoint` grouping.

[![SharePoint Online Configured permissions](../images/using-own-identity/spo-configured-permissions.png)](../images/using-own-identity/spo-configured-permissions.png)

:::warning

Note that when executing tenant level SharePoint Online commands, the CLI will attempt to autodiscover your tenant URL.

It will first check for the presence of an environment variable containing the tenant URL, which can be set by using [`m365 spo set`](../cmd/spo/spo-set.mdx) command.

If this cannot be found, a request will be made to the Microsoft Graph. For this request to be successful, you must ensure that you have at least the `Sites.Read.All` permission granted to your application.

:::

This completes the configuration required in the Azure portal. We can now move onto configuring the CLI for Microsoft 365 to use our custom application to login to Microsoft 365.

### Create environment variables

To configure the CLI for Microsoft 365 to use our newly created custom application, we need to tell it the Client ID of our custom application and the Tenant ID of where the custom application has been created.

To do that, we need to create two environment variables, named `CLIMICROSOFT365_ENTRAAPPID` and `CLIMICROSOFT365_TENANT`, giving them the values that you saved earlier.

How you set the environment variables depends on the operating system and shell that you are using.

If you are on Windows, you can set the environment variables using the `$env:<variable-name>` approach in a PowerShell session.

```
$env:CLIMICROSOFT365_ENTRAAPPID="EXAMPLE-GUID-PLACEHOLDER"
$env:CLIMICROSOFT365_TENANT="EXAMPLE-GUID-PLACEHOLDER"
```

:::tip

Execute `$env:CLIMICROSOFT365_ENTRAAPPID` and `$env:CLIMICROSOFT365_TENANT` to verify that the environment variables have been created correctly

:::

If you are using Linux or macOS, you can set the environment variables using the `export` command from your terminal prompt.

```
export CLIMICROSOFT365_ENTRAAPPID=EXAMPLE-GUID-PLACEHOLDER
export CLIMICROSOFT365_TENANT=EXAMPLE-GUID-PLACEHOLDER
```

:::tip

Execute `printenv` to verify that the environment variables have been created correctly

:::

Now that we have set our environment variables, we are now ready to use our custom application to log in with using the CLI for Microsoft 365.

### Login and consent

For the purpose of this tutorial, we will be using the `Device code flow` to interactively authenticate with an Microsoft 365 tenant. As this is the first time that we will have used the custom application to authenticate, we will also be required to give our consent.

At your terminal session, execute `m365 login` to start the authentication process, a login device code will be displayed along with a link to a web page where it needs to be entered. Navigate to [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin), enter the code into the input field and select `Next`. You will then be presented with either a login screen or accounts that you have already logged in to Microsoft 365 with. Login with or choose the account from the list that you want to use with CLI for Microsoft 365.

You will now be prompted to consent that the custom application, `Custom PnP CLI for M365`, can use the two permissions that we configure earlier, `Read items in all site collections` and `Sign you in and read your profile` on your behalf. Select `Accept` to consent and complete the sign-in process.

Returning back to your command line, you can now verify that the sign in has been successful by executing the `m365 status` command.

Finally, to test that we can indeed read SharePoint Online site collections, let's invoke the following command

```
m365 spo site get --url https://contoso.sharepoint.com -o json
```

The JSON representation of the SharePoint Online site will be returned to the console.

Congratulations! You have just configured the CLI for Microsoft 365 to use your own custom application with custom permissions from your own Microsoft Entra ID.

### Persisting environment variables

As mentioned earlier, the way in which we set the environment variables meant that they are only set for the lifetime of the session, if the terminal session is closed, you will need to repeat those steps, which may be undesirable.

How you permanently set the environment variable is dependant on the operating system and shell you are using.

If you are on Windows, you can set the environment variables using the `Edit the system environment variables` approach in the Windows UI.

Search for `Edit the system environment variables` in Start Menu and launch it. Select `Environment Variables`, under the `User variables for <user-name>` section, select `New...` to add a new variable. In the dialog, in the variable name field enter `CLIMICROSOFT365_ENTRAAPPID` and set the value using the Client ID (quotes should be omitted). Select `OK` to save the value and repeat the process for the `CLIMICROSOFT365_TENANT` variable. Select `OK` until all windows are closed to persist the changes.

Open a new PowerShell session and execute `$env:CLIMICROSOFT365_ENTRAAPPID` and `$env:CLIMICROSOFT365_TENANT` to verify that the environment variables have been created correctly.

If you are on Linux or MacOS, depending on your terminal, add the  `export` lines to `.bashrc` or `.zshrc` file in your home directory.

If you are using PowerShell, it is worth noting that environment variables set in `bash` or `zsh` will persist to the `pwsh` session and the same applies to Windows.

---

## using-proxy-url

### -e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

### title: Use proxy url
sidebar_position: 18

## Configure CLI for Microsoft 365 to use a proxy

If you are behind a corporate proxy, you'll be able to use the CLI for Microsoft 365 when the environment variable `HTTP_PROXY` or `HTTPS_PROXY` is set.

### Understanding Proxy URL

When using a proxy, it's important to understand the different parts of a proxy URL. A proxy URL typically consists of the following elements:

---
