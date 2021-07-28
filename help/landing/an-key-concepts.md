---
description: This section contains the key concepts for Adobe Analytics, a brief description of the concept, and a specific documentation link with additional detail on the topic.
title: Adobe Analytics - key concepts
exl-id: 359c6663-33fd-4491-8ea0-55cd9ae31859
---
# Adobe Analytics - key concepts

This section contains the key concepts for Adobe Analytics, a brief description of the concept, and a specific documentation link with additional detail on the topic.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Product | Description | Documentation Link |
| --- | --- | --- |
| Analysis Workspace | Browser solution for building robust, custom analysis projects and democratizing insights. Offers more report flexibility than Reports and Analytics | [Analysis Workspace home](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics (formerly SiteCatalyst) | Browser solution for reporting and analysis. Starter tool in the Analytics package. | [Reports and Analytics home](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | Excel add-in that lets you build customized requests from Adobe Analytics data, and visualize them using Microsoft Excel. | [Report Builder home](/help/analyze/report-builder/home.md) |
| Data Workbench (formerly Insight) | Designed to collect, process, analyze, and visualize data from both online and offline customer interactions across multiple channels. | [Data Workbench Client](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | Raw, unprocessed data for storage and custom reports, which you can run by filtering the data. Not hit level. | [Data Warehouse home](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | Brings together mobile marketing capabilities for mobile applications from across the Adobe Experience Cloud, letting you understand and improve user engagement with your applications. | [Mobile Services home](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors (formerly Genesis) | Import tracking data from third-party applications into Analytics, to give end-to-end visibility into performance in one central location. Effective August 1, 2021, Adobe intends to discontinue Data Connectors Integrations. | [Data Connectors home](/help/import/data-connectors/data-connectors-eol.md) |
| Adobe Experience Platform Data Collection | The next generation of website tag and mobile SDK management capabilities from Adobe. | [Adobe Experience Platform Data Collection home](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Click [here](/help/technotes/terms.md) for an expanded glossary of Adobe Analytics terms.

| Term | Description | Documentation Link |
| --- | --- | --- |
| Props (Custom Traffic) | Dimensions used to track page-by-page site traffic activity. Props do not persist between pages. Key applications of traffic variables: <ul> <li>Simple counting to find 'most popular' of a specific value</li> <li>Visibility into how users are pathing through your site</li> </ul> <br> Examples of traffic variables: Page Name, Site Sections, Browsers | [Props](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (Custom Conversion) | Dimensions that persist for a period of time that is customized by you. Expiration options include event expiration, visit expiration, or X-day expiration and should be driven by the type of analysis that will be performed on that variable. <br> Key differences between eVars and props: <ul> <li>Props are often used for pathing analysis because persistence is removed.</li> <li>eVars are often used for conversion analysis.</li> </ul> <br> Examples of conversion variables: Internal Search Terms, Internal Promotions, External Campaigns (s.campaign) | [eVars](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| Events/Metrics (s.events) | Metrics that measure key actions that we want to our visitors to take on our site. There are 3 types of events: Counter, Numeric, and Currency. Events are most useful when added to conversion variable (eVar) reports. The eVar provides the qualitative information about what happened and the Event gives quantitative information about what happened. <br> Key differences between eVars and events: <ul> <li>eVars tell us who, what, or which affected conversion</li> <li>Events measure how many conversions took place</li> </ul> <br> Examples of conversion events: Orders, Application Starts, Leads, Revenue. | [Events](/help/admin/admin/c-success-events/success-event.md) |
| Components | Dimensions, metrics, segments, and time granularities (date ranges) that you can drag-and-drop onto a project. | [Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| Dimensions | Collection of eVars, props, classifications, and standard Adobe collected values. | [Dimensions](/help/components/dimensions/overview.md) |
| Metrics | Collection of implemented events and calculated metrics. | [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| Calculated Metrics | Ability to derive custom metrics from existing metrics captured through your implementation. | [Calculated Metrics](/help/components/c-calcmetrics/cm-overview.md) |
| Segments | Ability to build, manage, share, and apply powerful, focused audience segments to your Analytics reports. Segments are shared across Analytics products and can be shared across the Experience Cloud. | [Segmentation](/help/components/segmentation/seg-home.md) |
| Time (Date Ranges) | Ability to filter date to any time period & create custom date ranges that can be reused in your analysis. | [Date Ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| Visualizations | Rich visuals that can help bring data to life in your projects. | [Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| Curation | Ability to limit the components accessible in a project or Virtual Report Suite. | [VRS curation](/help/components/vrs/vrs-components.md) <br> [Project curation](/help/analyze/analysis-workspace/curate-share/curate.md) |

## Key reports

| Report | Description | Documentation Link |
| --- | --- | --- |
| Full Dimensions/Reports List | Definition of all dimensions/reports available in Adobe Analytics. | [Dimensions](/help/components/dimensions/overview.md) |
| Advertising Analytics | Analyze all your Google and Bing Paid Search data side by side, within Adobe Analytics. Dimensions created through the integration include Ad Platform, Keyword, Match Type, etc. Metrics created are AMO Impressions, AMO Clicks, AMO Cost, Avg. Position, and Avg. Quality Score. | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | Enrich inbound Analytics hits with a user's audience membership in AAM. you can incorporate AAM audience data such as demographic information (e.g. gender or income level), psychographic information (e.g. interests and hobbies), CRM data, and ad impression data into any Analytics workflow. Dimensions created through this integration are Audience ID & Audience Name. | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | Enables you to understand how meaningful engagement takes place across the customer journey, intelligently identifying inflection points that lead customers to target outcomes, effectively optimizing marketing initiatives. Models include first, last, linear, participation, j-shaped, inverse j-shaped, u-shape, same touch, custom and time decay. | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| Anomaly Detection | A statistical method to determine how a given metric has changed in relation to previous data. AD is turned on by default for all trended visualizations in Analysis Workspace. | [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Contribution Analysis | Explores the "why" behind anomalies that occur, by running an automated analysis of every single metric and dimension you have access to. | [Contribution Analysis](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Cohort Analysis | A cohort is a group of people sharing common characteristics over a specified period. Cohort analysis aides in analyzing retention & churn of your users. | [Cohort Analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| Customer Journey Reports | Displays information about the path your users take through your site or app. Prop, eVars and events can be used in this analysis in Analysis Workspace. | [Analysis Workspace Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Analysis Workspace Flow](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Reports and Analytics pathing](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| Marketing Channels | Reports that help you learn which external channels drive users to your site and which are most effective at driving conversion. First & Last touch attribution views are provided. This is the preferred external traffic source report in Adobe Analytics (rather than Campaigns or Traffic Sources) because it is the most comprehensive look at both paid and organic channels. | [Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| Mobile | Displays information about websites accessed from a mobile device or tablet. | [Mobile report](/help/components/dimensions/mobile-dimensions.md) |
| Mobile App | Displays basic usage information related to your mobile apps. These reports are available once our SDK is implemented & reporting is turned on.  Additionally, Adobe Mobile Services has created a separate mobile app interface that provides more comprehensive app data, enabling you to understand and improve user engagement with your apps. | [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) |
| Products | Identifies how individual products and groups of products (categories) contribute to your various conversion metrics, such as Revenue or Checkouts. | [Products report](/help/components/dimensions/product.md) |
| Segment Comparison | Discovers the most statistically significant differences among segments through an automated analysis of every single metric and dimension you have access to. | [Segment Comparison](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| Site Content report | Displays information about which pages and areas of your site are most active and which servers are getting the most use. | [Site Content report](/help/components/dimensions/page.md) |
| Site Metrics report | Display quantitative information about your website, such as unique visitors, orders, revenue, etc. Each metric can be placed in other item-based reports. | [Site Metrics report](/help/components/metrics/overview.md) |
| Visitor Profile | Reports that help you see purchasing patterns of customers from various profile categories, including countries, states, ZIP/postal codes and domains. | [Visitor Profile](/help/components/dimensions/language.md) |
| Visitor Retention | Displays information about your customer loyalty, such as how many & how often visitors return to your site. | [Visitor Retention](/help/components/dimensions/customer-loyalty.md) |
| Project Link, Sharing and Scheduling | Methods to save and/or share your work with other in the Analytics interface. | [Send and schedule files](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Metric Name | Definition | Documentation Link |
| --- | --- | --- |
| Full Metric List | Definition of all metrics in Adobe Analytics. | [Metrics overview](/help/components/metrics/overview.md) |
| Unique Visitors | The number of unduplicated visitors to the website over the course of a specified time period. | [Unique Visitors](/help/components/metrics/unique-visitors.md) |
| Visits | A sequence of page views in a sitting. The visit begins when a person first views a page on the site and ends after 30 minutes of inactivity. | [Visits](/help/components/metrics/visits.md) |
| Page Views | A page view occurs when a visitor views a page on your web site. | [Page Views](/help/components/metrics/page-views.md) |
| Instances | The number of times a variable was defined. Each time Adobe Analytics sees a value within a variable, instances are incremented by one in that respective report. | [Instances](/help/components/metrics/instances.md) |
| Occurrences | The number of times a variable was defined or persisted. | [Occurrences](/help/components/metrics/occurrences.md) |

## Import options {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Option | Description | Documentation Link |
| --- | --- | --- |
| Classification Importer | Import metadata against captured dimensions via browser or FTP upload. Manual method compared to Rule Builder. | [Classification Importer](/help/components/classifications/importer/c-working-with-saint.md) |
| Rule Builder | Automatically create metadata classifications of dimensions based on user-defined rules. | [Classification Rule Builder](/help/components/classifications/crb/classification-rule-builder.md) |
| Customer Attributes | CRM data uploaded to the Experience Cloud for use in  Adobe Analytics and Adobe Target. | [Customer Attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) |
| Data Sources | Impor offline metrics into Analytics against dimensions or simply by day. | [Data Sources](/help/import/c-data-sources/datasrc-home.md) |
| Adobe Exchange Data Connectors | See [Analytics Tools](/help/import/data-connectors/data-connectors-eol.md)|  |
| Native Integrations | Audience Analytics & Advertising Analytics. | See "Key Reports" section. |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| Option | Description | Documentation Link |
| --- | --- | --- |
| UI downloads and scheduling | Export data from Analysis Workspace as CSV or PDF | [Download PDF or CSV files](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | See Analytics tools. |  |
| Analytics API | Create your own customized queries of Analytics data. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | See Analytics tools. |  |
| Analytics Data Feed | Most granular way to get data out of Analytics. Set up a hit-level feed out of Analytics. | [Analytics Data Feed](/help/export/analytics-data-feed/data-feed-overview.md) |

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Method/Resource | Description | Documentation Link |
| --- | --- | --- |
| Developer Resources | Documentation that outlines the libraries available to collect Analytics data across all available platforms (web, mobile app, video, flash, etc) | [Developer docs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Implementation Guide | A description of data collection variables and details on implementing data collection code in JavaScript. | [Implementation Guide](/help/implement/home.md) |
| App Measurement (s_code) | Global variable management | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| App SDKs | Customized package that includes a pre-populated version of the configuration file for Apps. | <ul><li>[iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/overview.html)</li><li>[Android](https://experienceleague.adobe.com/docs/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| Adobe Experience Platform Data Collection | See Analytics Tools. |  |
| VISTA | Enables you to apply server-side logic to alter or segment data as it is collected. | [VISTA rules](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| Processing Rules | Ability to set, modify, and copy variables in the Analytics UI, to alter the data collected. | [Processing Rules](/help/admin/admin/c-processing-rules/processing-rules.md) |
| Debugger Options | There are several debuggers and packet sniffers available to help validate your implementation, including the Adobe Experience Cloud debugger. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| Data Insertion API | The Data Insertion API provides a mechanism for server-side data collection and submission to Experience Cloud servers. Instead of using JavaScript beacons on each Web page to transmit visitor data to Experience Cloud servers, server-side data collection collects data based solely on Web browser requests and Web server responses. | [Steps to implement Adobe Analytics data insertion API using POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
