-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# app open

Opens Microsoft Entra app in the Microsoft Entra ID portal

## Usage

```sh
m365 app open [options]
```

## Options

```md definition-list
`--appId [appId]`
: Optional Application (client) ID of the Microsoft Entra application registration to open. Uses the app from the `.m365rc.json` file corresponding to the `appId`. If multiple apps are available, this will evade the prompt to choose an app. If the `appId` is not available in the list of apps, an error is thrown.

`--preview`
: Use to open the url of the Microsoft Entra ID preview portal.
```

<Global />

## Remarks

If config setting `autoOpenLinksInBrowser` is configured to true, the command will automatically open the link to the Azure Portal in the browser.

Gets the app from the `.m365rc.json` file in the current directory. If the `--appId` option is not used and multiple apps are available, it will prompt the user to choose one.

## Examples

Prints the URL to the Microsoft Entra application registration management page on the Azure Portal. 

```sh
m365 app open
```

Prints the url of the Microsoft Entra application registration management page on the preview Azure Portal.

```sh
m365 app open --preview
```

Prints the URL to the Microsoft Entra application registration management page on the Azure Portal, evading a possible choice prompt in the case of multiple saved apps in the `.m365rc.json` file. 

```sh
m365 app open --appId d75be2e1-0204-4f95-857d-51a37cf40be8 
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  "Use a web browser to open the page https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationMenuBlade/Overview/appId/02f9ff8c-b79e-4552-bdda-4facd74d6df2/isMSAApp/"
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  Use a web browser to open the page https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationMenuBlade/Overview/appId/02f9ff8c-b79e-4552-bdda-4facd74d6df2/isMSAApp/
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  Use a web browser to open the page https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationMenuBlade/Overview/appId/02f9ff8c-b79e-4552-bdda-4facd74d6df2/isMSAApp/
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  Use a web browser to open the page https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationMenuBlade/Overview/appId/02f9ff8c-b79e-4552-bdda-4facd74d6df2/isMSAApp/
  ```

  </TabItem>
</Tabs>
