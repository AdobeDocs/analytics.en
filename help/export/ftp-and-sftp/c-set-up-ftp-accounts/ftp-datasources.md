---
description: You can use Analytics to create and manage FTP-based Data Sources, which leverages FTP file transfer to import offline or historical data into the Experience Cloud.
keywords: ftp;sftp
title: Data Sources overview
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
---
# Data Sources

You can use Analytics to create and manage FTP-based Data Sources, which leverages FTP file transfer to import offline or historical data into the Experience Cloud.

After creating a Data Sources instance, the tool provides an FTP location that you can use to upload Data Sources files. Once uploaded, Data Sources automatically locates and processes them. After the files are processed, the data is available for Analytics reporting.

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. Your FTP login information is displayed in the [!UICONTROL Activate a Data Source] window in the [!UICONTROL Upload/FTP Information] section.

For information on FTP limits and data retention, see [FTP Limits and Data Retention](/help/export/ftp-and-sftp/ftp-limits.md).

## About the .fin File for Classifications and Data Sources Uploads {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. The purpose of the file is to tell the system that the data file has been completely uploaded to the FTP account. The [!DNL .fin] file lets Adobe recognize that you are done with your import. After you submit it, Adobe removes both files off of the FTP and begin processing the import.
Import File: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. If no email address is entered in this field, no notification is sent.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. If no email address is entered, no notification is sent.
