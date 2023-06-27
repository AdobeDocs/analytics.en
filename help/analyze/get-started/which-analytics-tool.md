---
description: This help page contains recommended use cases for each Adobe Analytics tool. Tools should be considered in the order they are listed. If a certain tool does not meet the need, move to the next one for consideration.
title: Which Adobe Analytics tool should I use?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
---
# Which Adobe Analytics tool should I use?

This help page contains recommended use cases for each Adobe Analytics tool. Tools should be considered in the order they are listed. If a certain tool does not meet the need, move to the next one for consideration.

For more on Adobe Analytics Product Comparisons, see [Analytics product comparison](/help/analyze/get-started/analytics-product-comparison.md).

Here is a video that compares various Adobe Analytics tools:

>[!VIDEO](https://video.tv.adobe.com/v/27220/?quality=12)

## Adobe Analytics Reporting User Interfaces {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** should be the go-to user interface for all of your reporting and analysis needs. Adobe continues to invest in and release monthly updates to this product. If there is a task you cannot do in Analysis Workspace, consider the other interfaces below.**

**[Reports & Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** should be used:

* By beginner users who need access to pre-built reporting that is easier to navigate.
* To access real-time data in the UI.
* To set up Calendar events.
* To set up Targets.
* To view Bot reporting.
* To access unique Video visualizations of Video Daypart and Viewer Drop-off.

**[Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html)** should be used:

* As the most flexible Analytics tool option (down to visitor-level, hit-level analysis).
* To create a multi-channel dataset of online and offline interactions from CRM to POS to Web.
* For advanced attribution (rules-based & algorithmic models).
* For predictive, statistical modeling (propensity scoring, clustering, correlations, etc.).
* For Latency analysis (time before / since an event).
* For identification and export of complex segments throughout Adobe Experience Cloud.

## Importing Data into Adobe Analytics {#import}

**[Classifications](/help/components/classifications/c-classifications.md)** should be used:

* When there is metadata you want to associate to a collect value (eVar, prop, marketing channel)
* Options:

  * Rule builder: use when you have predictable formatted-values being collected for a variable, e.g. delimited values. This approach allows you to set up rules once and largely "set-it and forget-it".
  * Browser importer: use when you don't have predictable values, or when you have a finite list of values that requires a one-time update. This approach requires that you do ongoing monitoring of the classifications for new values.

**[Data Sources](/help/import/data-sources/overview.md)** should be used:

* When there is offline data you want permanently written into Adobe Analytics
* Options:

  * Summary: simple data uploads, by day or limited dimensions
  * Transaction ID: data uploads that connect an online endpoint to offline data, and fully associate imported data to a visitor snapshot captured online (e.g. orders complete online, and get returned offline)
  * Full Processing: time-stamped data sources, processed as if it was a hit collected by Adobe servers. I.e. data gets inserted directly into the visitor journey.

**[Adobe Exchange integrations](https://www.adobeexchange.com/experiencecloud.html)** should be used:

* When you engage with a 3rd-party provider that has built a supported connection with Adobe Analytics. Integration apps typically incorporate summary-level data into Adobe Analytics permanently and automatically, on a recurring basis.

**[Data Insertion API](/help/import/c-data-insertion-api/c-data-insertion-api.md)** should be used:

* When you need to upload data into Adobe Analytics, and cannot use the Adobe AppMeasurement or mobile SDK code.

**[Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* Data Insertion API and Bulk Data Insertion API are both methods to submit server-side collection data to Adobe Analytics. Data Insertion API calls are made one event at a time. Bulk Data Insertion API accepts CSV formatted files containing event data, one event per row. If you are working on a new implementation of server-side collection, we recommend using Bulk Data Insertion API.

**[Customer Attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html)** should be used:

* If you capture enterprise customer data in a customer relationship management (CRM) database and want to upload the data to the Experience Cloud.
* If you want to use CRM data for deeper analysis in Analytics, or as targeting criteria in Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** should be used:

* If you want to incorporate Adobe Audience Manager audience data such as demographic information (e.g. gender or income level), psychographic information (e.g. interests and hobbies), CRM data, or ad impression data into any Analytics workflow.
* If you want uploaded CRM data to be time based, because this integration sends new information to Analytics hit by hit.

## Exporting Data from Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/home.md)** should be used:

* If the customized layout options of Workspace are limiting (anything is possible in Report Builder, within the limits of Excel).
* To loosely tie in user inputs or offline data sources (impressions, cost) to Adobe data. More permanent solution for tying in data is Data Sources (see Importing Data to Analytics).
* To merge data together from different dimensional reports (e.g. promo impressions report joined with promo click-to-conversion report).
* To merge data together from different report suites, either by summing or displaying in the same table side-by-side.
* If automation through scheduling is desired (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** should be used:

* To access variables otherwise hidden in the UI - IP address, Experience Cloud ID, Analytics Visitor ID, Page URL) 
* To access more granular data than the UI (denormalized table view) 
* To download data in a format suitable for a Pivot Table input 
* If the client wants to input Adobe data into a 3rd-party data visualization tool (slightly summarized, and not hit-level) 
* To access all unique dimension items if you are running into "Low Traffic" in Adobe Analytics

**[Analytics Data Feed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** should be used:

* To utilize the most granular data feed we can provide (visitor ID, hit).
* If the client wants Adobe data stored in a client-side database, at the most granular level we can send.
* If the client wants to develop a Business Intelligence (BI) tool or input hit-level Adobe data into a 3rd-party tool.

**[Reporting APIs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** should be used when the other visualization options do not meet your needs. The 3 API options include:

* **Fully Processed**: when you want feature-rich data (including visits, visitors, and segments). This is typical Analytics UI summarized data, available within ~30-90 minutes. Can be used through Report Builder.
* **Real-Time**: when you want to view a few metrics and dimensions with seconds of latency. This is limited, partially processed, summarized data that is available within ~30 seconds. Includes unique algorithms of most popular, gainers, and losers. Can be used through Report Builder.
* **[!UICONTROL Live Stream]**: when you want a stream of partially-processed hit-level Analytics data within seconds of collection. This is partially processed data, available within ~30 seconds. Available for Analytics Premium only. Requires some way to visualize the data, typically through an Engineering Services engagement.

## Custom Solutions {#custom-solutions}

Engineering Services should be used when:

* The other Adobe tools don't meet your needs.
* You want a custom experience.
* You want a fully automated solution.
* You want to reach many devices.
* You have multiple data sources.
* You have complex data ETL (Extract-Transform-Load) requirements.
* You want custom branding.
* You want to visualize [!UICONTROL Analytics Live Stream].
