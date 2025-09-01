<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - User Guide - automation

*This is an automatically generated condensed reference of the automation section of the Microsoft 365 CLI User Guide, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [azure-function-powershell](#azure-function-powershell)

---

## azure-function-powershell

-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->

## Using CLI in an Azure Function with PowerShell

This guide will walk you through setting up an Azure Function that uses PowerShell to run scripts leveraging CLI for Microsoft 365. We'll start from scratch, covering all necessary Azure resources, permissions, and configurations.

### Prerequisites

In order to follow this guide smoothly, we assume that certain things are already present in your environment.
The tools listed below are used in this guide. While they are not mandatory to use, they are recommended when you are following this guide.

Apart from this IDE, you will need the following extensions for Visual Studio Code:

### Setting up Azure resources

### Setting up local project

ode_modules\.bin" 
    if ($Env:PATH.Contains($functionPath) -eq $false) {
      [System.Environment]::SetEnvironmentVariable('PATH', $Env:PATH + ";$functionPath")
    }

```
# Ensure CLI for Microsoft 365 is configured properly for executing in an Azure Function.
m365 setup --scripting --skipApp
# Use Azure managed identity to authenticate
m365 login --authType identity --ensure
# The next line is not mandatory, but it's a good practice to set the URL of your tenant.
# This way CLI for Microsoft 365 doesn't need extra permissions to discover your SharePoint root URL.
# Replace with your own tenant URL
m365 spo set --url "https://contoso.sharepoint.com"
```
```

### Creating a new function

Open the `Azure` tab in Visual Studio Code and click the `Create Function` button to create a new Function.

![Create new function](../../images/azure-function-powershell-guide/create-new-function.png)

#### HTTP trigger

#### Timer trigger

### Granting permissions

In order to run the Azure Function, you need to grant the necessary permissions to the Azure Function.
In this guide, we are using the Azure managed identity to authenticate with CLI for Microsoft 365.
This way, you don't have to store any credentials in your Azure Function.

:::note

There are many ways to authenticate with CLI for Microsoft 365. In this guide, we are using the Azure managed identity.
If you want to use a different authentication method, please refer to the [log in to Microsoft 365 documentation](../connecting-microsoft-365) or the [login command documentation](../../cmd/login.mdx).

:::

### Deploying the project

This section will guide you through deploying your Azure Function to Azure.

### Testing

To verify that the deployment was successful, when you click the `Overview` tab of your Azure Function, you should see your functions:

![Azure Function overview](../../images/azure-function-powershell-guide/function-overview.png)

#### HTTP trigger

Open the `GetSitesFromHub` function and click on the `Get Function URL` button.

![Get function URL](../../images/azure-function-powershell-guide/function-url.png)

Copy the URL and paste it into your browser or an API request tool.
Add the query parameter `?Url=` to the URL and append a hub site URL of your tenant.
You should see a list of sites that are linked to the hub site.

![HTTP result](../../images/azure-function-powershell-guide/http-endpoint-result.png)

#### Timer trigger

Open the `GroupStats` function and click the `Test/Run` button.

![Test timer trigger](../../images/azure-function-powershell-guide/test-timer-trigger.png)

This will run the timer trigger function and send an email with the group stats to the email address you specified in the code.

![Email result](../../images/azure-function-powershell-guide/timer-endpoint-result.png)

---
