<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - CONNECTION Commands Reference

*This is an automatically generated condensed reference of all CONNECTION commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-12-01*

---

## Table of Contents

- [connection-list](#connection-list)
- [connection-remove](#connection-remove)
- [connection-set](#connection-set)
- [connection-use](#connection-use)

---

## connection-list

### Syntax
```
m365 connection list [options]
```

### Example
```
m365 connection list

```

### Remarks
If you are logged in to Microsoft 365 with multiple identities, this command will show you a list of users and/or applications used to sign in.  



---

## connection-remove

### Syntax
```
m365 connection remove [options]
```

### Example
```
m365 connection remove --name 'EXAMPLE-GUID-PLACEHOLDER'

m365 connection remove --name 'EXAMPLE-GUID-PLACEHOLDER' --force

```

### Remarks
The value for `--name` can be found by running [m365 connection list](connection-list.mdx). 



---

## connection-set

### Syntax
```
m365 connection set [options]
```

### Example
```
m365 connection set --name 'EXAMPLE-GUID-PLACEHOLDER' --newName 'myworkaccount'

```

### Remarks
The value for `--name` can be found by running [m365 connection list](connection-list.mdx). You can update the name of a connection to any value to make switching connections easier. 



---

## connection-use

### Syntax
```
m365 connection use [options]
```

### Example
```
m365 connection use --name 'EXAMPLE-GUID-PLACEHOLDER'

m365 connection use --name 'myworkaccount'

```

### Remarks
:::tip

If you haven't disabled the "prompt" setting, running this command without options will show a list of available connections. You can then select the connection to activate it.

:::

You can update the name of a connection by running [m365 connection set](connection-set.mdx).



---
