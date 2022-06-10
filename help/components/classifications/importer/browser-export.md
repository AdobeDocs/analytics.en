---
title: Browser export
description: Browser export lets you export your classification data to a tab-delimited file.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
---
# Browser export

Browser export lets you export your classification data to a tab-delimited file.

[!UICONTROL Admin] > [!UICONTROL Classification Importer]

The data set file is a tab-delimited data file (.tab filename extension) that most spreadsheet applications support.

>[!NOTE]
>Browser exports have a 30-column limit.

## Field descriptions

| Element | Descriptions |
| --- | --- |
| Select Report Suite | Select the report suite from which you want to export the report data. |
| Data Set to be classified | From the drop-down menu, select the data set that you want to classify. |
| Select Number of Rows | Specify how many rows of data to export.<ul><li>Select **[!UICONTROL All]** to download all report data (up to 50,000 rows).</li><li>Select **[!UICONTROL Limit Data Rows To]** if you want to specify a specific number of rows to download.</li></ul>If you want to download more than 50,000 data rows, use the FTP download option. | 
| Filter by Date Received | (Optional) Filter data by the date it was received. Specify the date range for which you want to download data. |
| Apply Data Filter | (Optional) Filter the data set by data criteria. You can filter the download to include data rows that include a specific value or data rows with unassigned column (classification) values. Consider the following issues when applying data filters:<ul><li>You can use wild cards when defining the data filter. Use an asterisk to match zero or more characters and a question mark `?` to match exactly one character. Use `?*` to match one or more characters.</li><li>Typically, when applying both types of data filters to a download, only rows that match both rules are downloaded. However, the following exceptions apply:<ul><li>If Rows with empty column = All Columns, then all columns except the column specified in the first rule are checked for emptiness. This exception ensures that the system downloads any row with a column that matches the first rule that also has all other columns empty.</li><li>When downloading data rows based on empty columns, all columns except those specified in the first rule are checked for emptiness.</li><li>If the same column is specified for both filter rules (it is almost impossible to meet both criteria) then only rows that match the first rule are downloaded.</li></ul></ul> |
| Data Filter | (Optional) Filter data by campaign data. You can download data only from active campaigns, or you can select campaigns that began (or ended) in a specific date range.<br>**Important**: This option is not available for report suites enabled for the New Classification Architecture. |
| Export Numeric 2 | You can import Numeric 2 classifications into the system using the importer. Numeric 2 classifications are useful for variables that change over time for different items, such as cost and budget values for the Marketing Channel report. See Numeric 2 Classifications for information about uploading data using numeric 2 classifications. |
| Encoding | Select the character encoding for the data file. The default encoding format is either UTF-8 or ISO-8859-1, based on the encoding that was uploaded for the classification. UTF-8 to UTF-16 converts your UTF-8 encoded classifications to UTF-16 encoding. ISO-8859-1 to UTF-16 converts your ISO-8859-1 encoded classifications to UTF-16 encoding.<br>**Note:** If you select to convert to UTF-16, the source encoding must match the encoding of the original upload or you may get unexpected results. We recommend encoding all uploaded files in UTF-8 without BOM.  |
| Quote Output | Specifies version 2.1 for the classification file. This setting places quotes around special characters to ensure that exports work in Excel when a line break exists in the eVar values. You can identify whether a classification file is version 2.1 by opening the downloaded file. You will see v2.1 in the header. For example: `## SC SiteCatalyst SAINT Import File v:2.1` |

## Export classification data using the browser

1. Click [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Click the [!UICONTROL Browser Export] tab.
1. Specify the data set details.
1. Click [!UICONTROL Export File].
1. Save the data set to your local system.
