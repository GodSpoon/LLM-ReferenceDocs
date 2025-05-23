-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - security
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Grant API permissions to SharePoint Microsoft Entra ID Application

Author: [Michaël Maillot](https://michaelmaillot.github.io)

When developing your SPFx components, you usually first run them locally before deploying them (really ?).

And then comes the time to work with API such as Microsoft Graph.

If you never use those permissions before in your SPFx projects (and the tenant with which you're working), you realize that you have to:

Add required API permissions in your `package-solution.json` file

* Bundle / Ship your project
* Publish it
* Go to the SharePoint Admin Center Web API Permissions page
* Approve those permissions

All of this, just to play with the API as you didn't plan to release your package in a production environment.

So what if you could bypass all these steps for both Graph and owned API?

:::info

This trick is just for development purposes. In Production environment, you should update your `package-solution.json` file to add required permissions and allow them (or ask for validation) in the _API access_ page.

:::

:::warning

These permissions will be granted on the whole tenant and could be used by any script running in your tenant. More info [here](https://learn.microsoft.com/sharepoint/dev/spfx/use-aadhttpclient#considerations).

:::

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  $m365Status = m365 status --output text
  if ($m365Status -eq "Logged Out") {
    m365 login
  }

  # Granting Microsoft Graph permissions
  $resourceName = "Microsoft Graph"
  $msGraphPermissions = @(
    "Mail.Read",
    "People.Read",
    "User.ReadWrite"
  )

  $progress = 0
  $total = $msGraphPermissions.Count

  ForEach ($permission in $msGraphPermissions) {
    $progress++
    Write-Host $progress / $total":" $permission
      
    # If permission already granted, you'll face an OAuth permission issue
    # So you can test the presence of the scope for the requested resource to prevent the error
    $scopeToAdd = m365 spo serviceprincipal grant list --query "[?Resource == '${resourceName}' && Scope == '${permission}']"
    if ($scopeToAdd -eq "") {
      m365 spo serviceprincipal grant add --resource "$resourceName" --scope "$permission"
      Write-Host "Permission '${permission}' for Resource '${resourceName}' granted" -ForegroundColor Green
    }
    else {
      Write-Host "Permission '${permission}' for Resource '${resourceName}' already granted" -ForegroundColor Yellow 
    }
  }

  # Granting custom permissions
  $resourceName = "contoso-api"
  $customPermissions = @(
    "user_impersonation",
    "random_permission"
  )

  $progress = 0
  $total = $customPermissions.Count

  ForEach ($permission in $customPermissions) {
    $progress++
    Write-Host $progress / $total":" $permission

    # If permission already granted, you'll face an OAuth permission issue
    # So you can test the presence of the scope for the requested resource to prevent the error
    $scopeToAdd = m365 spo serviceprincipal grant list --query "[?Resource == '${resourceName}' && Scope == '${permission}']"
    if ($scopeToAdd -eq "") {
      m365 spo serviceprincipal grant add --resource "$resourceName" --scope "$permission"
      Write-Host "Permission '${permission}' for Resource '${resourceName}' granted" -ForegroundColor Green
    }
    else {
      Write-Host "Permission '${permission}' for Resource '${resourceName}' already granted" -ForegroundColor Yellow 
    }
  }
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/bin/bash

  # color formatting for echo
  NOCOLOR='[0m'
  YELLOW='[1;33m'
  GREEN='[0;32m'

  m365 login # Don't execute that command if you're already logged in

  # Granting Microsoft Graph permissions
  resourceName="Microsoft Graph"
  msGraphPermissions=("Mail.Read" "People.Read" "User.ReadWrite")

  progress=0
  total=${#msGraphPermissions[@]}

  for permission in "${msGraphPermissions[@]}"; do
    ((progress++))
    printf '%s / %s:%s
' "$progress" "$total" "$permission"

    # If permission already granted, you'll face an OAuth permission issue
    # So you can test the presence of the scope for the requested resource to prevent the error
    scopeToAdd=$( m365 spo serviceprincipal grant list --query "[?Resource == '$resourceName' && Scope == '${permission}']" )
    if [ "$( [ -z "$scopeToAdd" ] && echo "Empty" )" == "Empty" ]; then
      m365 spo serviceprincipal grant add --resource "$resourceName" --scope "$permission"
      echo -e "${GREEN}Permission '${permission}' for Resource '${resourceName}' granted${NOCOLOR}"
    else
      echo -e "${YELLOW}Permission '${permission}' for Resource '${resourceName}' already granted${NOCOLOR}"
    fi
  done

  # Granting custom permissions
  resourceName="contoso-api"
  customPermissions=("user_impersonation" "random_permission")

  progress=0
  total=${#customPermissions[@]}

  for permission in "${customPermissions[@]}"; do
    ((progress++))
    printf '%s / %s:%s
' "$progress" "$total" "$permission"
    
    # If permission already granted, you'll face an OAuth permission issue
    # So you can test the presence of the scope for the requested resource to prevent the error
    scopeToAdd=$( m365 spo serviceprincipal grant list --query "[?Resource == '$resourceName' && Scope == '${permission}']" )
    if [ "$( [ -z "$scopeToAdd" ] && echo "Empty" )" == "Empty" ]; then
      m365 spo serviceprincipal grant add --resource "$resourceName" --scope "$permission"
      echo -e "${GREEN}Permission '${permission}' for Resource '${resourceName}' granted${NOCOLOR}"
    else
      echo -e "${YELLOW}Permission '${permission}' for Resource '${resourceName}' already granted${NOCOLOR}"
    fi
  done
  ```

  </TabItem>
</Tabs>
