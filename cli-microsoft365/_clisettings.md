-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
Setting name|Definition|Default value
------------|----------|-------------
`authType`|Default login method to use when running `m365 login` without the `--authType` option.|`deviceCode`
`autoOpenLinksInBrowser`|Automatically open the browser for all commands which return a url and expect the user to copy paste this to the browser. For example when logging in, using `m365 login` in device code mode.|`false`
`clientId`|ID of the default Entra ID app use by the CLI to authenticate|``
`clientSecret`|Secret of the default Entra ID app use by the CLI to authenticate|``
`clientCertificateFile`|Path to the file containing the client certificate to use for authentication|``
`clientCertificateBase64Encoded`|Base64-encoded client certificate contents|``
`clientCertificatePassword`|Password to the client certificate file|``
`copyDeviceCodeToClipboard`|Automatically copy the device code to the clipboard when running `m365 login` command in device code mode|`false`
`csvEscape`|Single character used for escaping; only apply to characters matching the quote and the escape options|`"`
`csvHeader`|Display the column names on the first line|`true`
`csvQuote`|The quote characters surrounding a field. An empty quote value will preserve the original field, whether it contains quotation marks or not.|` `
`csvQuoted`|Quote all the non-empty fields even if not required|`false`
`csvQuotedEmpty`|Quote empty strings and overrides quoted_string on empty strings when defined|`false`
`disableTelemetry`|Disables sending of telemetry data|`false`
`errorOutput`|Defines if errors should be written to `stdout` or `stderr`|`stderr`
`helpMode`|Defines what part of command's help to display. Allowed values are `options`, `examples`, `remarks`, `response`, `full`|`options`
`helpTarget`|Defines the way the command help will be shown. Allowed values are `console` or `web`
`output`|Defines the default output when issuing a command. Allowed values are `json`, `text`, `csv`, `md`, `none`|`json`
`printErrorsAsPlainText`|When output mode is set to `json`, print error messages as plain-text rather than JSON|`true`
`prompt`|Prompts for missing values in required options and enables interactive selection when multiple values are available for a command that requires a specific value to be retrieved.|`true`
`promptListPageSize`|By default, lists of choices longer than 7 will be paginated. Use this option to control how many choices will appear on the screen at once.|7
`showHelpOnFailure`|Automatically display help when executing a command failed|`true`
`tenantId`|ID of the default tenant to use when authenticating with|``
