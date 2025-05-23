-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - DevOps
  - pipelines
  - CI/CD
  - workflows
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Add CI/CD Pipeline for your SharePoint Framework project

Author: [Adam Wójcik](https://github.com/Adam-it)

Having a flow that builds and ships your project on push to your repository's main branch is a great practice that allows you to share your latest changes with your team, testers or customers. 
This may save you a lot of time and effort, as you don't need to manually build and deploy your project every time you make a change.
This script will help you to create a CI/CD pipeline for your SharePoint Framework project. 
Depending on what parameters you pass, the script will create either a new GitHub Actions workflow or an Azure DevOps pipeline.
If you choose to create an application login method (which is default and recommended), the script will also create an app registration in your tenant and generate a self-signed certificate that will be used to authenticate the app.

This script will NOT setup the pipeline for you. It will only generate the YAML file that you will need to commit to your repository and create a new pipeline or workflow based on it.

## Script parameters

- `PathToSpfxProject` - required - absolute path to your SPFx project
- `DevOpsEnvironment` - optional - possible options: `github` (default), `azuredevops`. Defines for which DevOps environment the YAML file will be generated.
- `LoginMethod` - optional - possible options: `application` (default), `user`. The CI/CD pipeline is not in the context of your Microsoft 365 tenant and in order to be able to deploy you solution it needs to login to your tenant. You may either login as a `user` which is ok for dev solution and will not work with accounts with MFA, or as an `application` which is recommended for production solutions.
- `ShouldCreateAppReg` - optional - possible options: `true` (default), `false`. Defines if the script should create an app registration in your tenant and generate a self-signed certificate for your app.
- `Name` - optional - default: `Deploy Solution`. Defines the name of the pipeline or workflow.
- `BranchName` - optional - default: `main`. Defines the name of the branch that will trigger the pipeline.
- `ManuallyTrigger` - optional - possible options: `true`, `false` (default). Defines if the pipeline should be triggered manually. This applies only to GitHub environment.
- `Scope` - optional - possible options: `tenant` (default), `sitecollection`. Defines the scope of the deployment. If you choose `sitecollection` you will need to provide the `siteUrl` parameter.
- `SiteUrl` - optional - required if `Scope` is set to `sitecollection`. Defines the site collection app catalog URL where the solution will be deployed.
- `SkipFeatureDeployment` - optional - possible options: `true`, `false` (default). Defines if the app should be added to all subsites or tenant.

## Examples

Creates a GitHub Actions workflow using application login method and creates an app registration in your tenant along with self-signed certificate. 

``` powershell
.\script.ps1 -PathToSpfxProject "C:\myCoolProjects\spfxDemo"
```

Creates a GitHub Actions workflow using application login method without creating an app registration. Sets custom name for the pipeline and branch name that will trigger the pipeline.

``` powershell
.\script.ps1 -PathToSpfxProject "C:\myCoolProjects\spfxDemo" -ShouldCreateAppReg $false -Name "custom name" -BranchName "dev"
```

Creates a GitHub Actions workflow using user login method. Allows the flow to be triggered manually. The solution will be deployed to the site collection app catalog.

``` powershell
.\script.ps1 -PathToSpfxProject "C:\myCoolProjects\spfxDemo" -LoginMethod "user" -ManuallyTrigger $true -Scope "sitecollection" -SiteUrl "https://tenanttocheck.sharepoint.com/sites/CLIDemo1/appcatalog"
```

Creates an Azure DevOps pipeline using application login method and creates an app registration in your tenant along with a self-signed certificate. 

``` powershell
.\script.ps1 -PathToSpfxProject "C:\myCoolProjects\spfxDemo" -DevOpsEnvironment "azuredevops"
```

Creates an Azure DevOps pipeline using application login method without creating an app registration. Sets custom name for the pipeline and branch name that will trigger the pipeline.

``` powershell
.\script.ps1 -PathToSpfxProject "C:\myCoolProjects\spfxDemo" -DevOpsEnvironment "azuredevops" -ShouldCreateAppReg $false -Name "custom name" -BranchName "dev"
```

Creates an Azure DevOps pipeline using user login method. The solution will be deployed to the site collection app catalog.

``` powershell
.\script.ps1 -PathToSpfxProject "C:\myCoolProjects\spfxDemo" -DevOpsEnvironment "azuredevops" -LoginMethod "user" -Scope "sitecollection" -SiteUrl "https://tenanttocheck.sharepoint.com/sites/CLIDemo1/appcatalog"
```

## Additional guidance

The script does not create the GitHub Actions workflow or Azure DevOps pipeline for you. It only generates the YAML file that you will need to commit to your repository and create a new pipeline or workflow based on it. Please check the below steps with additional guidance on how to set it up for the first time.

### GitHub Actions

After you commit the generated YAML file, GitHub will automatically pick it up and it will be visible in the 'Actions' tab of your repository.
Depending on what authentication method you chose, you will need to add the following secrets to your repository:

For the application login method:

- `APP_ID` - client id of the registered Entra application
- `CERTIFICATE_ENCODED` - application's encoded certificate
- `CERTIFICATE_PASSWORD` - certificate password. This applies only if the certificate is encoded which is the recommended approach
- `TENANT` - Tenant ID

For the user login method you will need to create the following secrets:

- `ADMIN_USERNAME` - username
- `ADMIN_PASSWORD` - password

In order to add a secret to your repository, navigate to 'Settings' -> 'Security' -> 'Secrets and variables'.

### Azure DevOps

Creating a new pipeline in Azure DevOps is a one-time operation and then every time you update the YAML definition Azure DevOps will automatically pick up the changes. 
In order to create a new pipeline go pipelines page in your Azure DevOps project.
Next in the top right corner of the page hit the new pipeline button. 
After that follow the for by selecting the location of your repo, next the branch on which the YAML file is present and then select the option to create a new pipeline based on the existing Azure Pipelines YAML file.
After that just confirm the creation process and you're ready to go!

As best practice, you should add a new library group to use in your pipeline with the following variables:

For the user login method you will need to fill in the following variables:

- `UserName` - user email
- `Password` - password

For the application login method you will need to fill in the following variables:

- `CertificateBase64Encoded` - base 64 encoded certificate. Use either CertificateBase64Encoded or CertificateSecureFileId but not both
- `CertificateSecureFileId` - id of a certificate file in the secure files section of the DevOps library. .pfx file. Use either CertificateBase64Encoded or CertificateSecureFileId but not both
- `CertificatePassword` - certificate password. This applies only if the certificate is encoded which is the recommended approach
- `EntraAppId` - client id of the registered Entra application

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param (
    [Parameter(Mandatory = $true, HelpMessage = "SPFx project path")]
    [string]$PathToSpfxProject,

    [Parameter(Mandatory = $false, HelpMessage = "DevOps environment [default: 'github']")]
    [ValidateSet("github", "azuredevops")]
    [string]$DevOpsEnvironment = "github",

    [Parameter(Mandatory = $false, HelpMessage = "Login method [default: 'application']")]
    [ValidateSet("application", "user")]
    [string]$LoginMethod = "application",

    [Parameter(Mandatory = $false, HelpMessage = "Should create an app registration [default: 'true']")]
    [bool]$ShouldCreateAppReg = $true,

    [Parameter(Mandatory = $false, HelpMessage = "Pipeline name [default: 'Deploy Solution']")]
    [string]$Name = "Deploy Solution",

    [Parameter(Mandatory = $false, HelpMessage = "Name of branch that will trigger the pipeline [default: 'main']")]
    [string]$BranchName = "main",

    [Parameter(Mandatory = $false, HelpMessage = "Should the allow to trigger the pipeline manually (applies only to 'GitHub' environment) [default: 'false']")]
    [bool]$ManuallyTrigger = $false,

    [Parameter(Mandatory = $false, HelpMessage = "Scope [default: 'tenant']")]
    [ValidateSet("tenant", "sitecollection")]
    [string]$Scope = "tenant",

    [Parameter(Mandatory = $false, HelpMessage = "siteUrl (applies only to 'sitecollection' scope)")]
    [string]$SiteUrl,

    [Parameter(Mandatory = $false, HelpMessage = "Should add the app to all subsites or tenant")]
    [bool]$SkipFeatureDeployment = $false
  )

  # validate if for sitecollection scope siteUrl is provided
  if ($Scope -eq "sitecollection" -and -not $SiteUrl) {
    Write-Error "For 'sitecollection' scope, the 'siteUrl' parameter is required"
    Exit
  }

  # set and validate location of the SPFx project
  $currentLocation = Get-Location
  Set-Location $PathToSpfxProject
  if (-not (Test-Path -Path ".yo-rc.json")) {
    Write-Error "The script needs to be executed in the context of the SPFx project. Please provide the correct path to the SPFx project"
    Exit
  }

  # ensure that temp directory exists
  if (-not (Test-Path -Path "temp")) {
    New-Item -ItemType Directory -Path "temp"
  }

  # generate self-signed certificate for application login method
  if ($LoginMethod -eq "user") {
    Write-Warning "User login method will not work for accounts with multi-factor authentication enabled"
  }
  elseif ($ShouldCreateAppReg) {
    Write-Host "Generating self-signed certificate..."
    $passwordString = Read-Host -Prompt "Please provide password for the certificate" -AsSecureString
    $password = ConvertTo-SecureString -String $passwordString -Force -AsPlainText
    $cert = New-SelfSignedCertificate -NotBefore $(Get-Date).AddDays(-1) -NotAfter $(Get-Date).AddYears(1) -FriendlyName "CI-CD-Certificate" -CertStoreLocation cert:\CurrentUser\My -Subject "CN=CICDCertificate" -KeyAlgorithm RSA -KeyLength 2048 -KeyExportPolicy Exportable
    $cert | Export-Certificate -Type cer -FilePath "temp/CI-CD-Certificate.cer" -Force
    $cert | Export-PfxCertificate -FilePath "temp/CI-CD-Certificate.pfx" -Password $password
    $cert | Remove-Item
    $pfxBytes = Get-Content "temp/CI-CD-Certificate.pfx" -AsByteStream -Raw
    [System.Convert]::ToBase64String($pfxBytes) | Out-File "temp/CertificateBase64String.txt"

    # create an Entra app registration
    Write-Host "Creating an app registration..."
    $app = m365 entra app add --name "My CI/CD App Reg" --apisApplication "https://microsoft.sharepoint-df.com/Sites.FullControl.All" --certificateFile ./temp/CI-CD-Certificate.cer --certificateDisplayName "CICD Certificate" --grantAdminConsent --output "json"
  }

  # create a new yaml flow file
  if ($SkipFeatureDeployment) {
    $SkipFeatureDeploymentStr = "--skipFeatureDeployment"
  }
  else {
    $SkipFeatureDeploymentStr = ""
  }

  if ($DevOpsEnvironment -eq "github") {
    Write-Host "Creating GitHub Actions pipeline..."
    
    if ($ManuallyTrigger) {
      $ManuallyTriggerStr = "--manuallyTrigger"
    }
    else {
      $ManuallyTriggerStr = ""
    }

    if ($Scope -eq "tenant") {
      m365 spfx project github workflow add --loginMethod $LoginMethod --name $Name --branchName $BranchName $ManuallyTriggerStr $SkipFeatureDeploymentStr
    }
    else {
      m365 spfx project github workflow add --loginMethod $LoginMethod --name $Name --branchName $BranchName --scope "sitecollection" --siteUrl $SiteUrl $ManuallyTriggerStr $SkipFeatureDeploymentStr
    }

    # show github guidance
    Write-Host "Your new '.github/workflows/deploy-spfx-solution.yml' is ready. Now you will need to commit it to your repository so that GitHub Actions may pick it up." 

    Write-Host "Please ensure that the following secrets are added to your GitHub repository:"
    Write-Host "You can add them in the 'Settings' -> 'Security' -> 'Secrets and variables'" 

    if ($LoginMethod -eq "user") {
      Write-Host "ADMIN_USERNAME: username"
      Write-Host "ADMIN_PASSWORD: password"
    }
    else { 
      if ($ShouldCreateAppReg) {
        $app = $app | ConvertFrom-Json
        Write-Host "APP_ID: $($app.appId)"
        Write-Host "TENANT_ID: $($app.tenantId)"
        Write-Host "CERTIFICATE_ENCODED: you may find that in the 'temp/CertificateBase64String.txt' file"
      }
      else {
        Write-Host "APP_ID: client id of the registered Microsoft Entra application"
        Write-Host "TENANT_ID: tenant id"
        Write-Host "CERTIFICATE_ENCODED: application's encoded certificate"
      }
      Write-Host "CERTIFICATE_PASSWORD: certificate password you provided when generating the certificate"
    }
  }
  else {
    Write-Host "Creating Azure DevOps pipeline..."
    if ($Scope -eq "tenant") {
      m365 spfx project azuredevops pipeline add --loginMethod $LoginMethod --name $Name --branchName $BranchName $SkipFeatureDeploymentStr
    }
    else {
      m365 spfx project azuredevops pipeline add --loginMethod $LoginMethod --name $Name --branchName $BranchName --scope "sitecollection" --siteUrl $SiteUrl $SkipFeatureDeploymentStr
    }

    # show azure devops guidance
    Write-Host "Your new '.azuredevops/pipelines/deploy-spfx-solution.yml' is ready. Now you will need to commit it to your repository and create a new pipeline based on it." 

    Write-Host "In order to create a new pipeline, you will need to navigate to your Azure DevOps pipelines -> New pipeline -> pick the repository -> Existing Azure Pipelines YAML file -> select the 'deploy-spfx-solution.yml' file -> Run."
    Write-Host "As best practice you should add a new library group with the following variables"
    Write-Host "Got to Pipelines -> Library -> Add variable group -> Add the following variables:" 
    Write-Host "SharePointBaseUrl: SharePoint host url"

    if ($LoginMethod -eq "user") {
      Write-Host "UserName: username"
      Write-Host "Password: password"
    }
    else { 
      if ($ShouldCreateAppReg) {
        $app = $app | ConvertFrom-Json
        Write-Host "EntraAppId: $($app.appId)"
        Write-Host "TenantId: $($app.tenantId)"
        Write-Host "CertificateBase64Encoded: you may find that in the 'temp/CertificateBase64String.txt' file"
      }
      else {
        Write-Host "EntraAppId: client id of the registered Microsoft Entra application"
        Write-Host "TenantId: tenant id"
        Write-Host "CertificateBase64Encoded: application's encoded certificate"
      }
      Write-Host "CertificatePassword: certificate password you provided when generating the certificate"
    }

    if ($Scope -eq "sitecollection") {
      Write-Host "SiteAppCatalogUrl: site collection app catalog url"
    }
  }

  Set-Location $currentLocation
  ```

  </TabItem>
</Tabs>
