---
description: Data source categories identify different data source types that provide similar functionality.
subtopic: Data sources
title: Overview of data types and categories
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
---
# Overview of data types and categories

Data source categories identify different data source types that provide similar functionality.

Categories provide a way to group data sources from a user's perspective. When creating a data source through the [!DNL Data Sources] UI, first select a data source category, then a specific data source type. Each category contains types of data sources that support similar types of data. [!DNL Data Sources] provides the following data source categories:

## Web Site Usage {#web-usage}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Web Server Log Files] | [Web Log](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | Most Web servers generate log files that record every page served. Using this data source, you can process the log files from most Web server data and add this data to your reports. |
| [!UICONTROL Advertising Cloud Bulk Upload] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) |Provides manual and Excel-automated bulk uploads in [!DNL Advertising Cloud]. |
| [!UICONTROL Site-level Traffic Data Source] | [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) |Imports Traffic data for your entire Web site. For example, [!UICONTROL Page Views]. |
| [!UICONTROL Breakdown Traffic Data Source] | [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) |Imports Traffic data broken down by another Web site variable. For example, [!UICONTROL Page Views] broken down by [!UICONTROL Product]. |

## Ad Campaigns {#ad-campaigns}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Generic Ad Server] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you integrate impressions and other top-line metrics about your ad serving activities from your ad server into marketing reports. This is the generic ad server data source and should be used if your specific ad server is not supported. |
| [!UICONTROL Generic Email Campaign Server] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you integrate metrics from your email campaign server into marketing reports.  Commonly incorporated metrics include the number of messages sent, messages delivered and messages read. This is the generic email campaign data source and should be used if your specific email campaign server is not supported. |
| [!UICONTROL Generic Pay-Per-Click Service] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you import data about your pay-per-click performance including impressions, clicks, and costs.  This is the generic pay-per-click data source and should be used if your specific pay-per-click service is not supported. |

## Customer Relationship Management (CRM) {#crm}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Generic Call Center] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you integrate information about your call center into marketing reports. Metrics more commonly imported include the number of calls, time on the phone, the agent, and total sales.  This data source is the generic call center data source and should be used if your specific call center software is not supported. |
| [!UICONTROL Generic Customer Support Application] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you integrate information from your customer support software into marketing reports. It includes metrics such as the number of new incidents, number of incidents resolved, and the time spent resolving incidents.  This is the generic customer support data source and should be used if your specific customer service application is not supported. |

## Customer Satisfaction {#csat}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Generic Survey Data] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you integrate survey results from a third-party tool into marketing reports, and show how satisfied customers are by their interactions with your site.  This is the generic survey data source and should be used if your specific survey data service is not supported. |

## Site Performance {#performance}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Generic Site Download Speed] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you integrate data from an application or service that tracks the speed of your downloads with your data. This is the generic download speed data source and should be used if your specific download speed software or service is not supported. |

## Generic {#generic}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Generic Data Source (Summary Data Only)] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Use this data source when there is no closer match to the type of data you want to import into marketing reports and analytics. |
| [!UICONTROL Generic Data Source (Full Processing)] | Full Processing | Adobe deprecated full processing data sources on January 31, 2022. [Learn more](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Adobe recommends that you use the [Bulk Data Insertion API (BDIA](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) instead. |
| [!UICONTROL Generic Data Source (Transaction ID)] | <ul><li>Transaction ID</li><li>Visitor ID</li></ul> | Lets you tie any offline event to an online event. The [!UICONTROL Transaction ID] acts as a key between the offline and online events. |

## Online Purchases {#purchases}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Product Returns] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you import product return data to associate with a purchase ID so you can identify search engines, keywords, campaigns and other attributes that are more likely to generate returns. |
| [!UICONTROL Product Cost] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you provide the actual cost of products purchased and shipped from your Web site by associating cost or profit with individual products so you can accurately report on the most profitable campaigns, keywords and internal promotions for your Web site. |
| [!UICONTROL Order Status] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you use metrics to identify the status of every order made, including orders canceled, shipped, completed, or deemed fraudulent. Order status reporting can identify which acquisition methods generate the highest order completion rate. |

## Leads and Quotes {#leads}

| Data Source | Processing Type | Description |
| --- | --- | --- |
| [!UICONTROL Lead Generation] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you upload information about the results of the leads for every lead generated on your Web site, including actual revenue generated.  After revenue is accurately attributed to lead IDs, you can identify your most profitable campaigns and promotions. |
| [!UICONTROL Online Quote] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you upload information about the results of the leads for every lead generated on your Web site, including actual revenue generated.  After revenue is accurately attributed to lead IDs, you can identify your most profitable campaigns and promotions. |
| [!UICONTROL Call Center Data] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Lets you upload call center transactions so you can identify the tactics (campaigns, promotions, and so on.) that lead customers to pick up the phone. |
