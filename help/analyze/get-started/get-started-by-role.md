---
description: General overview information about Adobe Analytics, including information about the Analytics interface as well as getting started information for administrators, analysts, users, and developers.
title: Get started for administrators, analysts, end users, and developers
feature: Analytics Basics
hide: yes
hidefromtoc: yes
---
# Get started for administrators, analysts, end users, and developers

There are 3 types of Adobe Analytics users in a typical organization: administrators, analysts, and end users. 

Administrators implement and configure Adobe Analytics; analysts set up projects and create analyses using Analysis Workspace, and end users gain actionable insights about their customers, either by creating their own analyses or working with analysts to create them.

The information below outlines how each of these users can get started with Adobe Analytics.

## Get started for administrators

Analytics administrators are responsible for choosing the implementation method most appropriate for their organization.

After Adobe Analytics is implemented, administrators need to perform various configuration tasks to ensure that analysts and end users are getting the full value from Adobe Analytics. Administrators should also regularly monitor their Analytics environment to ensure the system is running efficiently.

### Determine the types of data that should be gathered

Adobe Analytics lets you gather data from multiple channels types and bring it together to deliver meaningful, real-time customer insights. 

Following are some of the supported channels where data can be gathered:

* Mobile phones

* The Internet of Things

* TV

* Voice assistants

* Connected cars

* And more (new supported channels are added regularly)

