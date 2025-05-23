-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# tenant serviceannouncement message get

Retrieves a specified service update message for the tenant

## Usage

```sh
m365 tenant serviceannouncement message get [options]
```

## Options

```md definition-list
`-i, --id <id>`
: The ID of the service update message.
```

<Global />

## Examples

Get service update message with ID MC001337

```sh
m365 tenant serviceannouncement message get --id MC001337
```

## Response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "startDateTime": "2021-07-08T00:37:37Z",
    "endDateTime": "2022-12-09T07:00:00Z",
    "lastModifiedDateTime": "2022-06-07T20:21:06.713Z",
    "title": "(Updated) Microsoft Lists: Custom list templates",
    "id": "MC267581",
    "category": "planForChange",
    "severity": "normal",
    "tags": [
      "Updated message",
      "New feature",
      "User impact",
      "Admin impact"
    ],
    "isMajorChange": false,
    "actionRequiredByDateTime": null,
    "services": [
      "SharePoint Online"
    ],
    "expiryDateTime": null,
    "hasAttachments": false,
    "viewPoint": null,
    "details": [],
    "body": {
      "contentType": "html",
      "content": "<p>Updated June 7, 2022: We have updated the rollout timeline below. Thank you for your patience.</p><p>This new feature will support the addition of custom list templates from your organization alongside the ready-made templates Microsoft provides to make it easy to get started tracking and managing information.</p> \
<p>[Key points]</p> \
<ul> \
<li>Microsoft 365 <a href=\"https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=70753\" target=\"_blank\">Roadmap ID: 70753</a></li> \
<li>Timing:<ul><li>Targeted release (entire org): Complete</li><li>Standard release: will roll out in mid-September (previously mid-May) and be complete by early November (previously mid-June)</li></ul></li> \
<li>Roll-out: tenant level </li> \
<li>Control type: user control / admin control</li> \
<li>Action: review, assess and educate</li></ul><p>[How this will affect your organization]</p><p>This feature will give organizations the ability to create their own custom list templates with custom formatting and schema. It will also empower organizations to create repeatable solutions within the same Microsoft Lists infrastructure (including list creation in SharePoint, Teams, and within the Lists app itself).</p><p>End-user impact:</p>\
<p>Visual updates to the list creation dialog and the addition of a<i> From your organization</i> tab when creating a new list. This new tab is where your custom list templates appear alongside the ready-made templates from Microsoft.</p>\
<p><img src=\"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/cms/api/am/imageFileData/RE4P81n?ver=c93f\" alt=\"Your custom list templates along with Microsoft ready-made templates\" width=\"550\"><br>\
Admin impact:</p>\
<p>Custom list templates can only be uploaded by a SharePoint administrator for Microsoft 365 by using PowerShell cmdlets. For consistency, the process of defining and uploading custom list templates is like the custom site templates experience.</p><p>To define and upload custom list templates, admins will use the following site template PowerShell cmdlets:</p><ul><li>Use the <a href=\"https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositescriptfromlist?view=sharepoint-ps\" target=\"_blank\">Get-SPOSiteScriptFromList</a> cmdlet to extract the site script from any list</li><li>Run <a href=\"https://docs.microsoft.com/powershell/module/sharepoint-online/add-spositescript?view=sharepoint-ps\" target=\"_blank\">Add-SPOSiteScript</a> and <b style=\"\">Add-SPOListDesign</b> to add the custom list template to your organization.</li><li>Scope who sees the template by using <a href=\"https://docs.microsoft.com/powershell/module/sharepoint-online/grant-spositedesignrights?view=sharepoint-ps\" target=\"_blank\">Grant-SPOSiteDesignRights</a>  (Optional).</li></ul><p>The visual updates for this feature will be seen by end-users in the updated user interface (UI) when creating a list.</p><p>The <i>From your organization</i> tab will be empty until your organization defines and publishes custom list templates.</p>\
<p><img src=\"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/cms/api/am/imageFileData/RE4P81t?ver=70be\" alt=\"Your custom list templates along with Microsoft ready-made templates\" width=\"550\"></p><p>[What you need to do to prepare]</p><p>You might want to notify your users about this new capability and update your training and documentation as appropriate.</p>\
<p>Learn more:</p><ul><li><a href=\"https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview\" target=\"_blank\">PowerShell Cmdlets documentation for custom list templates</a></li><li> <a href=\"https://docs.microsoft.com/sharepoint/lists-custom-template\" target=\"_blank\">Creating custom list templates</a></li></ul>"
    }
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  actionRequiredByDateTime: null
  body                    : {"contentType":"html","content":"<p>Updated June 7, 2022: We have updated the rollout timeline below. Thank you for your patience.</p><p>This new feature will support the addition of custom list templates from your organization alongside the ready-made templates Microsoft provides to make it easy to get started tracking and managing information.</p> 
<p>[Key points]</p> 
<ul> 
<li>Microsoft 365 <a href=\"https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=70753\" target=\"_blank\">Roadmap ID: 70753</a></li> 
<li>Timing:<ul><li>Targeted release (entire org): Complete</li><li>Standard release: will roll out in mid-September (previously mid-May) and be complete by early November (previously mid-June)</li></ul></li> 
<li>Roll-out: tenant level </li> 
<li>Control type: user control / admin control</li> 
<li>Action: review, assess and educate</li></ul><p>[How this will affect your organization]</p><p>This feature will give organizations the ability to create their own custom list templates with custom formatting and schema. It will also empower organizations to create repeatable solutions within the same Microsoft Lists infrastructure (including list creation in SharePoint, Teams, and within the Lists app itself).</p><p>End-user impact:</p>
<p>Visual updates to the list creation dialog and the addition of a<i> From your organization</i> tab when creating a new list. This new tab is where your custom list templates appear alongside the ready-made templates from Microsoft.</p>
<p><img src=\"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/cms/api/am/imageFileData/RE4P81n?ver=c93f\" alt=\"Your custom list templates along with Microsoft ready-made templates\" width=\"550\"><br>
Admin impact:</p>
<p>Custom list templates can only be uploaded by a SharePoint administrator for Microsoft 365 by using PowerShell cmdlets. For consistency, the process of defining and uploading custom list templates is like the custom site templates experience.</p><p>To define and upload custom list templates, admins will use the following site template PowerShell cmdlets:</p><ul><li>Use the <a href=\"https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositescriptfromlist?view=sharepoint-ps\" target=\"_blank\">Get-SPOSiteScriptFromList</a> cmdlet to extract the site script from any list</li><li>Run <a href=\"https://docs.microsoft.com/powershell/module/sharepoint-online/add-spositescript?view=sharepoint-ps\" target=\"_blank\">Add-SPOSiteScript</a> and <b style=\"\">Add-SPOListDesign</b> to add the custom list template to your organization.</li><li>Scope who sees the template by using <a href=\"https://docs.microsoft.com/powershell/module/sharepoint-online/grant-spositedesignrights?view=sharepoint-ps\" target=\"_blank\">Grant-SPOSiteDesignRights</a>  (Optional).</li></ul><p>The visual updates for this feature will be seen by end-users in the updated user interface (UI) when creating a list.</p><p>The <i>From your organization</i> tab will be empty until your organization defines and publishes custom list templates.</p>
<p><img src=\"https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/cms/api/am/imageFileData/RE4P81t?ver=70be\" alt=\"Your custom list templates along with Microsoft ready-made templates\" width=\"550\"></p><p>[What you need to do to prepare]</p><p>You might want to notify your users about this new capability and update your training and documentation as appropriate.</p>
<p>Learn more:</p><ul><li><a href=\"https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview\" target=\"_blank\">PowerShell Cmdlets documentation for custom list templates</a></li><li> <a href=\"https://docs.microsoft.com/sharepoint/lists-custom-template\" target=\"_blank\">Creating custom list templates</a></li></ul>"}
  category                : planForChange
  details                 : []
  endDateTime             : 2022-12-09T07:00:00Z
  expiryDateTime          : null
  hasAttachments          : false
  id                      : MC267581
  isMajorChange           : false
  lastModifiedDateTime    : 2022-06-07T20:21:06.713Z
  services                : ["SharePoint Online"]
  severity                : normal
  startDateTime           : 2021-07-08T00:37:37Z
  tags                    : ["Updated message","New feature","User impact","Admin impact"]
  title                   : (Updated) Microsoft Lists: Custom list templates
  viewPoint               : null
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  startDateTime,endDateTime,lastModifiedDateTime,title,id,category,severity,tags,isMajorChange,actionRequiredByDateTime,services,expiryDateTime,hasAttachments,viewPoint,details,body
  2021-07-08T00:37:37Z,2022-12-09T07:00:00Z,2022-06-07T20:21:06.713Z,(Updated) Microsoft Lists: Custom list templates,MC267581,planForChange,normal,"[""Updated message"",""New feature"",""User impact"",""Admin impact""]",,,"[""SharePoint Online""]",,,,[],"{""contentType"":""html"",""content"":""<p>Updated June 7, 2022: We have updated the rollout timeline below. Thank you for your patience.</p><p>This new feature will support the addition of custom list templates from your organization alongside the ready-made templates Microsoft provides to make it easy to get started tracking and managing information.</p> 
