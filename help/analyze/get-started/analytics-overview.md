---
description: General overview information about Adobe Analytics
title: Adobe Analytics overview
feature: Analytics Basics
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

The following features in Adobe Analytics support these goals:

* Multichannel data collection

* [Offline data integration](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Ad hoc analysis in Analysis Workspace](/help/analyze/analysis-workspace/home.md)

### Attribution

Attribution lets organizations see how different interactions throughout the customer journey affect conversion. In addition to providing more traditional attribution options, such as Linear or First Touch models, Attribution in Adobe Analytics also uses machine learning and advanced statistical models to understand the precise impact of every touch.

For more information, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).


### Predictive analytics

Predictive analytics uses machine learning and advanced statistical modeling to analyze customer data, find patterns, and predict future behavior such as churn or a likelihood to convert. It allows data analysts to take advantage of huge data sets that might otherwise be wasted.

Key features in Adobe Analytics that provide these predictive capabilities are:

* [Anomaly detection](#anomaly-detection)

* [Contribution analysis](#contribution-analysis)

* [Intelligent alerts](#intelligent-alerts)

## Prerequisites

* <!-- ?? -->

## Supported channels where you can gather data

<!-- add info about how you can track on web, mobile, etc. ? -->

Adobe Analytics lets you gather data from multiple channels types and bring it together to deliver meaningful, real-time customer insights.

Following are some of the supported channels where you can gather data:

* Mobile phones

* The Internet of Things

* TV

* Voice assistants

* Connected cars

* And more (new supported channels are added regularly)

Learn more about how to gather data...

## Administrators

Analytics administrators are responsible for choosing the implementation method most appropriate for their organization.

After Adobe Analytics is implemented, administrators need to perform various configuration tasks to ensure that analysts and end users are getting the full value from Adobe Analytics.

### Implement Adobe Analytics

Various implementation methods are available when implementing Adobe Analytics on your website or mobile app. 

**Website implementation methods:**

* Web SDK extension (recommended)

* Web SDK

* Analytics extension

* Legacy JavaScript

**Mobile app implementation methods:**

* Mobile SDK extension (recommended)

* Analytics extension

For information about each available method, see [Implement Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html).

### Configure Adobe Analytics

Analytics administrators should complete the following tasks before making Adobe Analytics available to users in the organization:

|Task | Intended use | More information |
|---------|----------|---------|
| Define administrator roles | Adobe Analytics supports various types of administrators | [Administrator roles in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Define permissions | Analytics administrators need to assign product profiles in the Admin Console for Adobe Analytics, Report Suite Tools, and Analytics Tools. | [Analytics Permissions in the Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en) |
| Set up report suites and define settings for your company | A report suite is a silo of data that Adobe Analytics uses to generate reports. | <ul><li>[Create a report suite](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Company Settings Overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Import data | Adobe Analytics data sources let you import additional online or offline data for reporting.  | [Data sources overview](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classify data with Classifications | Classifications allow you to classify data to make better use of variables, allowing you to include more content into a single variable. | | 
| Manage components | Use the Data Dictionary and the management areas for each component type to define which components are available in your Analytics implementation, as well as which are approved for your organization.<p>This should be an ongoing activity to ensure that components are </p>| <ul><li>[Data Dictionary overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=en)</li><li>[Calculated metrics manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Manage segements](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=en)</li><li>[Create custom date ranges](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en)</li></ul> |
| Anomaly detection and Contribution analysis | | |
| Advanced segmentation | | |
| Publish audiences to Audience Manager | | |
| Attribution | | |
| Integrations | Analytics for Target, etc.  | |

### Understand the admin interface

To access the admin interface:

1. In Adobe Analytics, select the [!UICONTROL **Admin**] tab.

## Analysts

While anyone in an organization can use Adobe Analytics to gain actionable insights about customer behavior across websites and apps, Adobe Analytics is designed with data analysts in mind. 



Share projects and help [end users](#end-users) (non-analysts) in their organizations understand the data that is gathered

### Build projects in Analysis Workspace



Data analysts are often responsible for creating projects in Analysis Workspace for users withing their organization. (For information about creating projects, see [Create projects in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).)

Speicific features and tasks that analysts should be familiar with in Analysis Workspace include:

|Task | Intended use | More information |
|---------|----------|---------|
| Alerts | Be alerted when things happen to your data. | [Intelligent Alerts overview](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |

| Tool      | Description    |
|-----------|----------------|
| **[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html)** | Analysis Workspace is a flexible browser tool that allows you to quickly build analyses and share insights. Using the drag-and-drop interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, share and schedule projects with anyone in your organization. |
| **[Analytics dashboards](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html)** | Analytics dashboards and their mobile scorecards allow executive users to view a broad rendering of important summary data quickly and easily on their own mobile devices. Curators add visualizations to mobile scorecard projects and share them with executives.  <br>Scorecards provide a way to target and measure KPIs and provide a clear indication of how well organizations are working to achieve their targets. |
| **[Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html)** | Activity Map is an Adobe Analytics application that is designed to rank link activity using visual overlays and provide a dashboard of real-time analytics to monitor audience engagement of your web pages. <br>Activity Map lets you set up different views to visually identify the acceleration of customer activity, quantify marketing initiatives, and act on audience needs and behaviors." |
| **[Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html)** | Report Builder is an add-in for Microsoft Excel. Report Builder lets you build customized requests from Adobe Analytics data that are inserted into your Excel worksheets. Requests can dynamically reference cells within your worksheet, and you can update and customize how Report Builder presents the data. |
| **[Analytics APIs](https://developer.adobe.com/analytics-apis/docs/2.0/)** | Analytics APIs allow you to directly call Adobe's servers to perform almost any action that you can perform in the user interface. You can create reports to explore, get insights, or answer important questions about your data. You can also manage components of Adobe Analytics, such as the creation of segments or calculated metrics. |
| **[Reports & Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/getting-started.html)** | Reports & Analytics is a tool with dozens of pre-built reports and visualizations. These are now available within Analysis Workspace. **Effective December 31, 2023, Adobe intends to discontinue Reports & Analytics and its accompanying reports and features. Adobe recommends using Analysis Workspace for most reporting needs.** For additional information, see [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). | 


* Realtime reporting

* Virtual report suites (filter data in a report suite)

### Attribution

Analysts can customize how dimension items get credit for success events by employing various attribution models and lookback windows in Analysis Workspace. 

Linear attribution models gives equal credit to every touch point leading up to a conversion, while First Touch gives full credit to the first touch point. Many other attribution models are available, including the Algorithmic model, which uses statistical techniques to dynamically determine the optimal allocation of credit. 

For more information, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

### Anomaly detection

Statistical modeling in Analysis Workspace automatically finds unexpected trends in your data by analyzing metrics and determining a lower bound, upper bound, and expected range of values. When an unexpected spike or drop occurs, the system alerts you in the report.

For more information, see [Anomaly Detection overview](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md).

### Contribution analysis

Use Analysis Workspace to discover hidden patterns within your data to explain statistical anomalies and identify correlations behind unexpected customer actions, out-of-bound values, and sudden spikes or dips for metrics across audience segments.

For more information, see [Contribution Analysis overview](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md).

### Intelligent alerts

Create and manage alerts based on data anomalies and "stacked" alerts that capture multiple metrics in a single alert.

For more information, see [Intelligent Alerts overview](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md).

### Export data

Data Warehouse and Data Feeds allow you to export data to various cloud destinations, such as Google Cloud Platform, Azure RBAC, Azure SAS, and Amazon S3.

For more information, see the [Analytics Export Guide](https://experienceleague.adobe.com/docs/analytics/export/home.html).

### Understand the interface for analyst features

## End users

End users who are not professional analysts can either work with analysts in their organization to leverage the full power of Adobe Analytics and Analysis Workspace, or they can learn the basics of Analysis Workspace in order to start gaining actionable insights about their customers.

### Work with analysts

Typically, users in an organization who are interested in learning more about customer behavior across their various sites are not professional analysts. 

Ideally, these users should work with [analysts](#analysts) within an organization to:

1. Define requirements for the analyses by explaining to the analyst what they hope to learn about customers.

1. Review the analyses to ensure they meet the objectives.

1. Discuss the data gained from the analyses.

1. Modify the analyses as needed over time.

### Understand the Analysis Workspace interface

You don't have to be a data analyst to gain actionable insights from Adobe Analytics.

Some users might find it helpful to work with a data analyst to set up a project in Analysis Workspace and explain how to interpret the data, as described in [Work with analysts](#work-with-analysts); other users might be comfortable building the project and interpreting the data themselves. 

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

For information about how to create analyses and analyze data in Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

## Go further with Customer Journey Analytics

Customer Journey Analytics is Adobe's next-generation Analytics solution that lets you use the power of Analysis Workspace with data from Adobe Experience Platform. It can break down, filter, query, and visualize years' worth of data, and is combined with Platform's ability to hold all kinds of data schemas and types. 

Following are some of the advantages of Customer Journey Analytics over Adobe Analytics:

* **Unlimited variables and events**: The concepts of eVars, props, and events no longer exist. Data is primarily focused on dimensions and metrics. Datasets can have an unlimited number of unique dimensions and metrics.

* **Unlimited unique values**: Adobe Experience Platform is not constrained to any unique limitations.

* **Alter historical data**: Using Adobe Experience Platform, data can be removed or corrected.

* **Cross-report-suite data**: Existing implementations from multiple datasets can be combined in Platform.

For more information, see [Customer Journey Analytics overview](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en).

## Overview video

To learn about Adobe Analytics basics, check out the *Intro to Adobe Analytics - Skill Builder Webinar* video below. The video walks you through the basics of how data is captured, how data is sent to Adobe Analytics, and what visualization capabilities you can use within Adobe Analytics. The video provides a foundation for you to build, deploy, collect, and interpret data...allowing you to provide actionable insights and recommendations based on the collected data.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

For questions about which tool to use, see [Which Adobe Analytics tool should I use?](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html).

