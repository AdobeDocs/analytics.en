---
description: This help page contains recommended use cases for each Adobe Analytics tool. Tools should be considered in the order they are listed. If a certain tool does not meet the need, move to the next one for consideration.
title: Which Adobe Analytics tool should I use?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
---
# Which Adobe Analytics tool should I use?

This help page contains recommended use cases for each Adobe Analytics tool. Tools should be considered in the order they are listed. If a certain tool does not meet the need, move to the next one for consideration.

For more on Adobe Analytics Product Comparisons, see [Analytics product comparison](/help/analyze/get-started/analytics-product-comparison.md).


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparison of tools](https://video.tv.adobe.com/v/27220?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Adobe Analytics reporting user interfaces {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** should be the go-to user interface for all of your reporting and analysis needs. Adobe continues to invest in and release monthly updates to this product. If there is a task you cannot do in Analysis Workspace, consider the other interfaces below.**

**[Adobe Analytics Dashboards](/help/analyze/mobile-app/home.md)** allows users mobile access to intuitive scorecards. Scorecards are a collection of key metrics and other components presented in a tiled layout that you can tap for more detailed breakdowns and trended reports. The mobile app is supported on both iOS and Android operating systems.

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** is an add-in for Microsoft Excel that runs on Mac, Windows, and web browsers. It lets you build customized requests from Adobe Analytics data, which you can insert into your Excel worksheets. Requests can dynamically reference cells within your worksheet, and you can update and customize how Report Builder presents the data.

**[Legacy Report Builder](/help/analyze/legacy-report-builder/home.md)** is an add-in for Microsoft Excel that runs on Windows only. It lets you build customized requests from Adobe Analytics data, which you can insert into your Excel worksheets. Requests can dynamically reference cells within your worksheet, and you can update and customize how Report Builder presents the data.

**[Activity Map](/help/analyze/activity-map/overview.md)** is a feature within Adobe Analytics that provides a visual representation of user engagement on web pages and mobile apps. It enables marketers and analysts to track and analyze user interactions such as clicks, hovers, and scrolling behavior. 

## Importing data into Adobe Analytics {#import}

**[Classifications](/help/components/classifications/classifications-overview.md)** should be used:

* When there is metadata you want to associate to a collect value (eVar, prop, marketing channel). Adobe recommends using [Classification sets](/help/components/classifications/sets/overview.md). The classification rule builder and classification importer are legacy methods to bring classification data in to Adobe Analytics.

**[Data Sources](/help/import/data-sources/overview.md)** should be used:

* When there is offline data you want permanently written into Adobe Analytics
* Options:
  * Summary: simple data uploads, by day or limited dimensions
  * Transaction ID: data uploads that connect an online endpoint to offline data, and fully associate imported data to a visitor snapshot captured online (e.g. orders complete online, and get returned offline)

**[Adobe Exchange integrations](https://www.adobeexchange.com/experiencecloud.html)** should be used:

* When you engage with a 3rd-party provider that has built a supported connection with Adobe Analytics. Integration apps typically incorporate summary-level data into Adobe Analytics permanently and automatically, on a recurring basis.

**[Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* The Bulk Data Insertion API accepts CSV formatted files containing event data, one event per row. Adobe recommends using the Bulk Insertion API for any implementation that requires server-side code or otherwise cannot use AppMeasurement or the Web SDK for data collection.

**[Data Insertion API (Legacy)](/help/import/c-data-insertion-api/c-data-insertion-api.md)** should be used:

* When you need to bring data into Adobe Analytics and cannot use AppMeasurement, Web SDK, or the Bulk Data Insertion API.

**[Customer attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html)** should be used:

* If you capture enterprise customer data in a customer relationship management (CRM) database and want to upload the data to the Experience Cloud.
* If you want to use CRM data for deeper analysis in Analytics, or as targeting criteria in Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** should be used:

* If you want to incorporate Adobe Audience Manager audience data such as demographic information (e.g. gender or income level), psychographic information (e.g. interests and hobbies), CRM data, or ad impression data into any Analytics workflow.
* If you want uploaded CRM data to be time based, because this integration sends new information to Analytics hit by hit.

## Exporting Data from Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** should be used:

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
