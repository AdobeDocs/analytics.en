---
title: Terms used in Adobe Analytics
description: Glossary for Adobe Analytics, defining common terms used.
exl-id: 07507ba1-a512-48d9-8022-6084de4ae262
---
# Terms used in Adobe Analytics

Use this glossary to understand the context of many terms Adobe Analytics uses.

* **Activity map:** A browser plug-in that shows what areas on your site were clicked on the most. See [Activity Map](/help/analyze/activity-map/activity-map.md) in the Analyze user guide.
* **Admin console:** Can refer to:
  * Legacy admin tools, where report suite settings in Adobe Analytics are managed. In previous versions of Adobe Analytics, user permissions were also managed here. See [Admin Tools](/help/admin/admin/c-admin-tools.md) in the Admin user guide.
  * The Adobe admin console, where product access is provisioned and user permissions are managed. See [Admin Console](/help/admin/admin-console/home.md) in the Admin user guide.
* **Allocation:** If a conversion variable encounters more than one value during a visit, the variable's allocation setting determines which value is kept. See [Conversion variables](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Analysis Workspace:** Browser solution for building robust, custom analysis projects and democratizing insights. Offers more report flexibility than Reports and Analytics.
* **Anomaly:** Detected using statistical modeling to automatically find unexpected trends in data. The model analyzes metrics and determines a lower bound, upper bound, and expected range of values. See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in the Analyze user guide.
* **AppMeasurement:** The code library used to gather data and send it to Adobe. See the [Homepage](/help/implement/home.md) of the Implement user guide.
* **ASI slot:** No longer exists. In previous versions of Adobe Analytics, ASI slots provided a temporary report suite container to view segmented data. In the current version of Adobe Analytics, segments can be applied instantly to any report.
* **Breakdown:** Lets you view a dimension inside the context of another dimension. See [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Bounce:** A visit that consists of a single hit. See [Bounces](/help/components/metrics/bounces.md) in the Components user guide. See also Single access.
* **Calculated metric:** Allows the combination of existing metrics, statistical functions, and formulas for use in reporting. See [Calculated metrics](/help/components/c-calcmetrics/cm-overview.md) in the Components user guide.
* **Campaign:** Can refer to:
  * The Campaign variable, which populates the Tracking Code dimension. See [campaign](../implement/vars/page-vars/campaign.md) in the Implement user guide.
  * A default classification of the Tracking Code dimension; automatically created for all report suites.
  * Adobe Campaign, part of the Adobe Experience Cloud. More information on [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **Channel:** Can refer to:
  * The Channel variable, which populates the Site Sections dimension. See [Page variables](/help/implement/vars/page-vars/page-variables.md) in the Implement user guide.
  * Marketing Channels, a component that helps understand how users arrive to your site. See [Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md) in the Components user guide.
* **Classification:** A feature in Adobe Analytics that allows the grouping of dimension items. See [Classifications](/help/components/classifications/c-classifications.md) in the Components user guide.
* **Clickmap:** No longer used. A legacy browser plug-in that shows what areas on your site were clicked on the most. This tool was retired in favor of Activity map.
* **Clickstream data feed:** See Data feed.
* **Cohort:** A group of people sharing common characteristics over a given period of time. See [What is Cohort Analysis?](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analyze user guide.
* **Collection server:** See Data collection server.
* **Context data variables:** Temporary variables used solely in processing rules. Context data variable values are permanently lost if a processing rule does not copy them to a conversion or traffic variable. See [Context data variables](../implement/vars/page-vars/contextdata.md) in the Implement user guide.
* **Conversion variable:** Also known as eVars. Stores a custom value, and preserves the variable value until it expires. See the [eVar](/help/components/dimensions/evar.md) dimension in the Components user guide.
* **Correlation:** No longer used as a term; replaced with dimension breakdowns. In previous versions of Adobe Analytics, correlations granted the ability to break down traffic variables. See [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Current data:** An option in some reports that allows the inclusion of recently collected data that hasn't fully processed yet. See [Current data](/help/analyze/reports-analytics/current-data.md) in the Analyze user guide.
* **Custom link:** A type of hit that contains non-page view data. See the [s.tl() function](../implement/vars/functions/tl-method.md) in the Implement user guide. See also Hit.
* **Customer attributes:** An Experience Cloud feature that allows the upload of attribute data. See [Customer attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) in the Core Services user guide.
* **Customer support delegate:** A designated user authorized to interact directly with Adobe Customer Care. See [Customer support delegates](https://helpx.adobe.com/experience-cloud/supported-users.html) in the Experience Cloud Knowledgebase.
* **Data collection server:** Adobe-owned servers that receive and process data. Image requests are sent to Adobe's data collection servers for use in reporting.
* **Data connectors:** A complete development solution that allows a third party to automate the uploading of data into Adobe Analytics. Customers of that third party can use a data connector to enrich their data in Adobe Analytics. Most data connectors use a similar workflow used in Data Sources. See [Data Connectors](/help/import/data-connectors/data-connectors-eol.md) in the Import user guide.
* **Data feed:** A raw data export that lists every hit as a row and variables as separate columns. Most commonly used to export Adobe Analytics data to a third-party database. See [Data feeds](/help/export/analytics-data-feed/data-feed-overview.md) in the Export user guide.
* **Data sources:** Allows a user to upload data from a file into Adobe Analytics. The file is typically pulled from an FTP site. See [Data Sources](/help/import/data-sources/overview.md) in the Import user guide.
* **Data Warehouse:** A feature in Adobe Analytics that allows you to request larger reports. See [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) in the Export user guide.
* **Data Workbench:** Formerly known as Insight. Designed to collect, process, analyze, and visualize data from both online and offline customer interactions across multiple channels.
* **Dimension:** A component type that contains variable values, like text. Examples include Page Name, Tracking Code, or Referring Domain. A metric is typically its counterpart.
* **Event serialization:** The process of implementing measures to prevent the collection of duplicate events. See [Event serialization](../implement/vars/page-vars/events/event-serialization.md) in the Implement user guide.
* **eVar:** See Conversion variable.
* **Event:** See Success event.
* **ExcelClient:** No longer used as a term. The name of the predecessor of Report Builder.
* **Expiration:** In context of a conversion variable, how long the value persists on the backend. This persistence allows events to associate with variable values before the event's hit. See [Conversion variables](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Flow:** A type of visualization in Analysis Workspace that shows what paths users took on your site. See [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) in the Analyze user guide.
* **Genesis:** No longer used as a term. The former name of Data Connectors.
* **Global report suite:** An informal term designated to a report suite that collects hits from multiple sites.
* **H Code:** A predecessor to AppMeasurement. In prior versions of Adobe Analytics, code versions were measured by "H version", such as H.27.5, H.26, etc.
* **Hit:** A single image request sent to Adobe data collection servers. Page views and custom links can both be referred to as hits.
* **Image request:** A transparent 1x1 pixel image used to communicate with Adobe data collection servers. A website requests this invisible image with a long query string containing data; Adobe returns the invisible image and parses the query string received.
* **Insight:** Can refer to:
  * The former name of Data Workbench.
  * Custom Insight, a historical name for custom traffic variable.
* **KPI:** Abbreviation for key performance indicator. Metrics that help a business understand how their site is performing. Each organization has different KPI's that measure different aspects of their business. See [Create a solution design document](/help/implement/prepare/solution-design.md) in the Implement user guide.
* **Latency:** The delay between when data is collected and when it is available in reports. Typical latency in a report suite is 30-90 minutes. See [Latency](/help/technotes/latency.md) in the Technotes user guide.
* **Launch:** No longer used as a term. The shortened former name of tags in Adobe Experience Platform, Adobe's current implementation solution. See [Tags overview](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) in the Adobe Experience Platform user guide.
* **List prop:** A setting that converts a typical traffic variable to support multiple values in the same hit. Any custom traffic variable can become a list prop if the setting is enabled. See [prop](../implement/vars/page-vars/prop.md) in the Implement user guide.
* **List var:** A distinct variable separate to conversion variables. List vars support multiple values in the same hit, and variable values are preserved in a visit, similar to conversion variables. Only three list vars are available to an organization. See [list](/help/implement/vars/page-vars/list.md) in the Implement user guide.
* **Login company:** A collection of report suites used by your organization. Some organizations have multiple login companies that apply to different parts of their organization.
* **Marketing channel:** A feature in Adobe Analytics that categorizes hits by how they arrived to your site. The logic used to categorize hits can be customized using Marketing channel processing rules. See [Getting started with Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md) in the Components user guide.
* **Metric:** A component type that contains quantitative data. Metric values typically contain numbers, such as Page Views, Visits, and Revenue. A dimension is typically its counterpart.
* **Mobile Services:** Brings together mobile marketing capabilities for mobile applications from across the Adobe Experience Cloud, letting you understand and improve user engagement with your applications. See [Mobile Services overview](https://experienceleague.adobe.com/docs/mobile-services/using/home.html).
* **Multi-suite tagging:** The practice of sending the same hit to multiple report suites. With the introduction to virtual report suites, this practice is largely no longer necessary. Most multi-suite tagging efforts help accommodate a global report suite.
* **Normalization:** A way to organize a visualization that takes all metrics and forces them to equal proportions, allowing an easier comparison of trends.
* **Occurrences:** A type of metric that shows how many hits a dimension item was set or persisted. See the [Occurrences](/help/components/metrics/occurrences.md) metric in the Components user guide.
* **Omniture:** No longer used as a term. The organization that owned Adobe Analytics prior to being acquired by Adobe in 2009.
* **Pathing:** See Flow.
* **Page view:** A type of hit that increments page views. See the [Page views](/help/components/metrics/page-views.md) metric in the Components user guide. See also Hit.
* **Persistence:** An abstract concept for conversion variables that allows the linking between a variable value and event happening on separate hits. See also Expiration.
* **Primary server call:** Alternate name for image request or hit, used mostly in context of multi-suite tagging and billing. When the same hit is sent to multiple report suites, the first report suite is a primary server call while the rest are secondary server calls. This rule applies to all hit types, including page view and link tracking. See also Secondary server calls.
* **Processing rules:** Can refer to:
  * Processing rules, a way to alter data collection using certain rules in the Admin Console. See [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) in the Admin user guide.
  * Marketing channel processing rules, a set of rules that determines which marketing channel a hit belongs in. See [Marketing channel processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) in the Admin user guide.
* **Prop:** See Traffic variable.
* **Ranked report:** A report format that typically follows a dimension with a metric. This type of report allows you to see the top items, such as the most viewed pages on your site. See also Trended report.
* **Real-time:** Displays configured variables as soon as it is collected with little to no latency. See [Real-time reports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) in the Admin user guide.
* **Report Builder:** A Microsoft Excel add-in that lets you build customized requests from Adobe Analytics data.
* **Report suite:** An overarching container that you send data to. All reports in Adobe Analytics reference a report suite.
* **Reports & Analytics:** Formerly known as SiteCatalyst. Browser solution for reporting and analysis. Starter tool in the Analytics package.
* **Rolling date range:** A type of relative date range that changes as time passes. For example, a report showing the last 7 days can be considered a rolling date range. See also static date range.
* **RSID:** Abbreviation for report suite ID. A report suite has both a friendly name and a report suite ID.
* **s.t():** The name of the function in an AppMeasurement library that sends a page view image request. Some AppMeasurement libraries use `s.track()` instead. See [t](../implement/vars/functions/t-method.md) in the Implement user guide.
* **s<span>.</span>tl():** The name of the function in an AppMeasurement library that sends a link tracking image request. Some AppMeasurement libraries use `s.trackLink()` instead. See [tl](../implement/vars/functions/tl-method.md) in the Implement user guide.
* **s_code.js:** The name of the JavaScript file used in historical versions of Adobe Analytics. The current name of the JavaScript file used is AppMeasurement.js.
* **Satellite:** No longer used as a term. The former product name for Dynamic Tag Management.
* **Secondary server call:** Alternate name for image request or hit, used mostly in context of multi-suite tagging and billing. When the same hit is sent to multiple report suites, all report suites after the first listed are secondary server calls. See also Primary server calls.
* **Segment:** Allows you to focus on specific subset of your data. See [Segmentation](/help/components/segmentation/seg-overview.md) in the Components user guide.
* **Segment container:** The part of a segment that determines how much data to bring in. Containers can be based on page view, visit, or visitor. See [Segmentation](/help/components/segmentation/seg-overview.md) in the Components user guide.
* **Serialization:** See Event serialization.
* **Server call:** Alternate name for an image request or hit, used mostly in context of billing.
* **Single access:** A visit where a dimension had only a single unique value. The visit can have multiple hits, as long as there are not multiple unique values. See the [Single access](/help/components/metrics/single-access.md) metric in the Components user guide. See also Bounce.
* **SiteCatalyst:** No longer used as a term. A former product name for Adobe Analytics.
* **Solution design document:** Also known as a solution design reference, or SDR. An internal document maintained by an organization that outlines how custom variables are used, and the logic used to populate them. See [Create a solution design document](/help/implement/prepare/solution-design.md) in the Implement user guide.
* **Subrelation:** No longer used as a term; replaced with dimension breakdowns. In previous versions of Adobe Analytics, subrelations granted the ability to break down conversion variables. See [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Success event:** A tracked action a user took. Your organization determines what events to track, and which success event variables you use to track it. See [Custom events](/help/components/metrics/custom-events.md) in the Components user guide.
* **Supported user:** See Customer support delegate.
* **Traffic variable:** Also known as props. Stores a custom value for a single hit. Previous versions of Adobe Analytics gave props unique value, but improvements to the platform make custom traffic variables largely unnecessary. Adobe recommends using custom conversion variables (eVars) in most cases. See the [Prop](/help/components/dimensions/prop.md) dimension in the Components user guide.
* **Trended report:** A report format that typically shows multiple date ranges with a metric. This type of report allows you to see how a metric performs over time. See also Ranked report.
* **Unique visitor**: Represents the number of unique individuals that have visited your site. A single unique visitor can have multiple visits. See the [Unique visitors](/help/components/metrics/unique-visitors.md) metric in the Components user guide.
* **Virtual report suite:** A virtual container of data that references a regular report suite and allows the refinement of data. Data is not sent to a virtual report suite; instead, data is sent to a regular report suite, and a virtual report suite builds off of that data collected. See [Virtual report suites](/help/components/vrs/vrs-about.md) in the Components user guide.
* **Visit:** Represents the number of unique sessions that have taken place on your site. See the [Visits](/help/components/metrics/visits.md) metric in the Components user guide.
* **VISTA rule:** Custom logic created by Adobe at a customer's request to copy, parse, or filter data server-side. VISTA rules typically incur additional costs. See also Processing rules.
* **Web beacon:** See Image request.
