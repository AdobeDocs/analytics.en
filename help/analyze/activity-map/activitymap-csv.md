---
description: In Standard Mode, export Analytics data from Activity Map to a Comma Separated Values (CSV) file.
seo-description: In Standard Mode, export Analytics data from Activity Map to a Comma Separated Values (CSV) file.
seo-title: Export to CSV file
solution: Analytics
title: Export to CSV file
topic: Activity map
uuid: dc6c50c0-57f7-45b8-a4cb-2092a21da529
index: y
internal: n
snippet: y
---

# Export to CSV file

In Standard Mode, export Analytics data from Activity Map to a Comma Separated Values (CSV) file.

As a user, you may need to merge link click data with other data sources or perform other analysis (e.g. in Excel). CSV export allows you to obtain all of your Activity Map data for a given page in an easy-to-consume format. It lets you save the analytic data generated for a page to a flat CSV file, allowing you to export the [Page Report](c_page_report_section.md#concept_7E45C185339D4536A824A0F750D38BEA), [Page Flow Report](c_page_flow_section.md#concept_3876744F6C6542C79BA8ACCE4C9F44E0), and [Links on Page](c_Links_report.md#concept_0A8CDEEE91104B2CBEBB55762CCD24D2) data. You can then view as a spreadsheet or text file, or import the data into another system.

Click the Export icon on the Activity Map toolbar.

Activity Map generates the filename based on the Adobe Analytics Page name and appends a date and timestamp to it: Pagename_DateTime.csv. This file will be saved under the default Download directory for the corresponding browser. 

|  Export information  | Description  |
|---|---|
|  Page Metrics Report  | Page metrics data from Analytics, including time spent on page, clicks on page, and total page views.  |
|  Page Details Report  | Page entry and exit information identifying the previous page for internal entries or external references, as well as exit data.  |
|  Links on Page Report  | Link information for a specific page in either Standard or Live modes.  |

Here is an example of a CSV file for a page opened as a spreadsheet. 

![](assets/Activity_Map_CSV_report.png)

