---
title: What is the new Adobe Report Builder?
description: Describes the new Report Builder functionality
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
---
# About the new Adobe Report Builder

The new Javascript Report Builder Add-in that was initially available only in Customer Journey Analytics is now also being introduced in Adobe Analytics. This new version has several benefits:

- Find insights in Excel faster and easier with improved workflows for data block creation and management, including greater data block flexibility
- Cross-platform: no more logging into your VM to use Report Builder as we now support PC, Mac, and Excel Online
- Less time waiting for data blocks to return, thanks to API 2.0 upgrade
- Enhanced speed

Users of the Legacy Report Builder tool can [convert legacy workbooks](/help/analyze/report-builder/convert-workbooks.md) to the new Report Builder.

Report Builder allows you to easily create, edit, and refresh custom reports using Adobe Analytics data. With Report Builder's simple and flexible drag-and-drop UI, you can create complex data queries and custom reports from Adobe Analytics data, all within Excel.

With Report Builder, you can:

- Reference existing worksheet cells to get the perfect row order, date range, or filter
- Create custom dates using calendar, cell references, or date math
- Design your tables and visualizations with familiar Excel formatting tools

## Using Legacy Report Builder and the new Report Builder side by side

You can still use both versions of Report Builder, with the following caveats:

- Do not use both Report Builder versions on the same file at the same time. They are mutually exclusive.
- You can still use Legacy Report Builder on legacy workbooks and the new Report Builder on new workbooks.
- In addition, you can automatically [convert legacy workbooks](/help/analyze/report-builder/convert-workbooks.md) to the new Report Builder format. Before doing so, duplicate and rename the file.

## Legacy Report Builder features not supported in the New Report Builder

When comparing the functionality of Legacy Report Builder to the new Report Builder Add-in, some legacy functionality is no longer available:

- Real-time requests

- Path/Fallout reporting

- FTP option for scheduled reports

- Visitors metrics. The following metrics will all be converted to "unique visitors", even though the reporting result may not be an exact match: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly`, and `visitorsyearly`. This also applies to `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly`, and `mobilevisitorsyearly`.

## Common use cases

- **Data Extraction**: Adobe Report Builder allows you to extract data from Adobe Analytics into Excel. You can create custom reports and queries to retrieve specific data points that are relevant to your analysis. 

- **Custom Reporting**: You can design and format custom reports in Excel to suit your specific reporting needs. This is especially useful for tailoring reports to different stakeholders. 

- **Ad-Hoc Analysis**: Users can quickly generate ad-hoc reports to answer specific questions or explore data trends without having to go through a lengthy report creation process. 

- **Dashboarding**: Data extracted from CJA can be used to create Excel-based dashboards and visualizations for a high-level overview of key performance indicators (KPIs). 

- **Sharing Insights**: You can share Excel reports and insights with team members or stakeholders who might not have direct access to CJA.

## Overview video

>[!IMPORTANT]
>
>This overview video shows the Report Builder user interface in Customer Journey Analytics. Some of the user interface and terminology differ. Otherwise, the user experience is identical.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Report Builder overview](https://video.tv.adobe.com/v/337569?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

You can download Report Builder from the [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).
