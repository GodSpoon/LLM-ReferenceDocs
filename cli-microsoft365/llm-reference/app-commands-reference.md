<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - APP Commands Reference

*This is an automatically generated condensed reference of all APP commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-10-01*

---

## Table of Contents

- [app-get](#app-get)
- [app-open](#app-open)
- [permission-add](#permission-add)
- [permission-list](#permission-list)

---

## app-get

### Syntax
```
m365 app get [options]
```

### Example
```
m365 app get

m365 app get --appId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
Use this command to quickly look up information for the Microsoft Entra application registration registered in the .m365rc.json file in your current project (folder).

If you have multiple apps registered in your .m365rc.json file, you can specify the app for which you'd like to retrieve permissions using the `--appId` option. If you don't specify the app using the `--appId` option, you'll be prompted to select one of the applications from your .m365rc.json file.



---

## app-open

### Syntax
```
m365 app open [options]
```

### Example
```
m365 app open

m365 app open --preview

m365 app open --appId EXAMPLE-GUID-PLACEHOLDER 

```

### Remarks
If config setting `autoOpenLinksInBrowser` is configured to true, the command will automatically open the link to the Azure Portal in the browser.

Gets the app from the `.m365rc.json` file in the current directory. If the `--appId` option is not used and multiple apps are available, it will prompt the user to choose one.



---

## permission-add

### Syntax
```
m365 app permission add [options]
```

### Example
```
m365 app permission add --applicationPermissions 'https://graph.microsoft.com/User.ReadWrite.All https://graph.microsoft.com/User.Read.All' --grantAdminConsent```

### Remarks
If you have multiple apps registered in your .m365rc.json file, you can specify the app for which you'd like to retrieve permissions using the `--appId` option. If you don't specify the app using the `--appId` option, you'll be prompted to select one of the applications from your .m365rc.json file.



---

## permission-list

### Syntax
```
m365 app permission list [options]
```

### Example
```
m365 app permission list

m365 app permission list --appId EXAMPLE-GUID-PLACEHOLDER

```

### Remarks
Use this command to quickly look up API permissions for the Microsoft Entra application registration registered in the _.m365rc.json_ file in your current project (folder).

If you have multiple apps registered in your .m365rc.json file, you can specify the app for which you'd like to retrieve permissions using the `--appId` option. If you don't specify the app using the `--appId` option, you'll be prompted to select one of the applications from your _.m365rc.json_ file.



---
