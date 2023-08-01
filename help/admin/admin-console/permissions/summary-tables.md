---
title: Adobe Analytics Permissions - summary tables
description: Tables that summarize the available Adobe Analytics permissions in Adobe Admin Console.
exl-id: f1abbdb7-0f76-4d9b-a3ca-b12fa3cecb50
feature: Admin Tools
---
# Analytics Permissions in the Admin Console

Use the following summary tables to identify Adobe Analytics permissions in the Adobe Admin Console, by logical groupings.

## Report Suite Tools

| Report Suite Tool | Administration | Access Controls | Reports-only Features | Deprecated | Description |
| --- | --- | --- | --- | --- | --- |
| Account Summary | x |  |  |  | Grants access to General > General Account Settings in the Report Suite Manager. |
| Channels | x |  |  |  | Grants access to Marketing Channels, including Marketing Channel Manager, Marketing Channel Processing Rules, and Marketing Channel Expiration in the Report Suite Manager. |
| Classifications | x |  |  |  | Grants access to all classification settings in the Report Suite Manager. This permission item includes: |
| Conversion Variables | x |  |  |  | Grants access to Conversion > Conversion Variables in the Report Suite Manager. |
| Costs | x |  |  |  | Grants access to Marketing Channels > Marketing Channel Costs in the Report Suite Manager. |
| Custom Calendar | x |  |  |  | Grants access to General > Customize Calendar in the Report Suite Manager. |
| Data Feeds Manager | x |  |  |  | Grants access to Admin > Data feeds in the Analytics top navigation. |
| Data Repair API | x |  |  |  | Grants access to the Data Repair API |
| Data Sources Manager  | x |  |  |  | Grants access to Admin > All admin > Data sources in the Analytics top navigation. Requires the permission item 'Report Suite Mgmt'. |
| Default Metrics | x |  |  |  | Grants access to Individual Report Suite Settings > Default Metrics in the Report Suite Manager.      |
| Exclude By IP Address | x |  |  |  | Grants access to Admin > Exclude By IP in the Analytics top navigation. |
| Finding Methods | x |  |  |  | Grants access to Conversion > Finding Methods in the Report Suite Manager. |
| List Variables | x |  |  |  | Grants access to Conversion > List Variables in the Report Suite Manager. |
| Menu Customization | x |  |  |  | Grants access to General > Customize Menus in the Report Suite Manager. |
| Paid Search | x |  |  |  | Grants access to General > Paid Search Detection in the Report Suite Manager. |
| Processing Rules | x |  |  |  | Grants access to General > Processing Rules and General > Bot Rules in the Report Suite Manager.    |
| Real Time Report Configuration | x |  |  |  | Grants access to Real-Time in the Report Suite Manager. Use the permission item 'RealTime Report' to grant access to the report itself. |
| Report Suite Mgmt | x |  |  |  | Grants access to the Report Suite Manager, but does not allow any changes. |
| Success Events | x |  |  |  | Grants access to Conversion > Success Events in the Report Suite Manager. |
| Traffic Variables | x |  |  |  | Grants access to Traffic > Traffic Variables in the Report Suite Manager. |
| Unique Visitor | x |  |  |  | Grants access to Conversion > Unique Visitor Variable. Not typically used in modern implementations. |
| URL Filters | x |  |  |  | Grants access to General > Internal URL filters in the Report Suite Manager. |
| Anomaly Detection |  | x |  |  | Grants access to Anomaly Detection in Analysis Workspace. |
| Contribution Analysis |  | x  |  |  | Grants access to the right-click menu 'Run Contribution Analysis' in Analysis Workspace. |
| Custom Data Warehouse Report |  | x |  |  | Grants access to Tools > Data Warehouse in the Analytics top navigation. |
| Bot Pages |  |  | x |  | Grants access to Site Metrics > Bots > Bot Pages report in Reports & Analytics. |
| Bots |  |  | x |  | Grants access to Site Metrics > Bots > Bots report in Reports & Analytics. |
| Channel Report |  |  | x |  | Grants access to the Marketing Channels > Channel Overview Report in Reports & Analytics. |
| Daily Return Visits |  |  | x |  | Grants access to Visitor Retention > Daily Return Visits in Reports & Analytics. |
| My Recommended Reports |  |  | x |  | Grants access to Site Metrics > My Recommended Reports in Reports & Analytics. |
| RealTime Report |  |  | x |  | Grants access to Site Metrics > Real-Time in Reports & Analytics. Use the permission item 'Real Time Report Configuration' to grant access to set up this report. |
| Return Visits |  |  | x |  | Grants access to Visitor Retention > Return Visits in Reports & Analytics. |
| Advertising Analytics Configuration |  |  |  | x | Not used. |
| Company Summary Reportlet |  |  |  | x | Not used. |
| Data Warehouse |  |  |  | x | Not used. Use 'Custom Data Warehouse Report' instead. |
| Image |  |  |  | x | Not used. |
| KPI/Gauge Reportlet |  |  |  | x | Not used. |
| Last 100 Visitors |  |  |  | x | Not used. |
| Legacy ClickMap |  |  |  | x | Not used. Use Activity Map under Analytics Tools instead. |
| Legacy Clickmap Installation |  |  |  | x | Not used. Use Activity Map under Analytics Tools instead. |
| Mobile App Overview Report |  |  |  | x | Not used. |
| Report Suite Totals |  |  |  | x | Not used. |
| Report Suites (Read) |  |  |  | x | Not used. |
| Report Suites (Write) |  |  |  | x | Not used. |
| Site Catalyst |  |  |  | x | Not used. Use 'Analysis Workspace Access' instead. |
| Social |  |  |  | x | Not used. |
| Text Reportlet |  |  |   | x | Not used. |
| Traffic Management |  |  |  | x | Not used. |
| Usage Summary Reportlet |  |  |  | x | Not used. |
| Video Settings |  |  |  | x | Not used. |
| Web Resources |  |  |  | x | Not used. |

