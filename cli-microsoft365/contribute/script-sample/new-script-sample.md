-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Creating a new script sample

All samples may be found in the folder `docs/docs/sample-scripts` grouped in categories. CLI for Microsoft 365 script samples are synchronized to the [Microsoft Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery/) and therefore they need additional metadata to be specified to be presented correctly in the gallery.

## Structure

Each sample needs to be stored in a separate folder. The folder name should be the same as the sample title. The sample folder should have the following structure:

Note that all whitespaces in the title should be replaced with a dash (`-`).

```
my-new-sample/
├─ assets/
│  ├─ preview.png
│  ├─ sample.json
├─ index.mdx
```

- `assets/sample.json` - this file has additional metadata about the sample that is needed to properly synchronize the sample to the Microsoft Sample Solution Gallery. 
- `assets/preview.png` - this image will be shown as the sample preview in the Microsoft Sample Solution Gallery. This could present the result of the script sample (e.g. if your script adds list items to a SharePoint list, the preview image could show a screen of the populated list). 
- `index.mdx` - this is the main file that contains the sample title, description, author, tags, and the script (or scripts if the sample was developed in multiple technologies/languages) 

### Sample.json (sample metadata)

This file is needed to properly display the sample on the Microsoft Sample Solution Gallery. Please use the template below with information on how to fill in the file. 

:::info

All places marked with `<>` are placeholders that should be populated accordingly.

:::

```json title="assets/sample.json"
[
  {
    "name": "pnp-<Same as folder name e.g. pnp-disable-tenant-wide-extension>",
    "source": "pnp",
    "title": "<Same as sample title in the index.mdx file e.g. Disable specified Tenant-wide Extension>",
    "url": "<Url to the sample on the CLI for Microsoft 365 docs page e.g. https://pnp.github.io/cli-microsoft365/sample-scripts/spo/disable-tenant-wide-extension>",
    "creationDateTime": "<Date when the sample was first created>",
    "updateDateTime": "<Date of the last update of the sample file>",
    "shortDescription": "<Short one-liner description of the sample main goal or functionality>",
    "longDescription": [
      "<Long and detailed description of the sample. Should be similar to the one used in the index.mdx file>"
    ],
    "products": [
      "<Name of the Microsoft 365 product this sample interacts with e.g. SharePoint>"
    ],
    "categories": [],
    "tags": [
      "<Collection of tags related to the sample. Should be the same list as defined in the index.mdx file. e.g. provisioning, libraries>"
    ],
    "metadata": [
      {
        "key": "CLI-FOR-MICROSOFT365",
        "value": "<Provide the version of CLI which was used to develop the sample e.g. v6.1>"
      }
    ],
    "thumbnails": [
      {
        "type": "image",
        "order": 100,
        "url": "https://raw.githubusercontent.com/pnp/cli-microsoft365/main/docs/docs/sample-scripts/<Sample folder path>/assets/preview.png",
        "alt": "preview image for the sample"
      }
    ],
    "authors": [
      {
        "gitHubAccount": "<GitHub account name>",
        "pictureUrl": "<Url to the GitHub account image e.g. https://avatars.githubusercontent.com/u/123456789?v=4>",
        "name": "<Name>"
      }
    ],
    "references": [
      {
        "name": "Want to learn more about CLI for Microsoft 365 and the commands",
        "description": "Check out the CLI for Microsoft 365 site to get started and for the reference to the commands.",
        "url": "https://aka.ms/cli-m365"
      }
    ]
  }
]
```

## Sample contents

The sample file should contain a title, a short description, an author, tags, and the script in code blocks. To help you get started you may use the template below.

````md title="index.mdx"
---
tags:
  - provisioning
  - libraries
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Cool sample to add multiple lists in a site

Author: [author name](https://link)

Short description of the sample functionality.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  # Put your PowerShell script here
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  # Put your Bash script here
  ```

  </TabItem>
</Tabs>
````

## Next step

With your sample script ready. The next step is to submit your local code to the CLI for Microsoft 365 repository. This is explained in the next chapter, creating the PR: [Submitting the Pull Request (PR)](../creating-the-pr.mdx).
