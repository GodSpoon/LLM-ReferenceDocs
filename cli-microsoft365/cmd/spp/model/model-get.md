-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
import Global from '/docs/cmd/_global.mdx';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# spp model get

Retrieves information about a document understanding model

## Usage

```sh
m365 spp model get [options]
```

## Options

```md definition-list
`-u, --siteUrl <siteUrl>`
: The URL of the content center site.

`-i, --id [id]`
: The unique ID of the model to retrieve. Specify `id` or `title` but not both.

`-t, --title [title]`
: The display name of the model to retrieve. Specify `id` or `title` but not both.

`--withPublications`
: Retrieves information about the library where it has been applied.
```

<Global />

## Examples

Retrieve information about a SharePoint Premium document understanding model, using model UniqueId.

```sh
m365 spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc"
```

Retrieve information about a SharePoint Premium document understanding model, using model Title

```sh
m365 spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "climicrosoft365Model"
```

## Response

### Standard response

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AIBuilderHybridModelType": null,
    "AzureCognitivePrebuiltModelName": null,
    "BaseContentTypeName": null,
    "ConfidenceScore": {
      "trainingStatus": {
        "kind": "original",
        "ClassifierStatus": {
          "TrainingStatus": "success",
          "TimeStamp": 1604429035541
        },
        "ExtractorsStatus": [
          {
            "TimeStamp": 1604429033385,
            "ExtractorName": "Contributor",
            "TrainingStatus": "success"
          }
        ]
      },
      "modelAccuracy": {
        "Classifier": 1,
        "Extractors": {
          "Contributor": 1
        }
      },
      "perSampleAccuracy": {
        "43": {
          "Classifier": 1,
          "Extractors": {
            "Contributor": 1
          }
        }
      },
      "perSamplePrediction": {
        "43": {
          "Extractors": {
            "Contributor": [
              "Benefit Change Notice"
            ]
          }
        }
      },
      "trainingFailures": {}
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "ContentTypeName": "BenefitsChangeNotice",
    "Created": "2020-11-03T12:30:55Z",
    "CreatedBy": "i:0#.w|sharepoint\system",
    "DriveId": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "Explanations": {
      "Classifier": [
        {
          "id": "24f0b71f-87c6-4f7d-9797-88e9eab00cb6",
          "kind": "dictionaryFeature",
          "name": "Contains ",
          "active": true,
          "nGrams": [
            "Benefit Change Notice"
          ],
          "caseSensitive": true,
          "ignoreDigitIdentity": false,
          "ignoreLetterIdentity": false
        }
      ],
      "Extractors": {
        "Contributor": [
          {
            "id": "9abdbfc9-6425-4e03-a344-305d3e60ad7f",
            "kind": "dictionaryFeature",
            "name": "text",
            "active": true,
            "nGrams": [
              "Benefit Change Notice"
            ],
            "caseSensitive": false,
            "ignoreDigitIdentity": false,
            "ignoreLetterIdentity": false
          }
        ]
      }
    },
    "ID": 3,
    "LastTrained": "2020-11-03T18:43:53Z",
    "ListID": "bc696b17-378c-4347-b509-5d52cc6f3823",
    "ModelSettings": null,
    "ModelType": 2,
    "Modified": "2024-06-27T02:45:32Z",
    "ModifiedBy": "i:0#.w|sharepoint\system",
    "ObjectId": "01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S",
    "PublicationType": 0,
    "Schemas": {
      "Extractors": {
        "Contributor": {
          "concepts": {
            "6af8ef33-4bf1-49ca-93d3-7a2358746747": {
              "name": "Contributor"
            }
          },
          "relationships": []
        }
      }
    },
    "SourceSiteUrl": "https://contoso.sharepoint.com/sites/ContentCenter",
    "SourceUrl": null,
    "SourceWebServerRelativeUrl": "/sites/ContentCenter",
    "UniqueId": "b10e0de5-c069-46f9-90f7-4fb8ac001372"
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AIBuilderHybridModelType       : null
  AzureCognitivePrebuiltModelName: null
  BaseContentTypeName            : null
  ConfidenceScore                : {"trainingStatus":{"kind":"original","ClassifierStatus":{"TrainingStatus":"success","TimeStamp":1604429035541},"ExtractorsStatus":[{"TimeStamp":1604429033385,"ExtractorName":"Contributor","TrainingStatus":"success"}]},"modelAccuracy":{"Classifier":1,"Extractors":{"Contributor":1}},"perSampleAccuracy":{"43":{"Classifier":1,"Extractors":{"Contributor":1}}},"perSamplePrediction":{"43":{"Extractors":{"Contributor":["Benefit Change Notice"]}}},"trainingFailures":{}}
  ContentTypeGroup               : Intelligent Document Content Types
  ContentTypeId                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ContentTypeName                : BenefitsChangeNotice
  Created                        : 2020-11-03T12:30:55Z
  CreatedBy                      : i:0#.w|sharepoint\system
  DriveId                        : b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Explanations                   : {"Classifier":[{"id":"24f0b71f-87c6-4f7d-9797-88e9eab00cb6","kind":"dictionaryFeature","name":"Contains \"Benefit Change Notice\"","active":true,"nGrams":["Benefit Change Notice"],"caseSensitive":true,"ignoreDigitIdentity":false,"ignoreLetterIdentity":false}],"Extractors":{"Contributor":[{"id":"9abdbfc9-6425-4e03-a344-305d3e60ad7f","kind":"dictionaryFeature","name":"text","active":true,"nGrams":["Benefit Change Notice"],"caseSensitive":false,"ignoreDigitIdentity":false,"ignoreLetterIdentity":false}]}}
  ID                             : 3
  LastTrained                    : 2020-11-03T18:43:53Z
  ListID                         : bc696b17-378c-4347-b509-5d52cc6f3823
  ModelSettings                  : null
  ModelType                      : 2
  Modified                       : 2024-06-27T02:45:32Z
  ModifiedBy                     : i:0#.w|sharepoint\system
  ObjectId                       : 01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S
  PublicationType                : 0
  SourceSiteUrl                  : https://contoso.sharepoint.com/sites/ContentCenter
  SourceUrl                      : null
  SourceWebServerRelativeUrl     : /sites/ContentCenter
  UniqueId                       : b10e0de5-c069-46f9-90f7-4fb8ac001372
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AIBuilderHybridModelType,AzureCognitivePrebuiltModelName,BaseContentTypeName,ContentTypeGroup,ContentTypeId,ContentTypeName,Created,CreatedBy,DriveId,ID,LastTrained,ListID,ModelName,ModelType,Modified,ModifiedBy,ObjectId,PublicationType,SourceSiteUrl,SourceUrl,SourceWebServerRelativeUrl,UniqueId
  ,,,Intelligent Document Content Types,EXAMPLE_SECRET_VALUE_PLACEHOLDER,BenefitsChangeNotice,2020-11-03T12:30:55Z,i:0#.w|sharepoint\system,b!EXAMPLE_SECRET_VALUE_PLACEHOLDER,3,2020-11-03T18:43:53Z,bc696b17-378c-4347-b509-5d52cc6f3823,B 
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "b10e0de5-c069-46f9-90f7-4fb8ac001372"

  Date: 29/09/2024

  ## 3

  Property | Value
  ---------|-------
  ContentTypeGroup | Intelligent Document Content Types
  ContentTypeId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ContentTypeName | BenefitsChangeNotice
  Created | 2020-11-03T12:30:55Z
  CreatedBy | i:0#.w\|sharepoint\system
  DriveId | b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ID | 3
  LastTrained | 2020-11-03T18:43:53Z
  ListID | bc696b17-378c-4347-b509-5d52cc6f3823
  ModelName | BenefitsChangeNotice
  ModelType | 2
  Modified | 2024-11-08T04:49:57Z
  ModifiedBy | i:0#.w\|sharepoint\system
  ObjectId | 01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S
  PublicationType | 0
  SourceSiteUrl | https://contoso.sharepoint.com/sites/ContentCenter
  SourceWebServerRelativeUrl | /sites/ContentCenter
  UniqueId | b10e0de5-c069-46f9-90f7-4fb8ac001372
  ```

  </TabItem>
</Tabs>

### `withPublications` response

When we make use of the option `withPublications`, the response will differ. 

<Tabs>
  <TabItem value="JSON">

  ```json
  {
    "AIBuilderHybridModelType": null,
    "AzureCognitivePrebuiltModelName": null,
    "BaseContentTypeName": null,
    "ConfidenceScore": {
      "trainingStatus": {
        "kind": "original",
        "ClassifierStatus": {
          "TrainingStatus": "success",
          "TimeStamp": 1604429035541
        },
        "ExtractorsStatus": [
          {
            "TimeStamp": 1604429033385,
            "ExtractorName": "Contributor",
            "TrainingStatus": "success"
          }
        ]
      },
      "modelAccuracy": {
        "Classifier": 1,
        "Extractors": {
          "Contributor": 1
        }
      },
      "perSampleAccuracy": {
        "43": {
          "Classifier": 1,
          "Extractors": {
            "Contributor": 1
          }
        }
      },
      "perSamplePrediction": {
        "43": {
          "Extractors": {
            "Contributor": [
              "Benefit Change Notice"
            ]
          }
        }
      },
      "trainingFailures": {}
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeId": "EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "ContentTypeName": "BenefitsChangeNotice",
    "Created": "2020-11-03T12:30:55Z",
    "CreatedBy": "i:0#.w|sharepoint\system",
    "DriveId": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
    "Explanations": {
      "Classifier": [
        {
          "id": "24f0b71f-87c6-4f7d-9797-88e9eab00cb6",
          "kind": "dictionaryFeature",
          "name": "Contains Benefit Change Notice",
          "active": true,
          "nGrams": [
            "Benefit Change Notice"
          ],
          "caseSensitive": true,
          "ignoreDigitIdentity": false,
          "ignoreLetterIdentity": false
        }
      ],
      "Extractors": {
        "Contributor": [
          {
            "id": "9abdbfc9-6425-4e03-a344-305d3e60ad7f",
            "kind": "dictionaryFeature",
            "name": "text",
            "active": true,
            "nGrams": [
              "Benefit Change Notice"
            ],
            "caseSensitive": false,
            "ignoreDigitIdentity": false,
            "ignoreLetterIdentity": false
          }
        ]
      }
    },
    "ID": 3,
    "LastTrained": "2020-11-03T18:43:53Z",
    "ListID": "bc696b17-378c-4347-b509-5d52cc6f3823",
    "ModelSettings": null,
    "ModelType": 2,
    "Modified": "2024-06-27T02:45:32Z",
    "ModifiedBy": "i:0#.w|sharepoint\system",
    "ObjectId": "01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S",
    "PublicationType": 0,
    "Schemas": {
      "Extractors": {
        "Contributor": {
          "concepts": {
            "6af8ef33-4bf1-49ca-93d3-7a2358746747": {
              "name": "Contributor"
            }
          },
          "relationships": []
        }
      }
    },
    "SourceSiteUrl": "https://contoso.sharepoint.com/sites/ContentCenter",
    "SourceUrl": null,
    "SourceWebServerRelativeUrl": "/sites/ContentCenter",
    "UniqueId": "b10e0de5-c069-46f9-90f7-4fb8ac001372",
    "Publications": [
      {
        "Created": "2020-11-03T12:52:12Z",
        "CreatedBy": "i:0#.f|membership|user@contoso.onmicrosoft.com",
        "DriveId": "b!EXAMPLE_SECRET_VALUE_PLACEHOLDER",
        "HasTargetSitePermission": true,
        "ID": 1,
        "ModelId": 3,
        "ModelName": "BenefitsChangeNotice.classifier",
        "ModelType": 0,
        "ModelUniqueId": "b10e0de5-c069-46f9-90f7-4fb8ac001372",
        "ModelVersion": "2.0",
        "Modified": "2020-11-03T18:45:18Z",
        "ModifiedBy": "i:0#.f|membership|user@contoso.onmicrosoft.com",
        "ObjectId": "01XHOXSCVXVZCQAAQWCNGK6NGADKKZUMW7",
        "PublicationType": 1,
        "TargetLibraryId": "7eb6c306-1680-4ba9-9bbe-6b5b7efb27be",
        "TargetLibraryName": "Documents",
        "TargetLibraryRemoved": false,
        "TargetLibraryServerRelativeUrl": "/sites/Spaces/Shared%20Documents",
        "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/Spaces/Shared%20Documents",
        "TargetSiteId": "7e44de0a-30e3-45ab-a601-057298c9068f",
        "TargetSiteUrl": "https://contoso.sharepoint.com/sites/Spaces",
        "TargetTableListId": "00000000-0000-0000-0000-000000000000",
        "TargetTableListName": null,
        "TargetTableListRemoved": false,
        "TargetTableListServerRelativeUrl": null,
        "TargetTableListUrl": null,
        "TargetWebId": "9166df43-8e45-43b8-94ef-3a22826346de",
        "TargetWebName": "Spaces",
        "TargetWebServerRelativeUrl": "/sites/Spaces",
        "UniqueId": "0045aeb7-1602-4c13-af34-c01a959a32df",
        "ViewOption": "NewViewAsDefault"
      }
    ]
  }
  ```

  </TabItem>
  <TabItem value="Text">

  ```text
  AIBuilderHybridModelType       : null
  AzureCognitivePrebuiltModelName: null
  BaseContentTypeName            : null
  ConfidenceScore                : {"trainingStatus":{"kind":"original","ClassifierStatus":{"TrainingStatus":"success","TimeStamp":1604429035541},"ExtractorsStatus":[{"TimeStamp":1604429033385,"ExtractorName":"Contributor","TrainingStatus":"success"}]},"modelAccuracy":{"Classifier":1,"Extractors":{"Contributor":1}},"perSampleAccuracy":{"43":{"Classifier":1,"Extractors":{"Contributor":1}}},"perSamplePrediction":{"43":{"Extractors":{"Contributor":["Benefit Change Notice"]}}},"trainingFailures":{}}
  ContentTypeGroup               : Intelligent Document Content Types
  ContentTypeId                  : EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ContentTypeName                : BenefitsChangeNotice
  Created                        : 2020-11-03T12:30:55Z
  CreatedBy                      : i:0#.w|sharepoint\system
  DriveId                        : b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  Explanations                   : {"Classifier":[{"id":"24f0b71f-87c6-4f7d-9797-88e9eab00cb6","kind":"dictionaryFeature","name":"Contains \"Benefit Change Notice\"","active":true,"nGrams":["Benefit Change Notice"],"caseSensitive":true,"ignoreDigitIdentity":false,"ignoreLetterIdentity":false}],"Extractors":{"Contributor":[{"id":"9abdbfc9-6425-4e03-a344-305d3e60ad7f","kind":"dictionaryFeature","name":"text","active":true,"nGrams":["Benefit Change Notice"],"caseSensitive":false,"ignoreDigitIdentity":false,"ignoreLetterIdentity":false}]}}
  ID                             : 3
  LastTrained                    : 2020-11-03T18:43:53Z
  ListID                         : bc696b17-378c-4347-b509-5d52cc6f3823
  ModelSettings                  : null
  ModelType                      : 2
  Modified                       : 2024-06-27T02:45:32Z
  ModifiedBy                     : i:0#.w|sharepoint\system
  ObjectId                       : 01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S
  PublicationType                : 0
  Publications                   : [{"Created":"2020-11-03T12:52:12Z","CreatedBy":"i:0#.f|membership|user@contoso.onmicrosoft.com","DriveId":"b!EXAMPLE_SECRET_VALUE_PLACEHOLDER","HasTargetSitePermission":true,"ID":1,"ModelId":3,"ModelName":"BenefitsChangeNotice.classifier","ModelType":0,"ModelUniqueId":"b10e0de5-c069-46f9-90f7-4fb8ac001372","ModelVersion":"2.0","Modified":"2020-11-03T18:45:18Z","ModifiedBy":"i:0#.f|membership|user@contoso.onmicrosoft.com","ObjectId":"01XHOXSCVXVZCQAAQWCNGK6NGADKKZUMW7","PublicationType":1,"TargetLibraryId":"7eb6c306-1680-4ba9-9bbe-6b5b7efb27be","TargetLibraryName":"Documents","TargetLibraryRemoved":false,"TargetLibraryServerRelativeUrl":"/sites/Spaces/Shared%20Documents","TargetLibraryUrl":"https://contoso.sharepoint.com/sites/Spaces/Shared%20Documents","TargetSiteId":"7e44de0a-30e3-45ab-a601-057298c9068f","TargetSiteUrl":"https://contoso.sharepoint.com/sites/Spaces","TargetTableListId":"00000000-0000-0000-0000-000000000000","TargetTableListName":null,"TargetTableListRemoved":false,"TargetTableListServerRelativeUrl":null,"TargetTableListUrl":null,"TargetWebId":"9166df43-8e45-43b8-94ef-3a22826346de","TargetWebName":"Spaces","TargetWebServerRelativeUrl":"/sites/Spaces","UniqueId":"0045aeb7-1602-4c13-af34-c01a959a32df","ViewOption":"NewViewAsDefault"}]
  Schemas                        : {"Extractors":{"Contributor":{"concepts":{"6af8ef33-4bf1-49ca-93d3-7a2358746747":{"name":"Contributor"}},"relationships":[]}}}
  SourceSiteUrl                  : https://contoso.sharepoint.com/sites/ContentCenter
  SourceUrl                      : null
  SourceWebServerRelativeUrl     : /sites/ContentCenter
  UniqueId                       : b10e0de5-c069-46f9-90f7-4fb8ac001372
  ```

  </TabItem>
  <TabItem value="CSV">

  ```csv
  AIBuilderHybridModelType,AzureCognitivePrebuiltModelName,BaseContentTypeName,ContentTypeGroup,ContentTypeId,ContentTypeName,Created,CreatedBy,DriveId,ID,LastTrained,ListID,ModelName,ModelType,Modified,ModifiedBy,ObjectId,PublicationType,SourceSiteUrl,SourceUrl,SourceWebServerRelativeUrl,UniqueId
  ,,,Intelligent Document Content Types,EXAMPLE_SECRET_VALUE_PLACEHOLDER,BenefitsChangeNotice,2020-11-03T12:30:55Z,i:0#.w|sharepoint\system,b!EXAMPLE_SECRET_VALUE_PLACEHOLDER,3,2020-11-03T18:43:53Z,bc696b17-378c-4347-b509-5d52cc6f3823,BenefitsChangeNotice,2,2024-11-08T04:49:57Z,i:0#.w|sharepoint\system,01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S,0,https://contoso.sharepoint.com/sites/ContentCenter,,/sites/ContentCenter,b10e0de5-c069-46f9-90f7-4fb8ac001372
  ```

  </TabItem>
  <TabItem value="Markdown">

  ```md
  # spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "b10e0de5-c069-46f9-90f7-4fb8ac001372" --withPublications

  Date: 29/09/2024

  ## 3

  Property | Value
  ---------|-------
  ContentTypeGroup | Intelligent Document Content Types
  ContentTypeId | EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ContentTypeName | BenefitsChangeNotice
  Created | 2020-11-03T12:30:55Z
  CreatedBy | i:0#.w\|sharepoint\system
  DriveId | b!EXAMPLE_SECRET_VALUE_PLACEHOLDER
  ID | 3
  LastTrained | 2020-11-03T18:43:53Z
  ListID | bc696b17-378c-4347-b509-5d52cc6f3823
  ModelName | BenefitsChangeNotice
  ModelType | 2
  Modified | 2024-11-08T04:49:57Z
  ModifiedBy | i:0#.w\|sharepoint\system
  ObjectId | 01XHOXSCXFBUHLC2OA7FDJB52PXCWAAE3S
  PublicationType | 0
  SourceSiteUrl | https://contoso.sharepoint.com/sites/ContentCenter
  SourceWebServerRelativeUrl | /sites/ContentCenter
  UniqueId | b10e0de5-c069-46f9-90f7-4fb8ac001372
  ```

  </TabItem>
</Tabs>
