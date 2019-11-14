---
description: This section contains the key concepts for Adobe Analytics, a brief description of the concept, and a specific documentation link with additional detail on the topic.
title: Adobe Analytics - key concepts
---

# Adobe Analytics - key concepts

This section contains the key concepts for Adobe Analytics, a brief description of the concept, and a specific documentation link with additional detail on the topic.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Product | Description | Documentation Link |
|--- |--- |--- |
|Analysis Workspace|Browser solution for building robust, custom analysis projects and democratizing insights. Offers more report flexibility than Reports &amp; Analytics|[adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html)|
|Reports &amp; Analytics (formerly SiteCatalyst)|Browser solution for reporting and analysis. Starter tool in the Analytics package. |[Reports &amp; Analytics home](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html)|
|Report Builder|Excel add-in that lets you build customized requests from Adobe Analytics data, and visualize them using Microsoft Excel.|[Report Builder home](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html)|
|Ad Hoc Analysis (formerly Discover)|Java-based tool for advanced digital analysis.|[Ad Hoc Analysis home](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html)|
|Data Workbench (formerly Insight)|Designed to collect, process, analyze, and visualize data from both online and offline customer interactions across multiple channels.|[Data Workbench Client](https://marketing.adobe.com/resources/help/en_US/insight/client/)|
|Data Warehouse|Raw, unprocessed data for storage and custom reports, which you can run by filtering the data. Not hit level.|[Data Warehouse home](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html)|
|Adobe Mobile Services|Brings together mobile marketing capabilities for mobile applications from across the Adobe Experience Cloud, letting you understand and improve user engagement with your applications.|[Mobile Services home](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)|
|Adobe Exchange Data Connectors (formerly Genesis)|Import tracking data from third-party applications into Analytics, to give end-to-end visibility into performance in one central location.|[Data Connectors home](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works)|
|Dynamic Tag Management (DTM)|Helps you manage your Analytics, Target, and other tags across all of your sites, regardless of your number of domains.|[DTM home](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html)|
|Adobe Launch|The next generation of website tag and mobile SDK management capabilities from Adobe.|[Adobe Launch home](https://docs.adobe.com/content/help/en/launch/using/overview.html)|

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Click [here](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) for an expanded glossary of Adobe Analytics terms.

| Term | Description | Documentation Link |
|--- |--- |--- |
|Props (Custom Traffic)|Dimensions used to track page-by-page site traffic activity. Props do not persist between pages. Key applications of traffic variables: <ul><li>Simple counting to find 'most popular' of a specific value</li><li>Visibility into how users are pathing through your site </li></ul><br>Examples of traffic variables: Page Name, Site Sections, Browsers</br>|[Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html)|
|eVar (Custom Conversion)|Dimensions that persist for a period of time that is customized by you. Expiration options include event expiration, visit expiration, or X-day expiration and should be driven by the type of analysis that will be performed on that variable.<br>Key differences between eVars and props:</br><ul><li>Props are often used for pathing analysis because persistence is removed.</li><li>eVars are often used for conversion analysis.</li></ul><br>Examples of conversion variables: Internal Search Terms, Internal Promotions, External Campaigns (s.campaign)</br>|[eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)|
|Events/Metrics (s.events)|Metrics that measure key actions that we want to our visitors to take on our site. There are 3 types of events: Counter, Numeric, and Currency. Events are most useful when added to conversion variable (eVar) reports. The eVar provides the qualitative information about what happened and the Event gives quantitative information about what happened. <br>Key differences between eVars and events:</br><ul><li>eVars tell us who, what, or which affected conversion</li><li>Events measure how many conversions took place</li></ul><br>Examples of conversion events: Orders, Application Starts, Leads, Revenue.</br>| [Events](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html)|
|Components|Dimensions, metrics, segments, and time granularities (date ranges) that you can drag-and-drop onto a project.|[Components](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html)|
|Dimensions|Collection of eVars, props, classifications, and standard Adobe collected values.|[Dimensions](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html)|
|Metrics|Collection of implemented events and calculated metrics.|[Metrics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html)|
|Calculated Metrics|Ability to derive custom metrics from existing metrics captured through your implementation.|[Calculated Metrics](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html)|
|Segments|Ability to build, manage, share, and apply powerful, focused audience segments to your Analytics reports. Segments are shared across Analytics products and can be shared across the Experience Cloud.|[Segmentation](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html)|
|Time (Date Ranges)|Ability to filter date to any time period & create custom date ranges that can be reused in your analysis.|[Date Ranges](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)|
|Visualizations|Rich visuals that can help bring data to life in your projects.|[Visualizations](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)|
|Curation|Ability to limit the components accessible in a project or Virtual Report Suite.|[VRS curation](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[Project curation](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[Comparison](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html)|

## Key reports

| Report | Description | Documentation Link |
|--- |--- |--- |
|Full Dimensions/Reports List|Definition of all dimensions/reports available in Adobe Analytics.|[Dimensions](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html)|
|Advertising Analytics|Analyze all your Google and Bing Paid Search data side by side, within Adobe Analytics. Dimensions created through the integration include Ad Platform, Keyword, Match Type, etc. Metrics created are AMO Impressions, AMO Clicks, AMO Cost, Avg. Position, and Avg. Quality Score.|[Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html)|
|Audience Analytics|Enrich inbound Analytics hits with a user's audience membership in AAM. you can incorporate AAM audience data such as demographic information (e.g. gender or income level), psychographic information (e.g. interests and hobbies), CRM data, and ad impression data into any Analytics workflow. Dimensions created through this integration are Audience ID & Audience Name.| [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html)|
|Attribution IQ|Enables you to understand how meaningful engagement takes place across the customer journey, intelligently identifying inflection points that lead customers to target outcomes, effectively optimizing marketing initiatives. Models include first, last, linear, participation, j-shaped, inverse j-shaped, u-shape, same touch, custom and time decay.|[Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html)|
|Anomaly Detection|A statistical method to determine how a given metric has changed in relation to previous data. AD is turned on by default for all trended visualizations in Analysis Workspace.| [Anomaly Detection](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)|
|Contribution Analysis|Explores the "why" behind anomalies that occur, by running an automated analysis of every single metric and dimension you have access to.|[Contribution Analysis](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html)|
|Cohort Analysis|A cohort is a group of people sharing common characteristics over a specified period. Cohort analysis aides in analyzing retention & churn of your users.|[Cohort Analysis](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html)|
|Customer Journey Reports|Displays information about the path your users take through your site or app. Prop, eVars and events can be used in this analysis in Analysis Workspace.|[Analysis Workspace Fallout](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[Analysis Workspace Flow](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[Reports &amp; Analytics pathing](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html)|
|Marketing Channels|Reports that help you learn which external channels drive users to your site and which are most effective at driving conversion. First & Last touch attribution views are provided. This is the preferred external traffic source report in Adobe Analytics (rather than Campaigns or Traffic Sources) because it is the most comprehensive look at both paid and organic channels.|[Marketing Channels](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html)|
|Mobile|Displays information about websites accessed from a mobile device or tablet.|[Mobile report|(https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html)|
|Mobile App|Displays basic usage information related to your mobile apps. These reports are available once our SDK is implemented & reporting is turned on.  Additionally, Adobe Mobile Services has created a separate mobile app interface that provides more comprehensive app data, enabling you to understand and improve user engagement with your apps.  Access the interface [here](https://mobilemarketing.adobe.com).|[Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)|Products|Identifies how individual products and groups of products (categories) contribute to your various conversion metrics, such as Revenue or Checkouts.|[Products report](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html)|
|Segment Comparison|Discovers the most statistically significant differences among segments through an automated analysis of every single metric and dimension you have access to.|[Segment Comparison](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html)|
|Site Content report|Displays information about which pages and areas of your site are most active and which servers are getting the most use.|[Site Content report](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html)|
|Site Metrics report|Display quantitative information about your website, such as unique visitors, orders, revenue, etc. Each metric can be placed in other item-based reports.|[Site Metrics report](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html)|
|Visitor Profile|Reports that help you see purchasing patterns of customers from various profile categories, including countries, states, ZIP/postal codes and domains.|[Visitor Profile](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html)|
|Visitor Retention|Displays information about your customer loyalty, such as how many & how often visitors return to your site.|[Visitor Retention](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html)|
|Project Link, Sharing and Scheduling|Methods to save and/or share your work with other in the Analytics interface.|[Send and schedule files](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html)|

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

|  Metric Name  | Definition  | Documentation Link  |
|---|---|---|
|  Full Metric List  | Definition of all metrics in Adobe Analytics.  | [Metrics overview](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html)  |
|  Unique Visitors  | The number of unduplicated visitors to the website over the course of a specified time period.  | [Unique Visitors](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html)  |
|  Visits  | A sequence of page views in a sitting. The visit begins when a person first views a page on the site and ends after 30 minutes of inactivity.  | [Visits](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html)  |
|  Page Views  | A page view occurs when a visitor views a page on your web site.  | [Page Views](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html)  |
|  Instances  | The number of times a variable was defined. Each time Adobe Analytics sees a value within a variable, instances are incremented by one in that respective report.  | [Instances](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html)  |
|  Occurrences  | The number of times a variable was defined or persisted.  | [Occurrences](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html)  |

## Import options {#concept_7C6DF03B5F9149E2A77F36C739432059}

|  Option  | Description  | Documentation Link  |
|---|---|---|
|  Classification Importer  | Import metadata against captured dimensions via browser or FTP upload. Manual method compared to Rule Builder.  | [Classification Importer](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html)  |
|  Rule Builder  | Automatically create metadata classifications of dimensions based on user-defined rules.  | [Classification Rule Builder](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html)  |
| Customer Attributes|CRM data uploaded to the Experience Cloud for use in  Adobe Analytics and Adobe Target.|[Customer Attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html)|
|  Data Sources  | Impor offline metrics into Analytics against dimensions or simply by day.  | [Data Sources](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html)|
|  Adobe Exchange Data Connectors  |See [Analytics Tools](/help/landing/an-key-concepts.md)|  |
| Native Integrations | Audience Analytics & Advertising Analytics. |See "Key Reports" section.|

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

|  Option  | Description  | Documentation Link  |
|---|---|---|
|UI downloads and scheduling|Export data from Analysis Workspace as CSV or PDF|[Download PDF or CSV files](/help/analyze/analysis-workspace/curate-share/download-send.md)|
|Report Builder|See Analytics tools.|
|Analytics API|Create your own customized queries of Analytics data.|<ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul>|
|Data Warehouse|See Analytics tools.| |
|Analytics Data Feed|Most granular way to get data out of Analytics. Set up a hit-level feed out of Analytics.|[Analytics Data Feed](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html)|

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Method/Resource | Description | Documentation Link |
|--- |--- |--- |
|Developer Resources|Documentation that outlines the libraries available to collect Analytics data across all available platforms (web, mobile app, video, flash, etc)|[Developer docs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)|
|Implementation Guide|A description of data collection variables and details on implementing data collection code in JavaScript.|[Implementation Guide](https://docs.adobe.com/content/help/en/analytics/implementation/home.html)|
|App Measurement (s_code)|Global variable management|[AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)|
|App SDKs|Customized package that includes a pre-populated version of the configuration file for Apps.|<ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul>|
|DTM and Adobe Launch|See Analytics Tools.||
|VISTA|Enables you to apply server-side logic to alter or segment data as it is collected. | [VISTA rules](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html)|
|Processing Rules|Ability to set, modify, and copy variables in the Analytics UI, to alter the data collected.|[Processing Rules](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html)|
|Debugger Options|There are several debuggers & packet sniffers available to help validate your implementation, including the Adobe Experience Cloud debugger.|[Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en)|
|Data Insertion API|The Data Insertion API provides a mechanism for server-side data collection and submission to Experience Cloud servers. Instead of using JavaScript beacons on each Web page to transmit visitor data to Experience Cloud servers, server-side data collection collects data based solely on Web browser requests and Web server responses.|[Steps to implement Adobe Analytics data insertion API using POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)|
