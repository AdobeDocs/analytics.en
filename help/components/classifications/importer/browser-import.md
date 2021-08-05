---
description: You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite
subtopic: Classifications
title: Browser import
feature: Admin Tools
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
---
# Browser import

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
