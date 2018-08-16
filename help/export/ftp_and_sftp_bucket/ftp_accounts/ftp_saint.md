---
description: The classifications (SAINT) FTP option provides more flexibility in uploading large classification data sets, including the ability to upload data into multiple report suites and to upload data sets larger than 50,000 rows.
keywords: ftp;sftp
seo-description: The classifications (SAINT) FTP option provides more flexibility in uploading large classification data sets, including the ability to upload data into multiple report suites and to upload data sets larger than 50,000 rows.
seo-title: Classifications
solution: Analytics
title: Classifications
uuid: 12fed0b0-7d09-4da5-8563-1c3cc12c09ab
index: y
internal: n
snippet: y
translate: y
---

# Classifications

See [ classifications](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) for steps on how to download classification data via FTP and how to upload data files via FTP (including the steps to create an FTP account). 

The amount of time required for the system to import these files varies, based on a number of factors. If an uploaded file is still present on the FTP server after six hours, work with your organization's supported users to contact Adobe Customer Care. 

A successful import immediately shows the appropriate changes in an export, while the data changes in Analytics may take up to four hours with a browser import and up to 24 hours with an FTP import. 

For information on FTP limits and data retention, see [ FTP Limits and Data Retention](../../ftp_and_sftp_bucket/ftp_limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E). 

## About the .fin File for Classifications and Data Sources Uploads {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL  Data Source] file ( [!DNL  .tab]or [!DNL  .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL  .fin] extension. This [!DNL  .fin] file is a finish file. The purpose of the file is to tell the system that the data file has been completely uploaded to the FTP account. The [!DNL  .fin] file lets Adobe recognize that you are done with your import. After you submit it, Adobe removes both files off of the FTP and begins processing the import. 
Import File: [!DNL  Classifications.tab] 

Finish File: [!DNL  Classifications.fin] 

If you upload your Data Sources or classification file without an accompanying [!DNL  .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL  Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL  Notification Recipient] in the [!UICONTROL  Create FTP Account] window of Analytics. If no email address is entered in this field, no notification is sent. 

If you do upload your file with a [!DNL  .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL  Notification Recipient] field in the [!UICONTROL  Create FTP Account] window. If no email address is entered, no notification is sent. 