## Analytics Tools

| Analytics Tool | Administration | Access Controls | Reports-only Features | Deprecated | Description |
| --- | --- | --- | --- | --- | --- |
| Code Manager | x |  |  |  | Kept around for legacy purposes. Grants access to Admin > All admin > Code manager. In most cases, use the libraries included in the Adobe Analytics extension within Adobe Experience Platform Data Collection instead. |
| Code Manager - Web Services | x |  |  |  | Grants access to the Code Manager via the 1.4 API. |
| Hide Report Suites | x |  |  |  | Grants access to Admin > All admin > Company settings > Hide Report Suites. Grants the ability to hide any report suite in the organization, regardless of their report suite access. |
| Integrations (Create) | x |  |  |  | Grants access to Admin > All admin > Data connectors, and allows the user to create data connectors. |
| Integrations (Delete) | x |  |  |  | Grants access to Admin > All admin > Data connectors, and allows the user to delete data connectors. |
| Integrations (Update) | x |  |  |  | Grants access to Admin > All admin > Data connectors, and allows the user to modify existing connector configurations. |
| Logs | x |  |  |  | Grants access to Admin > All admin > Logs. |
| Logs - Web Services | x |  |  |  | Grants access to pull logs via the 1.4 API. |
| Pending Actions | x |  |  |  | Grants access to Admin > All admin > Company settings > Pending Actions.  |
| Security  | x |  |  |  | Grants access to Admin > All admin > Company settings > Security Manager. |
| Server Call Usage | x |  |  |  | Grants access to Admin > Server call usage. |
| Support | x |  |  |  | Grants access to Admin > All admin > Company settings > Support Information. |
| Traffic Management | x |  |  |  | Grants access to Admin > All admin > Traffic management.  |
| Web Services  | x |  |  |  | Grants access to Admin > All admin > Company settings > Web Services.  |
| Share Project Links With Anyone | x |  |  |  |  Grants access to users to Share with anyone under a Workspace project -> Share -> Share with anyone. |
| Activity Map |  | x |  |  | Grants access to Tools > Activity Map. Allows the user to use the Activity Map extension. |
| Ad Hoc Analysis License Users |  | x |  |  | Ad Hoc Analysis has been end-of-lifed. [More info](https://spark.adobe.com/page/S9Bhp66VJ2fEn/). |
| Analysis Workspace Access |  | x |  |  | Grants access to Analysis Workspace. Users must belong to either this group (preferred) or Reports & Analytics Access to use Adobe Analytics. |
| Analysis Workspace: Save As Template |  | x |  |  | Grants access to Project > Save As Template within Analysis Workspace. |
| Calculated Metric Creation |  | x |  |  | Grants the ability to create calculated metrics across all Analytics capabilities. |
| Labs Access |  | x |  |  | Grants access to Labs. |
| Report Builder |  | x |  |  | Enables the download button under Tools > Report Builder, and allows the user to authenticate within Microsoft Excel. |
| Segment Creation |  | x |  |  | Grants the ability to create and share segments across all Analytics capabilities. |
| Segment Publishing  |  | x |  |  | Grants the ability to make a segment an Experience Cloud audience when creating or editing a segment. |
| Web Service Access |  | x |  |  | Grants the ability to use the API, including authentication with third-party sites and sending API calls. |
| Current Data |  |  | x |  | Enables the option to see current data in Reports & Analytics reports. |
| Reports & Analytics Access |  |  | x |  | Grants access to Reports & Analytics. Users must belong to either this group or Analysis Workspace Access (preferred) to use Adobe Analytics. |
| Advertising Analytics Management |  |  |  | x | Not used. |
| Co-Branding |  |  |  | x | No longer used. Grants access to Admin > All admin > Company settings > Co-Branding. |
| Excel License Users |  |  |  | x | Not used. |
| Mobile App Admin |  |  |  | x | Not used. |
| Permission Management |  |  |  | x | No longer used. Grants access to the legacy user management interface under Admin > All admin > User management. |
| Permissions (Read) - Web Services |  |  |  | x | No longer used. Allows the user to view legacy Analytics permissions using the Admin API. Use the Adobe Admin Console instead. |
| Permissions (Write) - Web Services |  |  |  | x | No longer used. Allows the user to edit legacy Analytics permissions using the Admin API. Use the Adobe Admin Console instead. |
| Preferences |  |  |  | x | Not used. |
| Single Sign-On |  |  |  | x | No longer used. Grants access to the deprecated Single Sign-On Service. |
