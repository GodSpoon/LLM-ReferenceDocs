-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - files
  - libraries
  - ai
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Create sample documents in SharePoint with OpenAI

Author: [Nanddeep Nachan](https://nanddeepnachanblogs.com/posts/EXAMPLE_SECRET_VALUE_PLACEHOLDER/)

While working with SharePoint, we most times need to create test content related to a specific topic. OpenAI is the best fit in this case to generate content related to any topic.

The below script shows how OpenAI can be combined with CLI for Microsoft 365 to generate test documents in SharePoint.

Prerequisites:

- OpenAI API key.
- Document library should be available in the destination SharePoint site.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  param
  (
      [Parameter(Mandatory = $true, HelpMessage="The URL of the site where the files should be uploaded to")][string] $SiteURL,
      [Parameter(Mandatory = $true, HelpMessage="Site-relative or server-relative URL to the folder where the files should be uploaded")][string] $Folder,
      [Parameter(Mandatory = $true, HelpMessage="The OpenAI API key")][string] $OpenAiApiKey,
      [Parameter(Mandatory = $true, HelpMessage="Number of test files to generate")][int] $NumberOfDocuments
  )

  function New-WordFile {
    param(
        [string]$FileName,
        [string]$Content
    )

    # Load Word application
    $word = New-Object -ComObject Word.Application

    # Create new document
    $doc = $word.Documents.Add()

    # Add content to document
    $selection = $word.Selection
    $selection.TypeText($Content)

    # Save document
    $path = Join-Path (Get-Location).Path $FileName
    $doc.SaveAs("$path")
    $doc.Close()

    # Close Word application
    $word.Quit()

    # Clean up
    $null = [System.Runtime.InteropServices.Marshal]::ReleaseComObject([System.__ComObject]$word)
    [gc]::Collect()
    [gc]::WaitForPendingFinalizers()
    Remove-Variable word
  }

  try {
    $m365Status = m365 status
    if ($m365Status -eq "Logged Out") {
      Write-Host "Logging in the User!"
      m365 login --authType browser
    }

    $apiEndpoint = "https://api.openai.com/v1/completions"

    $headers = @{
      "Content-Type" = "application/json"
      "Authorization" = "Bearer $OpenAiApiKey"
    }

    $requestBody = @{
      prompt = "Generate $NumberOfDocuments comma-separated distinct random nouns without spaces"
      model = "text-davinci-003"        
      temperature = 0.7
      max_tokens = 256
    }

    $response = Invoke-WebRequest -Uri $apiEndpoint -Method POST -Headers $headers -Body (ConvertTo-Json $requestBody)
    $randomGeneratedWordsContent = $response.Content | ConvertFrom-Json
    $randomGeneratedWords = $EXAMPLE_SECRET_VALUE_PLACEHOLDER -replace "`n","" -replace "`r",""
    Write-Host "$NumberOfDocuments random generated words are: $randomGeneratedWords"
    $randomWords = $randomGeneratedWords.Split(',')

    $counter = 1
    Foreach ($randomWord in $randomWords) {
      $requestBody = @{
        prompt = "Write essay about $randomWord"
        model = "text-davinci-003"        
        temperature = 1
        max_tokens = 256
      }

      $response = Invoke-WebRequest -Uri $apiEndpoint -Method POST -Headers $headers -Body (ConvertTo-Json $requestBody)
      $essayContent = $response.Content | ConvertFrom-Json
      $essay = $essayContent.choices.text

      Write-Host "Generating document ($counter / $($randomWords.count)): $randomWord.docx"
      New-WordFile -FileName "$randomWord.docx" -Content $essay

      Write-Host "Uploading file $randomWord.docx..."
      $path = Join-Path (Get-Location).Path "$randomWord.docx"
      m365 spo file add --webUrl $SiteURL --folder $Folder --path $path

      Remove-Item -Path $path -Force

      $counter++
    }
  }
  catch {
      Write-Host -f Red "Error generating test documents: " $_.Exception.Message
  }

  Write-Host "Finished"
  ```

  </TabItem>
</Tabs>