The [implementation method](https://experienceleague.adobe.com/docs/analytics/implementation/home.html) you choose determines the type of data that can be gathered.

### Implement Adobe Analytics

Various implementation methods are available when implementing Adobe Analytics on your website or mobile app. 

For information about each available method, see [Implement Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html).

| | Implementation methods |
|---------|---------|
| **Websites** | <ul><li>Web SDK extension (recommended)</li><li>Web SDK</li><li>Analytics extension</li><li>Legacy JavaScript</li></ul> |
| **Mobile apps** | <ul><li>Mobile SDK extension (recommended)</li><li>Analytics extension</li></ul> |

{style="table-layout:auto"}

### Configure Adobe Analytics

Analytics administrators should complete the following tasks before making Adobe Analytics available to users in the organization:

|Task | Intended use | More information |
|---------|----------|---------|
| Define administrator roles | Adobe Analytics supports various types of administrators | [Administrator roles in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Define permissions | Analytics administrators need to assign product profiles in the Admin Console for Adobe Analytics, Report Suite Tools, and Analytics Tools. | [Analytics Permissions in the Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en) |
| Set up report suites and define settings for your company | A report suite is a silo of data that Adobe Analytics uses to generate reports.<p>Administrators can also set up [virtual report suites](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en) to further segment data.</p> | <ul><li>[Create a report suite](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Company Settings Overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Import data | Adobe Analytics data sources let you import additional online or offline data for reporting.  | [Data sources overview](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classify data with Classifications | Classifications allow you to classify data to make better use of variables, allowing you to include more content into a single variable. | | 
| Manage components | Use the Data Dictionary and the management areas for each component type to define which components are available in your Analytics implementation, as well as which are approved for your organization.<p>This should be an ongoing activity to ensure that components are being used effectively in your organization. </p>| <ul><li>[Data Dictionary overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=en)</li><li>[Calculated metrics manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Manage segements](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=en)</li><li>[Create custom date ranges](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en)</li></ul> |
| Anomaly detection | Anomaly Detection provides a statistical method to determine how a given metric has changed in relation to previous data. | [Anomaly Detection overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=en) |
| Contribution analysis | Contribution Analysis discovers hidden patterns within your data to explain statistical anomalies and identify correlations behind unexpected customer actions, out-of-bound values, and sudden spikes or dips for selected metrics across convergent audience segments. | [Contribution Analysis overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=en) |
| Analytics segmentation | Lets you build, manage, share, and apply powerful, focused audience segments to your reports using Analytics capabilities, the Adobe Experience Cloud, Adobe Target, and other integrated Adobe products. | [Analytics segmentation](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=en) |
| Publish audiences to Audience Manager | | |
| Integrations | You can surface information from other applications in Adobe Analytics. <p>Following are some common integrations:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=en">Media Analytics</a></li>  | |

{style="table-layout:auto"}

### Monitor Adobe Analytics

Various features are available to help you monitor your Adobe Analytics environment. 

Analytics administrators should be aware of the following features available to help monitor important aspects of your Analytics environment:

|Task | Intended use | More information |
|---------|----------|---------|
| Reporting Activity Manager | The Reporting Activity Manager lets you see the reporting capacity for each report suite in your organization. It provides detailed visibility into reporting consumption and helps you easily diagnose and fix capacity issues during peak reporting times. | [Reporting Activity Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Server call usage |  A server call, also known as a "hit" or an "image request", is an instance in which data is sent to Adobe servers to process. A Server Call Usage dashboard is available that tracks your server call consumption data and compares it to your contractual limit. You can set up alerts to prevent overages. | [Server Call Usage overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Log files | Log files to help you see when users log in, their usage, access, report suites, and Admin changes. | [Logs](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=en) |

{style="table-layout:auto"}

## Get started for Analysts

While anyone in an organization can use Adobe Analytics to gain actionable insights about customer behavior across websites and apps, Adobe Analytics is designed with data analysts in mind. 

Following are key tasks and features that analysts should be familiar with in order to leverage the full power of Adobe Analytics and Analysis Workspace.

| Feature | Intended use | More information |
|---------|----------|---------|
| Build and share projects in Analysis Workspace | Analysis Workspace is a flexible browser tool that allows you to quickly build analyses and share insights. Using the drag-and-drop interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, share and schedule projects with anyone in your organization.<p>Data analysts are often responsible for creating projects in Analysis Workspace for users within their organization.</p><p>After projects are created, analysts share those projects with the [end users](#end-users)(non-analysts) in their organizations who requested the data and help them understand how to interpret it.</p> | <ul><li>[Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul>|
| Attribution | Analysts can customize how dimension items get credit for success events by employing various attribution models and lookback windows in Analysis Workspace.<p>Linear attribution models gives equal credit to every touch point leading up to a conversion, while First Touch gives full credit to the first touch point. Many other attribution models are available, including the Algorithmic model, which uses statistical techniques to dynamically determine the optimal allocation of credit. </p>  | [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md) |
| Anomaly detection | Statistical modeling in Analysis Workspace automatically finds unexpected trends in your data by analyzing metrics and determining a lower bound, upper bound, and expected range of values. When an unexpected spike or drop occurs, the system alerts you in the report. | [Anomaly Detection overview](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Contribution analysis | Use Analysis Workspace to discover hidden patterns within your data to explain statistical anomalies and identify correlations behind unexpected customer actions, out-of-bound values, and sudden spikes or dips for metrics across audience segments. | [Contribution Analysis overview](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Intelligent alerts | Create and manage alerts based on data anomalies and "stacked" alerts that capture multiple metrics in a single alert. | [Intelligent Alerts overview](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Data export | Data Warehouse and Data Feeds allow you to export data to various cloud destinations, such as Google Cloud Platform, Azure RBAC, Azure SAS, and Amazon S3. | [Analytics Export Guide](https://experienceleague.adobe.com/docs/analytics/export/home.html) |
| Activity map | Activity Map is an Adobe Analytics application that is designed to rank link activity using visual overlays and provide a dashboard of real-time analytics to monitor audience engagement of your web pages.<p>Activity Map lets you set up different views to visually identify the acceleration of customer activity, quantify marketing initiatives, and act on audience needs and behaviors.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html) |
| Report Builder | Report Builder is an add-in for Microsoft Excel. Report Builder lets you build customized requests from Adobe Analytics data that are inserted into your Excel worksheets. Requests can dynamically reference cells within your worksheet, and you can update and customize how Report Builder presents the data. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Get started for end users

End users who are not professional analysts can either work with analysts in their organization to leverage the full power of Adobe Analytics and Analysis Workspace, or they can learn the basics of Analysis Workspace in order to start gaining actionable insights about their customers.

### Work with analysts

Typically, users in an organization who are interested in learning more about customer behavior across their various sites are not professional analysts. 

Ideally, these users should work with [analysts](#analysts) within an organization to:

1. Define requirements for the analyses by explaining to the analyst what they hope to learn about customers.

1. Review the analyses to ensure they meet the objectives.

1. Discuss the data gained from the analyses.

1. Modify the analyses as needed over time.

### Create analyses in Analysis Workspace

You don't have to be a data analyst to gain actionable insights from Adobe Analytics.

Some users might find it helpful to work with a data analyst to set up a project in Analysis Workspace and explain how to interpret the data, as described in [Work with analysts](#work-with-analysts); other users might be comfortable building the project and interpreting the data themselves. 

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

For information about how to create analyses in Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

## Get started for developers

[Analytics APIs](https://developer.adobe.com/analytics-apis/docs/2.0/) allow you to directly call Adobe's servers to perform almost any action that you can perform in the user interface. 

You can create reports to explore, get insights, or answer important questions about your data. You can also manage components of Adobe Analytics, such as the creation of segments or calculated metrics. 