---
title: Classification data export via FTP
description: FTP export provides more flexibility with data set downloads, including downloading data from multiple report suites and downloading data set files larger than 50,000 data rows
feature: Classifications
exl-id: 6f97f0b2-1a04-407f-9df9-8715da52037d
TQID: https://experienceleague.adobe.com/KKnG0DlET8t0Lp5kecZ7C-d9zyUx71nQ6FI8NleDirU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
# FTP export (legacy)

{{classification-importer-deprecation}}

The FTP option provides more flexibility in downloading data sets, including the ability to download data from multiple report suites and to download data set files larger than 50,000 data rows. Before downloading classification data via FTP, create an FTP account. 

Consider the following issues when applying data filters:

* You can use wild cards when defining the data filter. Use an asterisk `*` to match zero or more characters and a question mark `?` to match exactly one character. Use `?*` to match one or more characters.
* Typically, when applying both types of data filters to a download, only rows that match both rules are downloaded. However, the following exceptions apply:
   * If Rows with empty column = All Columns, then all columns except the column specified in the first rule are checked for emptiness. This exception ensures that the tool downloads any row with a column that matches the first rule that also has all other columns empty.
   * When downloading data rows based on empty columns, all columns except those specified in the first rule are checked for emptiness.
   * If the same column is specified for both filter rules (it is almost impossible to meet both criteria) then only rows that match the first rule are downloaded.
   * FTP exports have a 30-column limit.

## Export classifications using FTP

These steps describe how to export (download) classifications from Adobe Analytics using FTP.

1. Create an FTP account.
1. Go to [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Click the **[!UICONTROL FTP Import]** tab.
1. Configure fields for the FTP Export.
1. Click **[!UICONTROL Export File]**.
1. Save the data set to your local system.

## Field descriptions

| Element | Descriptions |
| --- | --- |
| [!UICONTROL Select Report Suite] | Select the report suite from which you want to export the report data. |
| [!UICONTROL Data Set to be classified] | From the drop-down menu, select the data set that you want to classify. |
| [!UICONTROL Select Number of Rows] | Specify how many rows of data to export.<ul><li>Select **[!UICONTROL All]** to download all report data.</li><li>Select **[!UICONTROL Limit Data Rows To]** if you want to specify a specific number of rows to download.</li></ul> |
| [!UICONTROL Filter by Date Received] | (Optional) Filter data by the date it was received. Specify the date range for which you want to download data. |
| [!UICONTROL Apply Data Filter] | (Optional) Filter the data set by data criteria. You can filter the download to include data rows that include a specific value or data rows with unassigned column (classification) values. |
| [!UICONTROL Date Filter] | (Optional) Filter data by campaign data.You can download data only from active campaigns, or select campaigns that begin (or end) in a specific date range. |
| [!UICONTROL Export Numeric 2] | You can import Numeric 2 classifications into the system using the importer. Numeric 2 classifications are useful for variables that change over time for different items, such as cost and budget values for the Marketing Channel report. |
| [!UICONTROL FTP Account] | Specify the FTP server information where you want Adobe to download the data file, including host name and port, path to the destination directory, username, and password. |
| [!UICONTROL Notification] | Specify the email address to receive notifications about this FTP download. |
| [!UICONTROL Encoding] | Select the character encoding for the data file. The default encoding format is either UTF-8 or ISO-8859-1, based on the encoding that was uploaded for the classification. UTF-8 to UTF-16 converts your UTF-8 encoded classifications to UTF-16 encoding. ISO-8859-1 to UTF-16 converts your ISO-8859-1 encoded classifications to UTF-16 encoding.<br>**Note:** If you select to convert to UTF-16, the source encoding must match the encoding of the original upload or you may get unexpected results. We recommend encoding all uploaded files in UTF-8 without BOM. |
