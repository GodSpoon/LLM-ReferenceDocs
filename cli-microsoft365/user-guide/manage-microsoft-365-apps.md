-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
title: Manage Microsoft 365 apps with the CLI 
sidebar_position: 14
---

# Manage Microsoft 365 apps with the CLI for Microsoft 365

When developing Microsoft 365 apps, you need to register them with the Microsoft cloud. You do this by creating a Microsoft Entra application registration. An application registration contains information about your app such as its name, type (for example if it's a client app or a web app) or API permissions. Typically, you manage these settings through the Azure portal. CLI for Microsoft 365 contains a set of commands that simplify managing application registrations for your Microsoft 365 apps. What's more, using CLI for Microsoft 365 you can automate create Microsoft Entra apps to allow developers in your team share their configuration without blocking each other.

## Step 1: Create Microsoft Entra application registration

You start bringing your app to Microsoft 365 by creating an application registration in Microsoft Entra ID. Using CLI for Microsoft 365, you can do this using the `m365 entra app add` command. For example, if you're building a single-page application, you'd execute:

```sh
m365 entra app add --name 'My single-page app' --platform spa --redirectUris 'https://myspa.azurewebsites.net,http://localhost'
```

With this one command, CLI for Microsoft 365 will create a new Microsoft Entra application registration and configure its authentication mode to a single-page application with the specified two redirect URLs.

:::tip

There are many settings that you can configure for application registrations, so be sure to check the [documentation for the `m365 entra app add` command](../cmd/entra/app/app-add.mdx) for more examples.

:::

This one-liner is great to share with your dev team so that each developer can create their own application registration that they can manage as they work on the app. If your app's configuration is complex, you can also choose to export the existing manifest and create a new application registration from it! But there's more.

## Step 2: Store information about your Microsoft Entra app in your project

As you work with Microsoft 365 apps, you'll be creating quite a few application registrations in Microsoft Entra ID. Over time, it might be hard for you to keep track of which one is which and where you need to apply changes.

To help you, CLI for Microsoft 365 offers you two things. First, when creating a application registration for your Microsoft 365 app, store a reference to it. You do this, by extending the `m365 entra app add` command with the `--save` flag:

```sh
m365 entra app add --name 'My single-page app' --platform spa --redirectUris 'https://myspa.azurewebsites.net,http://localhost' --save
```

When you use the `--save` flag, CLI for Microsoft 365 will create the `.m365rc.json` file in the current working directory and write to it the ID and name of the newly created application registration. If the file exists already, CLI for Microsoft 365 will add the new information to it. That way you can track which application registration belongs to your project without having to manually locate them in the Azure Portal! And if you're building complex solutions with multiple Microsoft Entra apps, you can keep track of all of them in one place too!

After you stored the reference to your Microsoft Entra apps in your projects, you're ready to use the `app` commands from CLI for Microsoft 365.

## Step 3: Manage Microsoft Entra application registrations for Microsoft 365 apps

CLI for Microsoft 365 exposes a set of `app` commands (`m365 app *`) that let you manage your Microsoft 365 app projects. For example, using the [`m365 app permission list`](../cmd/app/permission/permission-list.mdx) command, you can easily retrieve API permissions for your Entra app.

See the list of `app` commands in the **Commands** section of this documentation for the complete reference of supported operations.
