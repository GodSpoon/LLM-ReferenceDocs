<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - FILE Commands Reference

*This is an automatically generated condensed reference of all FILE commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-09-01*

---

## Table of Contents

- [convert-pdf](#convert-pdf)
- [file-add](#file-add)
- [file-copy](#file-copy)
- [file-list](#file-list)
- [file-move](#file-move)

---

## convert-pdf

### Syntax
```
m365 file convert pdf [options]
```

### Example
```
m365 file convert pdf --sourceFile file.docx --targetFile file.pdf

m365 file convert pdf --sourceFile file.docx --targetFile "https://contoso.sharepoint.com/Shared Documents/file.pdf"

m365 file convert pdf --sourceFile "https://contoso.sharepoint.com/Shared Documents/file.docx" --targetFile file.pdf

m365 file convert pdf --sourceFile "https://contoso.sharepoint.com/Shared Documents/file.docx" --targetFile "https://contoso.sharepoint.com/Shared Documents/file.pdf"

```

### Remarks
To convert a local file to PDF, CLI will temporarily upload the file to a document library. If you're using app-only authentication, CLI will upload the file to the default document library in the root site collection on your tenant. If you're authenticated as a user, CLI will upload the file to the default document library in your OneDrive for Business. After the conversion, CLI will remove the uploaded file.

If you choose to store the converted file in a document library, CLI will store the converted PDF file temporarily in the temp folder on your computer. After the PDF file has been uploaded to the location you specified, CLI will remove the temporary file.

If the conversion process fails, CLI will attempt to clean up the temporary files (the source file uploaded to your tenant, if you're converting a local file to PDF, and the converted PDF file on your disk if you chose to upload the converted file to your tenant). If removing the temporary files fails, you will need to clean them up yourself. CLI will list the URL and/or path of the files to remove.



---

## file-add

### Syntax
```
m365 file add [options]
```

### Example
```
m365 file add --filePath file.pdf --folderUrl "https://contoso.sharepoint.com/Shared Documents"```

### Remarks
The `folderUrl` must be an absolute URL to the document library where the file should be uploaded. The document library can be located in any site collection in your tenant, including OneDrive for Business. The `folderUrl` can also point to a (sub)folder in the document library.

By default, the `file add` command will automatically lookup the ID of the site where you want to upload the file based on the specified `folderUrl`. It will do this, by breaking the URL into chunks and incrementally calling Microsoft Graph to retrieve site information. This is necessary, because there is no other way looking at the URL to distinguish where the site URL ends and the document library URL starts. If you want to speed up uploading files, or you use resource-specific consent and your Microsoft Entra app only has access to the specific site, you can use the `siteUrl` option to specify the URL of the site yourself.



---

## file-copy

### Syntax
```
m365 file copy [options]
```

### Example
```
m365 file copy --webUrl https://contoso.sharepoint.com/sites/project --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents"```

---

## file-list

### Syntax
```
m365 file list [options]
```

### Example
```
m365 file list --webUrl https://contoso.sharepoint.com/sites/project-x --folderUrl 'Shared Documents'```

### Remarks
This command is an improved version of the `spo file list` command. The main difference between the two commands is, that `file list` uses Microsoft Graph and properly supports retrieving files from large folders. Because `file list` uses Microsoft Graph and `spo file list` uses SharePoint REST APIs, the data returned by both commands is different.



---

## file-move

### Syntax
```
m365 file move [options]
```

### Example
```
m365 file move --webUrl "https://contoso.sharepoint.com/sites/project" --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/project/Shared Documents/NewFolder"```

---
