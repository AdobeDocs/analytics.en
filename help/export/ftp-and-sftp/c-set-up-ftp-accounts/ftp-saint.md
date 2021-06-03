---
description: The classifications (SAINT) FTP option provides more flexibility in uploading large classification data sets, including the ability to upload data into multiple report suites and to upload data sets larger than 50,000 rows.
keywords: ftp;sftp
title: Classifications
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
---
# Classifications

The classifications FTP option provides more flexibility in uploading large classification data sets, including the ability to upload data into multiple report suites and to upload data sets larger than 50,000 rows.

See [classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) for steps on how to download classification data via FTP and how to upload data files via FTP (including the steps to create an FTP account).

The amount of time required for the system to import these files varies, based on a number of factors. If an uploaded file is present on the FTP server more than three days, work with your organization's supported users to contact Adobe Customer Care. 

A successful import immediately shows the appropriate changes in an export, while the data changes in Analytics may take up to four hours with a browser import and up to 24 hours with an FTP import.

For information on FTP limits and data retention, see [FTP Limits and Data Retention](/help/export/ftp-and-sftp/ftp-limits.md).

## About the `.fin` file for Classifications and Data Sources Uploads {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a Classification or Data Source file (`.tab` or `.txt`), the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a .`.fin` extension. This `.fin` file is a finish file. The purpose of the file is to tell the system that the data file has been completely uploaded to the FTP account. The `.fin` file lets Adobe recognize that you are done with your import.
 
After you submit both the source file and the `.fin` file,  it's important to log out from the FTP site. The reason is that Adobe Analytics uses logout events as a trigger that files are ready for processing. After the import is completed, Adobe removes both files from the FTP location.

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or Classification file without an accompanying `.fin` file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. If no email address is entered in this field, no notification is sent.

If you do upload your file with a `.fin` file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. If no email address was entered, no notification is sent.
