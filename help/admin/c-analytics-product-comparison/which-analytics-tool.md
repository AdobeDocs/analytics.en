---
description: This help page contains recommended use cases for each Adobe Analytics tool. Tools should be considered in the order they are listed. If a certain tool does not meet the need, move to the next one for consideration.
title: Which Adobe Analytics tool should I use?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
---

# Which Adobe Analytics tool should I use?

This help page contains recommended use cases for each Adobe Analytics tool. Tools should be considered in the order they are listed. If a certain tool does not meet the need, move to the next one for consideration.

For more on Adobe Analytics Product Comparisons, go [here](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Adobe Analytics Reporting User Interfaces {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** should be the go-to user interface for all of your reporting and analysis needs. Adobe continues to invest in and release monthly updates to this product. If there is a task you cannot do in Analysis Workspace, consider the other interfaces below.**

**[Reports & Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** should be used:

* By beginner users who need access to pre-built reporting that is easier to navigate.
* To understand Target activity (Analytics for Target/A4T) lift and confidence.
* To access real-time data in the UI.
* To set up Calendar events.
* To set up Targets.
* To view Bot reporting.
* To look at multiple report suites in a single UI dashboard.
* To access unique Video visualizations of Concurrent Viewer, Video Daypart, and Viewer Drop-off.
* To leverage Publishing Lists in scheduled reporting .

**[Mobile Services UI](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)** should be used:

* If a siloed view of Mobile App data is desired.
* To manage the implementation of your mobile app SDK.
* To set up mobile advertising, such as in-app messaging, push messaging, and location targeting.
* If more interactive visualizations are desired for App data (Sunburst).
* To visualize points of interest on a map.
* For Lifetime value metrics.

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)** should be used:

* To export 50,000 rows of data 
* If tab organization of project work is desired.
* To use the Site Analysis report (3D-pathing report).

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)** should be used:

* As the most flexible Analytics tool option (down to visitor-level, hit-level analysis).
* To create a multi-channel dataset of online and offline interactions from CRM to POS to Web.
* For advanced attribution (rules-based & algorithmic models).
* For predictive, statistical modeling (propensity scoring, clustering, correlations, etc.).
* For Latency analysis (time before / since an event).
* For identification and export of complex segments throughout Adobe Experience Cloud.

## Importing Data into Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Classifications](/help/components/c-classifications2/c-classifications.md)** should be used:

* When there is metadata you want to associate to a collect value (eVar, prop, marketing channel) 
* Options:

    * Rule builder: use when you have predictable formatted-values being collected for a variable, e.g. delimited values. This approach allows you to set up rules once and largely "set-it and forget-it".
    * Browser importer: use when you don't have predictable values, or when you have a finite list of values that requires a one-time update. This approach requires that you do ongoing monitoring of the classifications for new values.

**[Data Sources](/help/import/c-data-sources/datasrc-home.md)** should be used:

* When there is offline data you want permanently written into Adobe Analytics 
* Options:

    * Summary: simple data uploads, by day or limited dimensions 
    * Transaction ID: data uploads that connect an online endpoint to offline data, and fully associate imported data to a visitor snapshot captured online (e.g. orders complete online, and get returned offline) 
    * Full Processing: time-stamped data sources, processed as if it was a hit collected by Adobe servers. I.e. data gets inserted directly into the visitor journey.

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(formerly known as Genesis)** should be used:

* When you engage with a 3rd-party provider that has built a supported connection with Adobe Analytics. Data Connectors typically incorporate summary-level data into Adobe Analytics permanently and automatically, on a recurring basis.

**[Data Insertion API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)** should be used:

* When you need to upload data into Adobe Analytics, and cannot use the Adobe AppMeasurement or mobile SDK code.

**[Customer Attributes](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)** should be used:

* If you capture enterprise customer data in a customer relationship management (CRM) database and want to upload the data to the Experience Cloud.
* If you want to use CRM data for deeper analysis in Analytics, or as targeting criteria in Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** should be used:

* If you want to incorporate Adobe Audience Manager (AAM) audience data such as demographic information (e.g. gender or income level), psychographic information (e.g. interests and hobbies), CRM data, or ad impression data into any Analytics workflow.
* If you want uploaded CRM data to be time based, because this integration sends new information to Analytics hit by hit.

## Exporting Data from Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)** should be used:

* If the customized layout options of Workspace are limiting (anything is possible in Report Builder, within the limits of Excel).
* To loosely tie in user inputs or offline data sources (impressions, cost) to Adobe data. More permanent solution for tying in data is Data Sources (see Importing Data to Analytics).
* To merge data together from different dimensional reports (e.g. promo impressions report joined with promo click-to-conversion report).
* For cross-report-suite views.
* If automation through scheduling is desired (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** should be used:

* To access variables otherwise hidden in the UI - IP address, Experience Cloud ID, Analytics Visitor ID, Page URL) 
* To access more granular data than the UI (denormalized table view) 
* To download data in a format suitable for a Pivot Table input 
* If the client wants to input Adobe data into a 3rd-party data visualization tool (slightly summarized, and not hit-level) 
* To access all unique dimension values if you are running into "Low Traffic" in Adobe Analytics

**[Analytics Data Feed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** should be used:

* To utilize the most granular data feed we can provide (visitor ID, hit).
* If the client wants Adobe data stored in a client-side database, at the most granular level we can send.
* If the client wants to develop a Business Intelligence (BI) tool or input hit-level Adobe data into a 3rd-party tool.

**[Reporting APIs](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)** should be used when the other visualization options do not meet your needs. The 3 API options include:

* **Fully Processed**: when you want feature-rich data (including visits, visitors, and segments). This is typical Analytics UI summarized data, available within ~30-90 minutes. Can be used through Report Builder.
* **Real-Time**: when you want to view a few metrics and dimensions with seconds of latency. This is limited, partially processed, summarized data that is available within ~30 seconds. Includes unique algorithms of most popular, gainers, and losers. Can be used through Report Builder.
* **[!UICONTROL Live Stream]**: when you want a stream of partially-processed hit-level Analytics data within seconds of collection. This is partially processed data, available within ~30 seconds. Available for Analytics Premium only. Requires some way to visualize the data, typically through an Engineering Services engagement.

## Custom Solutions {#section_4A212F26A15947599DFB0399A0440CB6}

Engineering Services should be used when:

* The other Adobe tools don't meet your needs.
* You want a custom experience.
* You want a fully automated solution.
* You want to reach many devices.
* You have multiple data sources.
* You have complex data ETL (Extract-Transform-Load) requirements.
* You want custom branding.
* You want to visualize [!UICONTROL Analytics Live Stream].
