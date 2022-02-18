---
title: Classification importer processing time
description: Understand the time frame Adobe processes classification files, and how to minimize processing time.
feature: Classifications
exl-id: 6b8b87f1-5dbc-46b8-9912-0e3086ff4b2a
---
# Classification importer processing time

Processing time for a classification file varies with the size of the file and total number of files Adobe processes. Classifications typically don't take longer than 72 hours. However, periods of heavy classification use across organizations that use Adobe Analytics can cause files to take longer than 72 hours. Adobe sees heavy classification use in months leading up to the holiday season.

If you want to see if a classification file is finished, do the following:

1. Log in to Adobe Analytics, then navigate to **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Select the report suite and data set in question.
3. If processing is not yet complete, either one of the following messages appear:
   
   * ![Notice](assets/icon_notice_notice.gif) The selected report has a classification import that is processing.
   * ![Notice](assets/icon_notice_notice.gif) The selected report has classification data that hasn't propagated to all servers yet.

If you want to minimize classification import time, Adobe strongly recommends adhering to the following guidelines:

* **Use the classification rule builder when possible**: The classification rule builder processes data differently than the traditional classification importer. If classification data follows specific patterns, using this capability is highly recommended.
* **Upload only changed rows**: This practice greatly reduces the amount of time it takes to process classification files, since it doesn't sort through unchanged rows. Adobe highly recommends only uploading changed rows.
* **Plan ahead**: Start uploading classification data as soon as possible, especially if this data is used during the holiday season.
* **Combine classification files where possible**: If a single variable has multiple classifications, upload a single file with all applicable classifications. Avoid uploading multiple classifications for the same variable.
* **Avoid uploading files over 500 MB**: If dealing with large amounts of classification data, Adobe recommends splitting files into 100 MB-500 MB files.
* **Avoid uploading large quantities of files to FTP**: If you plan to upload the same files to many report suites through FTP, limit the number of files uploaded at a time. Adobe recommends the number of files multiplied by the number of applicable report suites being less than 1000. If uploading 100 files to 100 report suites is required, then the total number of files is 10,000. Rather than uploading all 100 files at once, break it into 10 groups of 10 files at a time.
* **Upload small files via the browser importer**: If you have a file that is less than 1 MB (less than 50,000 rows), Adobe recommends using the browser importer. Browser imports are almost always faster than FTP imports.
