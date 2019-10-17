---
description: Data source categories identify different data source types that provide similar functionality.
seo-description: Data source categories identify different data source types that provide similar functionality.
seo-title: Overview of data types and categories
solution: Analytics
subtopic: Data sources
title: Overview of data types and categories
topic: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
---

# Overview of data types and categories

Data source categories identify different data source types that provide similar functionality.

Categories provide a way to group data sources from a user’s perspective. When creating a data source through the Data Sources UI, first select a data source category, then a specific data source type. Each category contains types of data sources that support similar types of data. Data Sources has the following data source categories:

## Web Site Usage {#section_4BA8D97B6BA848518F21760AE49F41D1}

<table id="table_2562E7A400214B8F9BB9177D210348F4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Web Server Log Files </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md"   > Web Log </a> </p> </td> 
   <td colname="col3"> <p>Most Web servers generate log files that record every page served. Using this data source, you can process the log files from most Web server data and add this data to your reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Cloud Bulk Upload </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Provides manual and excel-automated bulk uploads in Advertising Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-level Traffic Data Source </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md"   > Traffic </a> </p> </td> 
   <td colname="col3"> <p>Imports Traffic data for your entire Web site. For example, Page Views. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Breakdown Traffic Data Source </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md"   > Traffic </a> </p> </td> 
   <td colname="col3"> <p>Imports Traffic data broken down by another Web site variable. For example, Page Views by Product. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ad Campaigns {#section_9AE27E347CFC48F29E7C1134B6E928A6}

<table id="table_2A297A86CC3E4B1E8B72389AA148549A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generic Ad Server </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you integrate impressions and other top-line metrics about your ad serving activities from your ad server into marketing reports. This is the generic ad server data source and should be used if your specific ad server is not supported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generic Email Campaign Server </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you integrate metrics from your email campaign server into marketing reports. </p> <p>Commonly incorporated metrics include the number of messages sent, messages delivered and messages read. This is the generic email campaign data source and should be used if your specific email campaign server is not supported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generic Pay-Per-Click Service </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p> Lets you import data about your pay-per-click performance including impressions, clicks, and costs. </p> <p>This is the generic pay-per-click data source and should be used if your specific pay-per-click service is not supported. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Relationship Management (CRM) {#section_013A1C5D3CAD4CCEAD22C2FDD26715A0}

<table id="table_5895659CAB2C415AB2AA59A2E6C75AD1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generic Call Center </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you integrate information about your call center into marketing reports. Metrics more commonly imported include the number of calls, time on the phone, the agent, and total sales. </p> <p>This data source is the generic call center data source and should be used if your specific call center software is not supported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Generic Customer Support </p> <p>Application </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you integrate information from your customer support software into marketing reports. It includes metrics such as the number of new incidents, number of incidents resolved, and the time spent resolving incidents. </p> <p>This is the generic customer support data source and should be used if your specific customer service application is not supported. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Satisfaction {#section_1058CA3860044630B0B06EEDA261DBA2}

<table id="table_3811CA1E2B7C45D7A0CBEC5CE44C11A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generic Survey Data </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you integrate survey results from a third-party tool into marketing reports, and show how satisfied customers are by their interactions with your site. </p> <p>This is the generic survey data source and should be used if your specific survey data service is not supported. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Site Performance {#section_3A7BECB0B4B247FB991DC59237ECFE1F}

<table id="table_7B623D08275E4FDEADDD85EA89A2B7C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generic Site Download Speed </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you integrate data from an application or service that tracks the speed of your downloads with your data. </p> <p>This is the generic download speed data source and should be used if your specific download speed software or service is not supported. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generic {#section_9B9A2A9871894B6491032AE1E961629A}

<table id="table_D63A6A00C93A4CD48FEBE7BC24E5DA9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Generic Data Source (Summary Data Only) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Use this data source when there is no closer match to the type of data you want to import into marketing reports and analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generic Data Source (Full Processing) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Full Processing </a> </p> </td> 
   <td colname="col3"> <p>Lets you import log file data. This data is processed as if it were received by data collection servers at the time specified (each hit receives a timestamp). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Generic Data Source (Transaction ID) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md"   > Transaction ID </a> </p> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md"   > Visitor ID </a> </p> </td> 
   <td colname="col3"> <p>Lets you tie any offline event to an online event. The transaction ID acts as a key between the offline and online events. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Online Purchases {#section_2B2D4DBB045548C3A5DC7DEF81BA56D1}

<table id="table_EE450D955D4C4264A40142AF6D74F1AA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product Returns </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you import product return data to associate with a purchase ID so you can identify search engines, keywords, campaigns and other attributes that are more likely to generate returns. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product Cost </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you provide the actual cost of products purchased and shipped from your Web site by associating cost or profit with individual products so you can accurately report on the most profitable campaigns, keywords and internal promotions for your Web site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Order Status </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you use metrics to identify the status of every order made, including orders canceled, shipped, completed, or deemed fraudulent. </p> <p>Order status reporting can identify which acquisition methods generate the highest order completion rate. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Leads and Quotes {#section_0B3EAA59BEC94244BE3EB3825D719DF6}

<table id="table_85B095414F6C4644A191A94AC0CAD13D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data Source </p> </th> 
   <th colname="col2" class="entry"> <p>Processing Type </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lead Generation </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you upload information about the results of the leads for every lead generated on your Web site, including actual revenue generated. </p> <p>After revenue is accurately attributed to lead IDs, you can identify your most profitable campaigns and promotions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Online Quote </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you upload information about the results of the leads for every lead generated on your Web site, including actual revenue generated. </p> <p>After revenue is accurately attributed to lead IDs, you can identify your most profitable campaigns and promotions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Call Center Data </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversion </a> </p> </td> 
   <td colname="col3"> <p>Lets you upload call center transactions so you can identify the tactics (campaigns, promotions, and so on.) that lead customers to pick up the phone. </p> </td> 
  </tr> 
 </tbody> 
</table>

