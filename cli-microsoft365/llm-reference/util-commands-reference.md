<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - UTIL Commands Reference

*This is an automatically generated condensed reference of all UTIL commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [accesstoken-get](#accesstoken-get)

---

## accesstoken-get

### Syntax
```
m365 util accesstoken get [options]
```

### Example
```
m365 util accesstoken get --resource https://graph.microsoft.com

m365 util accesstoken get --resource sharepoint

m365 util accesstoken get --resource graph

m365 util accesstoken get --resource https://contoso.sharepoint.com --new

m365 util accesstoken get --resource https://contoso.sharepoint.com --decoded

```

### Remarks
:::tip

Instead of specifying the full URL of the resource, you can use one of the following shorthand identifiers: `sharepoint`, `graph`.

:::

The `util accesstoken get` command returns an access token for the specified resource. If an access token has been previously retrieved and is still valid, the command will return the cached token. If you want to ensure that the returned access token is valid for as long as possible, you can force the command to retrieve a new access token by using the `--new` option.



---
