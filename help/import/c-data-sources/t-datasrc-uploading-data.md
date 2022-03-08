---
description: Steps that describe how to upload a data sources file.
title: Upload a Data Sources file
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 8b7fa32c-01f2-452b-bf8e-8a81da266926
---
# Upload a Data Sources file

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
1. After the .fin file is uploaded, it's important that you log out of the Data Sources FTP site. The reason is that  Analytics uses logout events as a trigger to indicate that files are ready for processing.
1. Watch for any messages during the Data Sources file processing.

   Data Sources Manager displays any errors that occur during the file processing.
