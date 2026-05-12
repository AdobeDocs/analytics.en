---
description: You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite
title: Browser import
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
TQID: https://experienceleague.adobe.com/iFVW-d9C12dj6TXnUlA3-zVF0oBAWpJwg1JK8LqzF-s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Browser import (legacy)

{{classification-importer-deprecation}}

You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite

## Browser import {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite 

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Classifications Browser Import - Field Descriptions {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Element | Description|
| --- | --- |
| Select Report Suite|The report suite where you want to import the classifications data. The import data file must match the format of the data set in the report suite. |
| Data Set to be Classified|The data set to receive the classifications. The drop-down list includes all reports in your report suites that are configured for classifications. |
| Select file to Import|Lets you browse to locate the import data file you want to upload.  Note:  The upload file size limit is 1 MB. |
| Overwrite Data on Conflicts | Automatically overwrites existing data that conflicts with the imported data.<br>**Important**: This option is not available for report suites enabled for the New Classification Architecture.|
| Automatically Download Classification File After the Import is Complete | Automatically downloads a tab-delimited file that represents the data set with the newly uploaded classifications data. Adobe automatically generates this file for you if the import creates any unique IDs, or if any errors occur.<br>**Important**: This option is not available for report suites enabled for the New Classification Architecture.|
  

## Import classifications via the browser {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**.
1. Configure the **[!UICONTROL Browser Import]** fields.
1. Click **[!UICONTROL Import File]**.
1. Watch the status window for processing messages.
1. (Conditional) If you selected **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specify where you want to store the resulting file when processing completes. Note that this option is not available for report suites enabled for the New Classification Architecture.

>A successful import immediately displays the appropriate changes in an export. However, data changes in reports take up to four hours when using a browser import and up to 24 hours when using an FTP import.
