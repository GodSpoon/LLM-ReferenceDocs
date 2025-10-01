<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - CLI Commands Reference

*This is an automatically generated condensed reference of all CLI commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-10-01*

---

## Table of Contents

- [app-add](#app-add)
- [app-reconsent](#app-reconsent)
- [cli-consent](#cli-consent)
- [cli-doctor](#cli-doctor)
- [cli-issue](#cli-issue)
- [completion-clink-update](#completion-clink-update)
- [completion-pwsh-setup](#completion-pwsh-setup)
- [completion-pwsh-update](#completion-pwsh-update)
- [completion-sh-setup](#completion-sh-setup)
- [completion-sh-update](#completion-sh-update)
- [config-get](#config-get)
- [config-list](#config-list)
- [config-reset](#config-reset)
- [config-set](#config-set)

---

## app-add

### Syntax
```
m365 cli app add [options]
```

### Example
```
m365 cli app add

m365 cli app add --name "Contoso CLI app" --scopes all

m365 cli app add --scopes "https://graph.microsoft.com/User.Read,https://graph.microsoft.com/Group.Read.All"

```

---

## app-reconsent

### Syntax
```
m365 cli app reconsent [options]
```

### Example
```
m365 cli app reconsent

```

### Remarks
This command will add all missing scopes used in CLI for Microsoft 365 to your current app registration. It will only add missing scopes and won't remove any scopes that are already present in the app registration.



---

## cli-consent

### Syntax
```
m365 cli consent [options]
```

### Example
```
m365 cli consent --service VivaEngage

```

### Remarks
Using the `cli consent` command you can consent additional permissions for the Microsoft Entra application used by the CLI for Microsoft 365. This is for example necessary to use Viva Engage commands, which require the Viva Engage API permission that isn't granted to the CLI by default.

After executing the command, the CLI for Microsoft 365 will present you with a URL that you need to open in the web browser in order to consent the permissions for the selected Microsoft 365 service.

To simplify things, rather than wondering which permissions you should grant for which CLI commands, this command allows you to easily grant all the necessary permissions for using commands for the specified Microsoft 365 service, like Viva Engage.



---

## cli-doctor

### Syntax
```
m365 cli doctor [options]
```

### Example
```
m365 cli doctor

```

### Remarks
This command gets all the necessary diagnostic information needed to triage and debug CLI issues without exposing any security-sensitive details



---

## cli-issue

### Syntax
```
m365 cli issue [options]
```

### Example
```
m365 cli issue --type bug

m365 cli issue --type command

```

### Remarks
If you are running the command in a docker container, or the Azure Cloud Shell the CLI won't be able to open the URL directly and you'll need to copy the URL to a new tab or browser instance yourself.



---

## completion-clink-update

### Syntax
```
m365 cli completion clink update [options]
```

### Remarks
This commands updates the list of commands and their options used by command completion in Clink (cmder). You should run this command each time after upgrading the CLI for Microsoft 365.

:::info

Before running this command, change the working directory to where your shell stores completion plugins. For cmder, it's `%CMDER_ROOT%endor



---

## completion-pwsh-setup

### Syntax
```
m365 cli completion pwsh setup [options]
```

### Example
```
m365 cli completion pwsh setup --profile $profile

```

### Remarks
This commands sets up command completion for the CLI for Microsoft 365 in PowerShell by registering a custom PowerShell argument completer in the specified profile. Because CLI for Microsoft 365 is not a native PowerShell module, it requires a custom completer to provide completion.

If the specified profile path doesn't exist, the CLI will try to create it.



---

## completion-pwsh-update

### Syntax
```
m365 cli completion pwsh update [options]
```

### Example
```
m365 cli completion pwsh update

```

### Remarks
This commands updates the list of commands and their options used by command completion in PowerShell. You should run this command each time after upgrading the CLI for Microsoft 365.



---

## completion-sh-setup

### Syntax
```
m365 cli completion sh setup [options]
```

### Example
```
m365 cli completion sh setup

```

---

## completion-sh-update

### Syntax
```
m365 cli completion sh update [options]
```

### Example
```
m365 cli completion sh update

```

### Remarks
This commands updates the list of commands and their options used by command completion in Zsh, Bash and Fish. You should run this command each time after upgrading the CLI for Microsoft 365.



---

## config-get

### Syntax
```
m365 cli config get [options]
```

### Example
```
m365 cli config get --key output

```

### Remarks
If the specified setting has not been configured, CLI will return no output.



---

## config-list

### Syntax
```
m365 cli config list [options]
```

### Example
```
m365 cli config list

```

---

## config-reset

### Syntax
```
m365 cli config reset [options]
```

### Example
```
m365 cli config reset --key showHelpOnFailure

m365 cli config reset

```

---

## config-set

### Syntax
```
m365 cli config set [options]
```

### Example
```
m365 cli config set --key showHelpOnFailure --value true

m365 cli config set --key output --value json

```

---
