---
description: Enable user permissions for API Access, Report Suite Management, Tools and Reports, and Dashboard Items.
keywords: groups;permissions
subtopic: Users and groups
title: Customize Report Suite Tools permissions
feature: Admin Tools
uuid: 3c95d296-ffd0-4971-9c5f-110ddbe042ce
exl-id: 8b776055-66a5-4ada-8d92-391c50a1d4f1
---
# Customize Report Suite Tools permissions

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe will notify you when it is your time to migrate users. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** will be retired.

Enable user permissions for API Access, Report Suite Management, Tools and Reports, and Dashboard Items.

 **[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Report Suite Tools]** > **[!UICONTROL Customize]**

The [!UICONTROL Customize Report Suite Tools] page grants members of a group access to the following items.

![](assets/report-suite-tools.png)

## Field Descriptions

The settings on this page pertain to the report suites selected on the [!UICONTROL Define User Groups] page.

| Element | Description |
|--- |--- |
|**Web Services**||
|These settings enable users to make calls to the Data Warehouse method and pull report suite settings.||
|Data Warehouse|Allows a non-admin user to make calls using the  Data Warehouse methods via the Web Services API. See [Data Warehouse - Developer Documentation](/help/export/data-warehouse/data-warehouse.md)|
|Report Suites (Read)|Allows a non-admin user to use the report suite methods in the API.|
|Report Suites (Write)|Allows a non-admin user to use the report suite methods in the API.|
|**Report Suite Management**||
|These settings grant access to the menu items in  Admin >  Report Suites  >  Edit Settings ([Report Suite Manager](/help/admin/c-manage-report-suites/report-suites-admin.md)).||
|[Traffic Management](/help/admin/c-traffic-management/traffic-management.md)|Grants permission to Traffic Management.|
|[Report Suite Management](/help/admin/c-manage-report-suites/report-suites-admin.md)|Grants permission to manage report suites.|
|[Account Summary](/help/admin/admin/general-acct-settings-admin.md)|Grants permission to edit account settings for a report suite.|
|[URL Filters](/help/admin/admin/internal-url-filter-admin.md)|Grants permission to Internal URL Filters in report suites. Internal URL Filters are used to determine which referrers, or referring pages, are internal to your site.|
|[Custom Calendar](/help/admin/admin/custom-calendar.md)|Grants permission to edit custom calendar.|
|[Paid Search](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)|Paid Search Detection differentiates paid from natural searches in the  Search Engines  and  Search Keywords reports.|
|[Menu Customization](/help/admin/admin/customize-menus.md)|Customize the report menus that a user sees in Reports & Analytics.|
|[Real-Time Report Configuration](/help/admin/admin/realtime/t-realtime-admin.md)|Permissions to set up real-time reports Analytics.|
|[Video Settings](/help/admin/admin/video-management.md)|Permissions to designate a set of Custom Conversion Variables (eVars) and Custom Events for use in tracking and reporting on video.|
|[Video Classifications](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)|Permission to designate a set of Custom Conversion Variables (eVars) and Custom Events for use in tracking and reporting on video.|
|[Traffic Variables](/help/admin/admin/c-traffic-variables/traffic-var.md)|Permission to correlate custom data with specific traffic-related events.|
|[Traffic Classifications](/help/admin/admin/c-traffic-variables/traffic-classifications.md)|Consolidated into Classifications (under Tools and Reports).|
|[Channels](/help/components/c-marketing-channels/analyze-mc.md)|Grants permission to  Marketing Channel settings in  Report Suite Manager >  Edit Settings >  Marketing Channels.|
|[Costs](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/analyze-mc.html)|Enables permission to  Marketing Channels >  Marketing Channel Costs in the  Report Suite Manager.|
|[Conversion Variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)|The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports.|
|[Finding Methods](/help/admin/admin/finding-methods.md)|Lets you identify how various finding methods reports receive credit for conversion success events on your site.|
|[Conversion Classifications](/help/admin/admin/conversion-var-admin/conversion-classifications.md)|Consolidated into Classifications (under Tools and Reports).|
|[Unique Visitor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/unique-visitor-variable/t-unique-visitor-variable.html)|Grants permission to specify the Unique Visitor variable.|
|[Success Events](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html)|Actions that can be tracked, such as product view, checkout, and purchase.|
|[Classification Hierarchies](/help/admin/admin/conversion-var-admin/classification-hierarchies.md)|Consolidated into Classifications (under Tools and Reports).|
|[List Variables](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html)|Also known as List Var. Similar to how List Props function, List Vars allow multiple values within the same image request.|
|[Default Metrics](/help/admin/admin/default-metrics.md)|Reports & Analytics displays a default set of metrics in all conversion reports, unless a user selects a custom set of metrics. The selected metrics display for all users of the associated report suite.|
|[Processing Rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html)|Grants access to Processing Rules, which simplify data collection and manage content as it is sent to reports.|
|**Tools and Reports**||
|[Anomaly Detection](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)|Grants permission to  Anomaly Detection, which provides a statistical method to determine how a given metric has changed in relation to previous data.|
|[Channel Report](/help/components/c-marketing-channels/analyze-mc.md)|Grants permission to  Marketing Channel reports, found in  Reports >  Marketing Channel Reports.|
|[Real-Time Report](/help/admin/admin/realtime/t-realtime-admin.md)|Grants access to the  Real-Time Report.|
|[Bot Pages](/help/admin/admin/bot-removal/bot-rules.md)|**Note: Bot Pages are for specific Reports & Analytics reports, not for managing bot rules. Currently, there is no permission to allow editing bot rules.** Bot Rules let you remove traffic that is generated by known spiders and bots from your report suite. Removing bot traffic can provide a more accurate measurement of user activity on your website.|
|[Bots](/help/admin/admin/bot-removal/bot-rules.md)|**Note: Bots are for specific Reports & Analytics reports, not for managing bot rules. Currently, there is no permission to allow editing bot rules.** Bots let you remove traffic that is generated by known spiders and bots from your report suite. Removing bot traffic can provide a more accurate measurement of user activity on your website.|
|[Custom Data Warehouse Report](/help/export/data-warehouse/data-warehouse.md)|Data warehouse refers to the copy of raw, unprocessed data for storage and custom reports, which you can run by filtering the data. You can request reports to display advanced data relationships from raw data based on your unique questions.|
|Daily Return Visits|(Legacy) Report that displays the number of visitors to your website more than once on a given day. A day is defined as the last 24-hour period.|
|[Data Sources Manager](/help/admin/admin/data-sources.md)|The Data Sources feature allows you to import data to Analytics from offline sources.|
|[Exclude By IP Address](/help/admin/admin/exclude-ip.md)|You can exclude data from specific IP addresses, such as internal website activities, site testing and employee usage, from your reports.|
|Legacy ClickMap|Grants access to the menu for the legacy ClickMap overlay tool.|
|Legacy Clickmap Installation|Grants installation rights to the legacy ClickMap tool.|
|Return Visits|A report showing the number of visits where visit number is greater than 1. The Return Visits Report includes non-cookied visitors.|
|[Classifications Importer](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) / Exporter and [Rule Builder](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html)|Consolidated into Classifications (see below).|
|Data Feeds Manager|Grants rights to the Analytics Data Feed.|
|Classifications|Combines the following permissions: 'Traffic Classifications', 'Video Classifications', 'Conversion Classifications', 'Classification Hierarchies', 'Classifications Manager' and 'Classifications Importer/Exporter & Rule Builder'.  Note:  With this permission, users edit classifications for all report suites, not just the selected one/s.|
|[Contribution Analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html)|Grants rights to use Contribution Analysis in Analysis Workspace.|
|**Dashboard Items**||
|The settings in Dashboard Items enables access to [reportlets](https://experienceleague.adobe.com/docs/analytics/admin/server-call-usage/server-call-usage-dashboard.html) in Reports & Analytics:, My Recommended Reports, Company Summary Reportlet, Image, KPI/Gauge Reportlet, Report Suite Totals, Text, Reportlet, Usage Summary Reportlet, and Web Resources||
|**Other**||
|Social|Controls access to the  Social Management menu in the  Report Suite Manager.|
