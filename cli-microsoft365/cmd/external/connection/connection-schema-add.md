-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';

# external connection schema add

Allow the administrator to add a schema to a specific external connection

## Usage

```sh
m365 external connection schema add [options]
```

## Alias

```sh
m365 search externalconnection schema add
```

## Options

```md definition-list
`-i, --externalConnectionId  <externalConnectionId>`
: ID of the External Connection.

`-s, --schema [schema]`
: The schema object to be added.

`--wait`
: Wait for the schema to be added before completing the command.
```

<Global />

## Examples

Adds a new schema to a specific external connection.

```sh
m365 external connection schema add --externalConnectionId 'CliConnectionId' --schema '{"baseType":"microsoft.graph.externalItem","properties":[{"name":"ticketTitle","type":"String","isSearchable":"true","isRetrievable":"true","labels":["title"]},{"name":"priority","type":"String","isQueryable":"true","isRetrievable":"true","isSearchable":"false"},{"name":"assignee","type":"String","isRetrievable":"true"}]}'
```

Adds a new schema to a specific external connection and wait for its provisioning to complete.

```sh
m365 external connection schema add --externalConnectionId 'CliConnectionId' --schema '{"baseType":"microsoft.graph.externalItem","properties":[{"name":"ticketTitle","type":"String","isSearchable":"true","isRetrievable":"true","labels":["title"]},{"name":"priority","type":"String","isQueryable":"true","isRetrievable":"true","isSearchable":"false"},{"name":"assignee","type":"String","isRetrievable":"true"}]}' --wait
```

## Response

Upon executing the command, you'll receive the job status URL. This URL enables manual checking of the job's progress if automated polling fails or for interactive monitoring purposes.

```text
"https://graph.microsoft.com/v1.0/external/connections/MyApp/operations/795b6888-4093-0fe7-6270-ddbcac9ebd3a"
```
