<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - EXTERNAL Commands Reference

*This is an automatically generated condensed reference of all EXTERNAL commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-05-15*

---

## Table of Contents

- [connection-add](#connection-add)
- [connection-doctor](#connection-doctor)
- [connection-get](#connection-get)
- [connection-list](#connection-list)
- [connection-remove](#connection-remove)
- [connection-schema-add](#connection-schema-add)
- [connection-urltoitemresolver-add](#connection-urltoitemresolver-add)
- [item-add](#item-add)

---

## connection-add

### Syntax
```
m365 external connection add [options]
```

### Example
```
m365 external connection add --id MyApp --name "Test" --description "Test"

m365 external connection add --id MyApp --name "Test" --description "Test" --authorizedAppIds  "EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER,EXAMPLE-GUID-PLACEHOLDER"

```

### Remarks
The `id` must be at least 3 and no more than 32 characters long. It can contain only alphanumeric characters, can't begin with _Microsoft_ and can be any of the following values: *None, Directory, Exchange, ExchangeArchive, LinkedIn, Mailbox, OneDriveBusiness, SharePoint, Teams, Yammer, Connectors, TaskFabric, PowerBI, Assistant, TopicEngine, MSFT_All_Connectors*.



---

## connection-doctor

### Syntax
```
m365 external connection doctor [options]
```

### Example
```
m365 external connection doctor --id contosoproducts --ux copilot

```

### Remarks
The `external connection doctor` command runs several automated checks to verify if an external connection is correctly configured for use with a user experience in Microsoft 365.

Required checks must pass for the external connection to be compatible with the specified user experience. Recommended checks are optional, but recommended for optimal user experience.

Some checks must be done manually, because there are no APIs available to verify the configuration automatically.

When you check the compatibility with all UXs, and there are multiple checks with the same ID, the command will use the first matching check, following the order listed above.



---

## connection-get

### Syntax
```
m365 external connection get [options]
```

### Example
```
m365 external connection get --id "MyApp"

m365 external connection get --name "Test"

```

---

## connection-list

### Syntax
```
m365 external connection list [options]
```

### Example
```
m365 external connection list

```

---

## connection-remove

### Syntax
```
m365 external connection remove [options]
```

### Example
```
m365 external connection remove --id "MyApp"

m365 external connection remove --name "Test" --force

```

### Remarks
If the command finds multiple external connections with the specified name, it will prompt you to disambiguate which external connection it should remove, listing the discovered IDs.



---

## connection-schema-add

### Syntax
```
m365 external connection schema add [options]
```

### Example
```
m365 external connection schema add --externalConnectionId 'CliConnectionId' --schema '{"baseType":"microsoft.graph.externalItem","properties":[{"name":"ticketTitle","type":"String","isSearchable":"true","isRetrievable":"true","labels":["title"]},{"name":"priority","type":"String","isQueryable":"true","isRetrievable":"true","isSearchable":"false"},{"name":"assignee","type":"String","isRetrievable":"true"}]}'```

---

## connection-urltoitemresolver-add

### Syntax
```
m365 external connection urltoitemresolver add [options]
```

### Example
```
m365 external connection urltoitemresolver add --externalConnectionId "samplesolutiongallery" --baseUrls "https://adoption.microsoft.com" --urlPattern "/sample-solution-gallery/sample/(?<sampleId>[^/]+)" --itemId "{sampleId}" --priority 1

```

---

## item-add

### Syntax
```
m365 external item add [options]
```

### Example
```
m365 external item add --id "pnp-ensure-siteassets-library" --externalConnectionId "samplesolutiongallery" --content "Ensure that the Site Assets library is created." --title "Ensure the Site Assets Library is created" --description "Ensure that the Site Assets library is created." --authors "Phil Harding" --acls "grant,everyone,everyone"```

### Remarks
When creating an external item, the options you specify will map to the external item properties, eg. `--author "Steve"` will set the `author` property of the external item to `Steve`.

If in your schema you have a multi-value property, to specify its value you need two things:

When creating items you can specify one or more permissions that define who can access the external item. The format of the permissions is `accessType1,type1,value1;accessType2,type2,value2`, eg. `grant,everyone,everyone`.

You can use the following access types:

You can use the following types:

For more information about using these options, see the Microsoft Graph API documentation and documentation about Microsoft Graph connectors.



---
