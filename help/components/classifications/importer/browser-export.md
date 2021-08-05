---
title: Browser export
description: Browser export lets you export your classification data to a tab-delimited file.
---

# Browser export

Browser export lets you export your classification data to a tab-delimited file.

Admin > Classification Importer

The data set file is a tab-delimited data file (.tab filename extension) that most spreadsheet applications support.

>[!NOTE]
>Browser exports have a 30-column limit.

## Field descriptions

| Element | Descriptions |
| --- | --- |
| Select Report Suite | Select the report suite from which you want to export the report data. |
| Data Set to be classified | From the drop-down menu, select the data set that you want to classify. |
| Select Number of Rows | Specify how many rows of data to export.<ul><li>Select **[!UICONTROL All]** to download all report data (up to 50,000 rows).</li><li>Select **[!UICONTROL Limit Data Rows To]** if you want to specify a specific number of rows to download.</li></ul>If you want to download more than 50,000 data rows, use the [FTP download]() option. | 
| Filter by Date Received | (Optional) Filter data by the date it was received. Specify the date range for which you want to download data. |
| Apply Data Filter | (Optional) Filter the data set by data criteria. You can filter the download to include
data rows that include a specific value or data rows with unassigned column (classification) values. Consider the following issues when applying data filters:<ul><li>You can use wild cards when defining the data filter. Use an asterisk to match zero or more characters and a question mark (?) to match exactly one character. Use ?* to match one or more characters.</li><li>Typically, when applying both types of data filters to a download, only rows that match both rules are downloaded. However, the following exceptions apply:<ul><li>If Rows with empty column = All Columns, then all columns except the column specified in the first rule are checked for emptiness. This exception ensures that the system downloads any row with a column that matches the first rule
that also has all other columns empty.</li><li>When downloading data rows based on empty columns, all columns except those specified in the first rule are checked for emptiness.</li><li>If the same column is specified for both filter rules (it is almost impossible to meet both criteria) then only rows that match the first rule are downloaded.</li></ul></ul> |
| Data Filter | (Optional) Filter data by campaign data. You can download data only from active campaigns, or you can select campaigns that began (or ended) in a specific date
range.<br>**Important**: This option is not available for report suites enabled for the New Classification Architecture.|

