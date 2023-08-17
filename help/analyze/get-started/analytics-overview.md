---
description: General overview information about Adobe Analytics
title: Adobe Analytics overview
feature: Analytics Basics
hide: yes
hidefromtoc: yes
---
# Adobe Analytics overview

Adobe Analytics enables organizations to gather data and gain actionable insights from any digital customer interaction. With in-depth analysis, versatile reporting, and predictive intelligence, organizations get the insightful foundation they need to build better experiences for their customers. 

## Key benefits

Following are some of the key ways that Adobe Analytics helps organizations gain critical insights in order to better serve their customers.

For additional details about the benefits that Adobe Analytics provides, see the [Adobe Analytics product page](https://business.adobe.com/products/analytics/adobe-analytics.html).

### Web analytics

Adobe Analytics provides the following complex segmentation and predictive tools for analyzing website traffic:

* [Ad hoc analysis in Analysis Workspace](/help/analyze/analysis-workspace/home.md)

* [Flow analysis](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [Advanced segmentation](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### Marketing analytics

Adobe Analytics helps organizations understand where customers interact with their brands, which channels customers prefer, and which experiences resonate with them. 

The following key features in Adobe Analytics provide these marketing capabilities:

* Multichannel data collection

* [Offline data integration](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Ad hoc analysis in Analysis Workspace](/help/analyze/analysis-workspace/home.md)

### Attribution

Attribution lets organizations see how different interactions throughout the customer journey affect conversion. In addition to providing more traditional attribution options, such as Linear or First Touch models, Attribution in Adobe Analytics also uses machine learning and advanced statistical models to understand the precise impact of every touch.

For more information, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).


### Predictive analytics

Predictive analytics uses machine learning and advanced statistical modeling to analyze customer data, find patterns, and predict future behavior such as churn or a likelihood to convert. It allows data analysts to take advantage of huge data sets that might otherwise be wasted.

The following key features in Adobe Analytics provide these predictive capabilities:

* [Anomaly detection](#anomaly-detection)

* [Contribution analysis](#contribution-analysis)

* [Intelligent alerts](#intelligent-alerts)

## Prerequisites for using Adobe Analytics

Before you can use Adobe Analytics, you must have:

* A valid Adobe Analytics license

  Adobe Analytics requires a site license. Contact your Adobe Account rep for more information. <!--is this phrased correctly? Is this important? -->

* A supported browser

  Each user accessing Adobe Analytics must use a supported browser. For more information, see the [Adobe Analytics system requirements](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Understand the Analytics interface 

The Adobe Analytics interface consists of the following main areas:

### Workspace tab

The [!UICONTROL Workspace] tab shows shows the [!UICONTROL Projects] area by default, which displays the Company folder, any personal folders you created, your projects, and Mobile scorecards. 

1. In Adobe Analytics, select the [!UICONTROL **Workspace**] tab.

   ![Workspace tab](assets/landing-all2.png)

For more information about the features and functions available on the [!UICONTROL Workspace] tab, see [Adobe Analytics Landing page](/help/analyze/landing.md).

### Reports tab

Effective December 31, 2023, Adobe intends to discontinue Reports & Analytics and its accompanying reports and features. 

Instead, use the [!UICONTROL **Reports**] area in the left rail on the [!UICONTROL **Workspace**] tab. For more information, see *Navigate the Reports tab* in [Adobe Analytics Landing page](/help/analyze/landing.md).

### Components tab

The [!UICONTROL Components] tab includes features that help you fine tune and empower your analysis of data.

1. In Adobe Analytics, select the [!UICONTROL **Components**] tab, then select [!UICONTROL **All components**].

   ![Workspace tab](assets/components-tab.png)

2. Select any of the following product features to configure it: 

   
   | Product feature | Function | More information |
   |---------|----------|----------|
   | Segments | Adobe Analytics lets you build, manage, share, and apply powerful, focused audience segments to your reports using Analytics capabilities, the Adobe Experience Cloud, Adobe Target, and other integrated Adobe products. | [Analytics segmentation](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=en) |
   | Calculated metrics | Calculated and Advanced Calculated (or Derived) metrics are custom metrics that you can create from existing metrics.  They allow marketers, product managers, and analysts to ask questions of the data without having to change the Analytics implementation.  | [Calculated and Advanced Calculated (Derived) metrics](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=en) |
   | Date ranges | Analysis Workspace includes a list of default date ranges that users can use when building analyses. In addition, you can create custom date ranges and make them available to users in Analysis Workspace. | [Create custom date ranges](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | Virtual report suites | Virtual report suites segment your Adobe Analytics data so you can control access to each segment. | [Virtual report suites overview](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en) |
   | Alerts | Intelligent Alerts allow for more granular control over alerts and integrates anomaly detection with the alert system. | [Intelligent alerts](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | Targets | Targets let you measure your website performance and track progress against target goals. When you create targets, you select which attribute metrics or eVars you want to measure or you can choose to measure your entire site against your selected metric. <p>Targets are part of Reports & Analytics. Read more about the Reports & Analytics [End-of-life announcement](https://express.adobe.com/page/6WnF8JK6IRDhf/).</p> | [Targets](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | Calendar events | For reports trended over time, calendar events allow you to graphically display events and see whether campaigns or other events have affected your site traffic, revenue, or any other metric. | [Calendar events](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | Annotations | Annotations in Workspace enable you to effectively communicate contextual data nuances and insights to your organization. They let you tie calendar events to specific dimensions and metrics.  | [Manage annotations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | Classification sets | Classification sets provide a single interface to manage classifications and rules. <p>A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports. You establish a relationship between a variable value and metadata related to that value. Classifications can be used on most custom dimensions, such as Tracking code, props, and eVars.</p>  | [Classification sets overview](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=en) |
   | Locations | In order to import Adobe Analytics classification data from a cloud destination, you first need to add and configure the location where you want the classification data to be collected. You can create, edit, or delete locations. | [Locations manager](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | Scheduled projects | When managing scheduled projects, you can edit and delete recurring project schedules; search for a schedule in the search bar or by using the filter options in the left rail; and filter by tag, approved schedules, owners and more. | [Scheduled projects](/help/components/scheduled-projects-manager.md) |
   | Bookmarks | Bookmarks give you access to the reports that you use the most. The bookmarks you create are added to the Experience Cloud and are available in integrated capabilities like data connectors. <p>Bookmarks are part of Reports & Analytics. Read more about the Reports & Analytics [End-of-life announcement](https://express.adobe.com/page/6WnF8JK6IRDhf/). | [Bookmark manager](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | Dashboards | Dashboards are created to visualize metrics and provide interactive analytic capability with data. By clicking on items within a dashboard, you can quickly and easily segment the data to derive information from your analysis. <p>Dashboards are part of Data Workbench. Read more about the Data Workbench [End-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [Dashboard manager](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | Scheduled reports | Admin-level users can see and manage scheduled reports across the organization. | [Scheduled reports queue](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | Report settings | These settings refer to legacy Adobe Analytics products, which excludes Analysis Workspace and its related components. o make adjustments to Analysis Workspace settings, go to Components > Preferences.  |  |
   | Preferences | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create. Existing projects and panels are not affected. | [Preferences](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### Tools tab

<!-- The Tools tab ... -->

1. In Adobe Analytics, select the [!UICONTROL **Tools**] tab, then select [!UICONTROL **All tools**].

   ![Workspace tab](assets/tools-tab.png)

2. Select any of the following product features to configure it:

   | Product feature | Function | More information |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse refers to the copy of Analytics data for storage and custom reports, which you can run by filtering the data. <p>The Request Manager lets you view, duplicate, and re-prioritize requests.</p> | [Manage Data Warehouse requests](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map is designed to rank link activity using visual overlays and provide a dashboard of real-time analytics to monitor audience engagement of your web pages. It lets you set up different views to visually identify the acceleration of customer activity, quantify marketing initiatives, and act on audience needs and behaviors. | [Activity Map overview](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=en) |
   | Recommendations Classic | Recommendations is an Adobe Target feature that automatically display products, services, or content that might interest your visitors based on previous user activity, preferences, or other criteria.  | [Recommendations](https://experienceleague.adobe.com/docs/target/using/recommendations/recommendations.html?lang=en) |
   | Search & Promote |  |  |
   | Mobile Services |  |  |
   | Analytics dashboards (mobile app) | The Adobe Analytics dashboards app delivers anytime, anywhere insights from Adobe Analytics. Through the app, users can view intuitive Scorecards that you create using the Adobe Analytics desktop UI.  | The Adobe Analytics dashboards app in the iOS App Store or Google Play store |
   | Report Builder | Adobe Report Builder is an add-in for Microsoft Excel. It lets you build customized requests from Adobe Analytics data, which you can insert into your Excel worksheets. Requests can dynamically reference cells within your worksheet, and you can update and customize how Report Builder presents the data. |[What is Report Builder?](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=en) |

   {style="table-layout:auto"}

### Admin tab

The Admin tab includes features and configuration options to administer Adobe Analytics.

1. In Adobe Analytics, select the [!UICONTROL **Admin**] tab, then select [!UICONTROL **All admin**].

   ![Workspace tab](assets/admin-tab.png)

2. Select any of the following product features to configure it:   

   | Product feature | Function | More information |
   |---------|----------|----------|
   | Analytics users & assets | While most user and product management functions are now available only in the [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html), the administrative functions of transferring assets from one user to another, as well as setting an expiration date for a user account, are available only from the Adobe Analytics Admin area. | [Transfer user assets or set account expirations](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) |
   | User ID migration | The Analytics user ID migration enables administrators to easily migrate user accounts in Analytics User Management to the Adobe Admin Console.  | [Analytics User Migration to the Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/migrate-users/c-migration-tool.html?lang=en) |
   | User management home (legacy) | User and product management has moved to the Adobe Admin Console. Use the Adobe Admin Console to get started managing user permissions for Adobe Analytics users. | [Analytics in the Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=en) |
   | Groups (legacy) | Group management has moved to the Adobe Admin Console. Use the Adobe Admin Console to get started managing groups for Adobe Analytics. | [Analytics in the Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=en) |
   | Report suite access | The method for granting access to report suites has moved to the Adobe Admin Console. Use the Adobe Admin Console to grant report suite access for Adobe Analytics users. | [Product profile permissions for Report Suite Tools](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html?lang=en) |
   | Admin tools home |  |  |
   | Report suites |  |  |
   | Analytics users & assets |  |  |
   | User ID migration |  |  |
   | Classification importer |  |  |
   | Classification rule builder |  |  |
   | Data sources |  |  |
   | Code manager | Code manager lets you download data collection code for web and mobile platforms | [Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=en) |
   | Traffic management |  |  |
   | Server call usage |  |  |
   | Logs | Log files to help you see when users log in, their usage, access, report suites, and Admin changes. | [Logs](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=en) |
   | Advertising Analytics |  |  |
   | Data feeds | Data feeds are a powerful way to get raw data out of Adobe Analytics. This raw data can be used in other platforms outside of Adobe to use at your organization's discretion.  | [Analytics Data Feed overview](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) |
   | Exclude by IP |  |  |
   | Publishing widgets |  |  |
   | Reporting Activity Manager |  |  |
   | Data Governance Privacy Labeling |  |  |
   | Company settings home |  |  |
   | Security manager |  |  |
   | Support information |  |  |
   | Web services |  |  |
   | Report Builder reports |  |  |
   | Single sign-on service |  |  |
   | Co-brand the Adobe Experience Cloud |  |  |
   | Hide report suites |  |  |

   {style="table-layout:auto"}

### Analysis Workspace

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

The following image and accompanying table explain some of the main areas in Analysis Workspace.

For a more detailed overview of Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

![Analysis Workspace overview](assets/analysis-workspace-overvew.png)

| Location in image | Name and function |
|---------|----------|
| A | **Far left rail:** Contains tabs for adding panels, visualizations, and components to Analysis Workspace. Also contains the Data Dictionary icon that is used to open the Data Dictionary. |
| B | **Left rail:** Depending on which tab is selected in the far left rail, this area contains individual panels, visualizations, or components. |
| C | **Canvas:** This is the main area where you drag content from the left rails to build your project. The project dynamically updates as you add panels, visualizations, and components to the canvas. | 
| D | **Report suite drop-down menu:** For each panel in Analysis Workspace, the report suite drop-down menu allows you to choose the report suite that you want to use as your data source. | 

## Get started for administrators, analysts, end users, and developers

There are 3 types of Adobe Analytics users in a typical organization: administrators, analysts, and end users. 

Administrators implement and configure Adobe Analytics; analysts set up projects and create analyses using Analysis Workspace, and end users gain actionable insights about their customers, either by creating their own analyses or working with analysts to create them.

Expand the sections below to learn how each of these users can get started with Adobe Analytics.

### Get started for administrators

Analytics administrators are responsible for choosing the implementation method most appropriate for their organization.

After Adobe Analytics is implemented, administrators need to perform various configuration tasks to ensure that analysts and end users are getting the full value from Adobe Analytics. Administrators should also regularly monitor their Analytics environment to ensure the system is running efficiently.

#### Determine the types of data that should be gathered

Adobe Analytics lets you gather data from multiple channels types and bring it together to deliver meaningful, real-time customer insights. 

Following are some of the supported channels where data can be gathered:

* Mobile phones

* The Internet of Things

* TV

* Voice assistants

* Connected cars

* And more (new supported channels are added regularly)

The [implementation method](https://experienceleague.adobe.com/docs/analytics/implementation/home.html) you choose determines the type of data that can be gathered.

#### Implement Adobe Analytics

Various implementation methods are available when implementing Adobe Analytics on your website or mobile app. 

For information about each available method, see [Implement Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html).

| | Implementation methods |
|---------|---------|
| **Websites** | <ul><li>Web SDK extension (recommended)</li><li>Web SDK</li><li>Analytics extension</li><li>Legacy JavaScript</li></ul> |
| **Mobile apps** | <ul><li>Mobile SDK extension (recommended)</li><li>Analytics extension</li></ul> |

{style="table-layout:auto"}

#### Configure Adobe Analytics

Analytics administrators should complete the following tasks before making Adobe Analytics available to users in the organization:

|Task | Intended use | More information |
|---------|----------|---------|
| Define administrator roles | Adobe Analytics supports various types of administrators | [Administrator roles in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Define permissions | Analytics administrators need to assign product profiles in the Admin Console for Adobe Analytics, Report Suite Tools, and Analytics Tools. | [Analytics Permissions in the Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en) |
| Set up report suites and define settings for your company | A report suite is a silo of data that Adobe Analytics uses to generate reports.<p>Administrators can also set up [virtual report suites](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en) to further segment data.</p> | <ul><li>[Create a report suite](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Company Settings Overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Import data | Adobe Analytics data sources let you import additional online or offline data for reporting.  | [Data sources overview](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classify data with Classifications | Classifications allow you to classify data to make better use of variables, allowing you to include more content into a single variable. | | 
| Manage components | Use the Data Dictionary and the management areas for each component type to define which components are available in your Analytics implementation, as well as which are approved for your organization.<p>This should be an ongoing activity to ensure that components are being used effectively in your organization. </p>| <ul><li>[Data Dictionary overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=en)</li><li>[Calculated metrics manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Manage segements](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=en)</li><li>[Create custom date ranges](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en)</li></ul> |
| Anomaly detection and Contribution analysis | | |
| Advanced segmentation | | |
| Publish audiences to Audience Manager | | |
| Attribution | | |
| Reporting Activity Manager | | |
| Integrations | You can surface information from other applications in Adobe Analytics. <p>Following are some common integrations:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=en">Media Analytics</a></li>  | |

{style="table-layout:auto"}

#### Monitor Adobe Analytics

Various features are available to help you monitor your Adobe Analytics environment. 

Analytics administrators should be aware of the following features available to help monitor important aspects of your Analytics environment:

|Task | Intended use | More information |
|---------|----------|---------|
| Reporting Activity Manager | The Reporting Activity Manager lets you see the reporting capacity for each report suite in your organization. It provides detailed visibility into reporting consumption and helps you easily diagnose and fix capacity issues during peak reporting times. | [Reporting Activity Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Server call usage |  A server call, also known as a "hit" or an "image request", is an instance in which data is sent to Adobe servers to process. A Server Call Usage dashboard is available that tracks your server call consumption data and compares it to your contractual limit. You can set up alerts to prevent overages. | [Server Call Usage overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Log files | Log files to help you see when users log in, their usage, access, report suites, and Admin changes. | [Logs](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=en) |

{style="table-layout:auto"}

### Get started for Analysts

While anyone in an organization can use Adobe Analytics to gain actionable insights about customer behavior across websites and apps, Adobe Analytics is designed with data analysts in mind. 

Following are key tasks and features that analysts should be familiar with in order to leverage the full power of Adobe Analytics and Analysis Workspace.

| Feature | Intended use | More information |
|---------|----------|---------|
| Build and share projects in Analysis Workspace | Analysis Workspace is a flexible browser tool that allows you to quickly build analyses and share insights. Using the drag-and-drop interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, share and schedule projects with anyone in your organization.<p>Data analysts are often responsible for creating projects in Analysis Workspace for users within their organization.</p><p>After projects are created, analysts share those projects with the [end users](#end-users)(non-analysts) in their organizations who requested the data and help them understand how to interpret it.</p> | <ul><li>[Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul>|
| Attribution | Analysts can customize how dimension items get credit for success events by employing various attribution models and lookback windows in Analysis Workspace.<p>Linear attribution models gives equal credit to every touch point leading up to a conversion, while First Touch gives full credit to the first touch point. Many other attribution models are available, including the Algorithmic model, which uses statistical techniques to dynamically determine the optimal allocation of credit. </p>  | [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md) |
| Anomaly detection | Statistical modeling in Analysis Workspace automatically finds unexpected trends in your data by analyzing metrics and determining a lower bound, upper bound, and expected range of values. When an unexpected spike or drop occurs, the system alerts you in the report. | [Anomaly Detection overview](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Contribution analysis | Use Analysis Workspace to discover hidden patterns within your data to explain statistical anomalies and identify correlations behind unexpected customer actions, out-of-bound values, and sudden spikes or dips for metrics across audience segments. | [Contribution Analysis overview](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Intelligent alerts | Create and manage alerts based on data anomalies and "stacked" alerts that capture multiple metrics in a single alert. | [Intelligent Alerts overview](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Data export | Data Warehouse and Data Feeds allow you to export data to various cloud destinations, such as Google Cloud Platform, Azure RBAC, Azure SAS, and Amazon S3. | [Analytics Export Guide](https://experienceleague.adobe.com/docs/analytics/export/home.html) |
| Activity map | Activity Map is an Adobe Analytics application that is designed to rank link activity using visual overlays and provide a dashboard of real-time analytics to monitor audience engagement of your web pages.<p>Activity Map lets you set up different views to visually identify the acceleration of customer activity, quantify marketing initiatives, and act on audience needs and behaviors.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html) |
| Report Builder | Report Builder is an add-in for Microsoft Excel. Report Builder lets you build customized requests from Adobe Analytics data that are inserted into your Excel worksheets. Requests can dynamically reference cells within your worksheet, and you can update and customize how Report Builder presents the data. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### Get started for end users

End users who are not professional analysts can either work with analysts in their organization to leverage the full power of Adobe Analytics and Analysis Workspace, or they can learn the basics of Analysis Workspace in order to start gaining actionable insights about their customers.

#### Work with analysts

Typically, users in an organization who are interested in learning more about customer behavior across their various sites are not professional analysts. 

Ideally, these users should work with [analysts](#analysts) within an organization to:

1. Define requirements for the analyses by explaining to the analyst what they hope to learn about customers.

1. Review the analyses to ensure they meet the objectives.

1. Discuss the data gained from the analyses.

1. Modify the analyses as needed over time.

#### Create analyses in Analysis Workspace

You don't have to be a data analyst to gain actionable insights from Adobe Analytics.

Some users might find it helpful to work with a data analyst to set up a project in Analysis Workspace and explain how to interpret the data, as described in [Work with analysts](#work-with-analysts); other users might be comfortable building the project and interpreting the data themselves. 

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

For information about how to create analyses in Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

### Get started for developers

[Analytics APIs](https://developer.adobe.com/analytics-apis/docs/2.0/) allow you to directly call Adobe's servers to perform almost any action that you can perform in the user interface. 

You can create reports to explore, get insights, or answer important questions about your data. You can also manage components of Adobe Analytics, such as the creation of segments or calculated metrics. 

## Video overview

To learn about Adobe Analytics basics, check out this *Intro to Adobe Analytics - Skill Builder Webinar* video. The video walks you through the basics of how data is captured, how data is sent to Adobe Analytics, and what visualization capabilities you can use within Adobe Analytics. The video provides a foundation for you to build, deploy, collect, and interpret data, allowing you to provide actionable insights and recommendations based on the collected data.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

For questions about which tool to use, see [Which Adobe Analytics tool should I use?](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html).

## Go further with Customer Journey Analytics

Customer Journey Analytics is Adobe's next-generation Analytics solution that lets you use the power of Analysis Workspace with data from Adobe Experience Platform. It can break down, filter, query, and visualize years' worth of data, and is combined with Platform's ability to hold all kinds of data schemas and types. 

Following are some of the advantages of Customer Journey Analytics over Adobe Analytics:

* **Unlimited variables and events**: The concepts of eVars, props, and events no longer exist. Data is primarily focused on dimensions and metrics. Datasets can have an unlimited number of unique dimensions and metrics.

* **Unlimited unique values**: Adobe Experience Platform is not constrained to any unique limitations.

* **Alter historical data**: Using Adobe Experience Platform, data can be removed or corrected.

* **Cross-report-suite data**: Existing implementations from multiple datasets can be combined in Platform.

For more information, see [Customer Journey Analytics overview](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en).

