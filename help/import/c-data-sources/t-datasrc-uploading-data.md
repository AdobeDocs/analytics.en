---
description: Steps that describe how to upload a data sources file.
seo-description: Steps that describe how to upload a data sources file.
seo-title: Upload a Data Sources file
solution: Analytics
subtopic: Data sources
title: Upload a Data Sources file
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
---

# Upload a Data Sources file

Steps that describe how to upload a data sources file.

 After you have prepared a Data Sources data file, submit it to Data Sources for processing. Adobe maintains several Data Sources FTP servers where you can upload Data Sources files. Remember the following about the Data Sources FTP servers:

* Select FTP Info next to the Data Source entry in the [!UICONTROL Data Sources Manage] tab to see the FTP Host, Login, and Password information for the data source's FTP account. Anyone with access to this information can upload data into your report suite. 
* For security purposes, FTP accounts are closed after 30 days of inactivity. 
* FTP accounts are data source-specific. You cannot use one FTP account to upload Data Sources files to multiple data sources.

**To upload a data sources file** 

1. Use an FTP client to send the data to your Data Sources FTP site.

   (Available in the FTP Info link in the Data Sources Manager). 

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   The [!DNL .fin] file must have the exact same name as the Data Sources file, except for the file extension. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   Do not upload the file until all Data Sources files have finished uploading. Otherwise, Data Sources might attempt to process an incomplete file. 
1. Watch for any messages during the Data Sources file processing.

   Data Sources Manager displays any errors that occur during the file processing. 