<p>[Key points]</p> 
<ul> 
<li>Microsoft 365 <a href=\""https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=70753\"" target=\""_blank\"">Roadmap ID: 70753</a></li> 
<li>Timing:<ul><li>Targeted release (entire org): Complete</li><li>Standard release: will roll out in mid-September (previously mid-May) and be complete by early November (previously mid-June)</li></ul></li> 
<li>Roll-out: tenant level </li> 
<li>Control type: user control / admin control</li> 
<li>Action: review, assess and educate</li></ul><p>[How this will affect your organization]</p><p>This feature will give organizations the ability to create their own custom list templates with custom formatting and schema. It will also empower organizations to create repeatable solutions within the same Microsoft Lists infrastructure (including list creation in SharePoint, Teams, and within the Lists app itself).</p><p>End-user impact:</p>
<p>Visual updates to the list creation dialog and the addition of a<i> From your organization</i> tab when creating a new list. This new tab is where your custom list templates appear alongside the ready-made templates from Microsoft.</p>
<p><img src=\""https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/cms/api/am/imageFileData/RE4P81n?ver=c93f\"" alt=\""Your custom list templates along with Microsoft ready-made templates\"" width=\""550\""><br>
Admin impact:</p>
<p>Custom list templates can only be uploaded by a SharePoint administrator for Microsoft 365 by using PowerShell cmdlets. For consistency, the process of defining and uploading custom list templates is like the custom site templates experience.</p><p>To define and upload custom list templates, admins will use the following site template PowerShell cmdlets:</p><ul><li>Use the <a href=\""https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositescriptfromlist?view=sharepoint-ps\"" target=\""_blank\"">Get-SPOSiteScriptFromList</a> cmdlet to extract the site script from any list</li><li>Run <a href=\""https://docs.microsoft.com/powershell/module/sharepoint-online/add-spositescript?view=sharepoint-ps\"" target=\""_blank\"">Add-SPOSiteScript</a> and <b style=\""\"">Add-SPOListDesign</b> to add the custom list template to your organization.</li><li>Scope who sees the template by using <a href=\""https://docs.microsoft.com/powershell/module/sharepoint-online/grant-spositedesignrights?view=sharepoint-ps\"" target=\""_blank\"">Grant-SPOSiteDesignRights</a>  (Optional).</li></ul><p>The visual updates for this feature will be seen by end-users in the updated user interface (UI) when creating a list.</p><p>The <i>From your organization</i> tab will be empty until your organization defines and publishes custom list templates.</p>
<p><img src=\""https://EXAMPLE_SECRET_VALUE_PLACEHOLDER/cms/api/am/imageFileData/RE4P81t?ver=70be\"" alt=\""Your custom list templates along with Microsoft ready-made templates\"" width=\""550\""></p><p>[What you need to do to prepare]</p><p>You might want to notify your users about this new capability and update your training and documentation as appropriate.</p>
<p>Learn more:</p><ul><li><a href=\""https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview\"" target=\""_blank\"">PowerShell Cmdlets documentation for custom list templates</a></li><li> <a href=\""https://docs.microsoft.com/sharepoint/lists-custom-template\"" target=\""_blank\"">Creating custom list templates</a></li></ul>""}"
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # tenant serviceannouncement message get --id "MC267581"

  Date: 5/24/2022

  ## (Updated) Microsoft Lists: Custom list templates (MC267581)

  Property | Value
  ---------|-------
  startDateTime | 2021-07-08T00:37:37Z
  endDateTime | 2022-12-09T07:00:00Z
  lastModifiedDateTime | 2022-06-07T20:21:06.713Z
  title | (Updated) Microsoft Lists: Custom list templates
  id | MC267581
  category | planForChange
  severity | normal
  isMajorChange | false
  hasAttachments | false
  ```

  </TabItem>
</Tabs>

## More information

- Microsoft Graph REST API reference: [https://learn.microsoft.com/graph/api/serviceupdatemessage-get](https://learn.microsoft.com/graph/api/serviceupdatemessage-get)
