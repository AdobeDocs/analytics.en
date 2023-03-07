---
description: This topic provides answers to common questions.
subtopic: Data sources
title: Data Sources FAQ
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 2a5d38fe-5c5b-4275-bc44-e9cb02ec2f5d
---
# Data Sources FAQ

This topic provides answers to common questions.

## How can we tie offline data to online events? {#offline}

For transaction ID data sources to tie offline data to online events, you must enable Transaction ID Recording. See [Transaction ID Recording](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) for more information.

## How much does it cost to use the Data Source feature? {#cost}

Data Sources does not carry any additional fees beyond the standard server call. Server call charges apply only to full-processing data source types, where individual hits are sent in as rows of data. Traffic and aggregate level data sources do not incur additional costs.

## How do I include comments in Data Sources files? {#comments}

Each row in a Data Sources file that begins with a pound sign (#) is treated as a comment.

## Do I have to include a date column in my spreadsheet data? {#date}

Yes. Because many marketing reports are keyed from the date column, Data Sources requires a date column.

## Can I store data in existing variables that I'm already using? {#variables}

Adobe recommends you select new, unused variables to import data using Data Sources. If you are uncertain about the configuration of your data file, or want to better understand the risks of re-using variables, contact Customer Care.

## Can I delete data that was imported using Data Sources? {#imported}

No. Data uploaded into reports using Data Sources cannot be removed, even by Adobe technicians, once it has been imported. It is inserted into your existing data permanently, and becomes indistinguishable from your data entered through traditional data collection means (i.e. JavaScript, ActionSource, Data Insertion API, etc.). Therefore, Adobe strongly recommends uploading Data Sources data into a test report suite before uploading into a production suite.

## How much data can I import at a time? {#amount}

Processing pauses if the size exceeds 50 MB and does not resume until the total is below 50 MB. To limit delays in generating reports, do not upload more than 90 days of data per day.

## When I import data through Data Sources, is the existing data overwritten? {#overwrite}

Data Sources data never overwrite existing report data. Instead, data uploaded using Data Sources is added to the existing data.

## When I upload my data via Data Sources, why don't I get my metrics as well? {#metrics}

When you upload Data Sources data, you are uploading the metrics that will be available in the report interface.

For example, if you are uploading Call Center Revenue for products you sell on your site, you can have that Call Center Revenue in the same report as Online Revenue. However, you will not be able to use it in conjunction with Visits, because you didn't upload the number of Visits with it. Adobe can only report on the metrics and elements that you uploaded through Data Sources (in addition to the regular marketing report metrics).

## What happens if I pass negative values into reporting through Data Sources? {#negative}

The value is decreased accordingly.

## What is the difference between a Traffic and a Conversion (Generic) Data Source? {#traffic}

The Traffic Data Source uploads much faster since it merely updates the summary values into the appropriate tables. The Generic Data Source with conversion data (events etc.) creates a hit for every value in the column to be processed.

Sample file: 

<table id="table_D5408E0BDB984229B4C60A66BB53CEBB"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Date </code> </p> </td> 
   <td colname="col2"> <p> <code> Event15 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 01/01/2013 </code> </p> </td> 
   <td colname="col2"> <p> <code> 553 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

The example above creates 553 hits to be processed in the cache system.

## Does Data Sources take subrelations, correlations, and pathing into account? {#breakdown}

Since the Data Source process ("for Generic DS, non-Traffic") builds individual hits that are processed by cache, the subrelation process is used, but not the correlation process. Pathing has the potential to be processed, but each hit would be its own visit, so no pathing is generated. Pathing data is generated for Web log imports.

## Are the file extensions case-sensitive for a Data Source upload or a classification file? {#case}

If the extensions of a Data Source upload file or a classification file are capitalized, the files will not be processed. Data Source upload file extensions must be lowercase. For example, [!DNL file.TXT] and [!DNL file.FIN] will not be processed. Similarly, [!DNL .TAB] and [!DNL .FIN] will not be processed. However, [!DNL .txt] and [!DNL .fin] are processed.

## Can I add additional events to the generated template or am I limited to three? {#template}

You can add in as many events as you like. However, the wizard allows for only three events only. Once the template file is created you can add in more events as needed.

## What happens to a Data Source file where one or more of the records do not have the same number of columns as the header record? {#header}

If you have a Data Source file where one or more of the records do not have the same number of columns as the header record, the following will occur.

* An email is sent to the creator of the data source, notifying them of an error.
* The file is not processed due to column mismatch.

## Is Data Sources information rolled up? {#rollup}

Data Sources information can be rolled up; however, Adobe Customer Care must reprocess the rollup from the historical date to include the historical data. For example, if the current date is 31 October 2015 and you upload data for 1-15 August 2015 using Data Sources, the rollup must be set to reprocess beginning with 1 August 2015, so that the newly imported data is included.

Also note that data should never be uploaded directly into a rollup report suite using Data Sources. If you need this data included in a rollup, it should be imported into a standard report suite, also called a *`child suite`* to the rollup. Contact Adobe Customer Care for more information.

## Why does the Page Views Report not show any Data Sources data for a single day, but it shows the correct data for a week? {#week}

Data Sources does not report data on an hourly basis. When you try to run a report for a particular day, the data can be broken down only by the hour so nothing shows in the report. You can see data only when it is broken down by a level of granularity of daily or higher, which can be accomplished by running a weekly or a monthly report.

## How are Unique Visitors calculated in a web server log Data Source upload? {#unique}

The number of Unique Visitors in a web-server log is calculated as the different distinct combinations of *`IP Address`* and *`User Agent`* in the Web log. Each unique combination of these two items is calculated as a Unique Visitor. If the [!UICONTROL User Agent] column is blank (or not included in the web log) then we are unable to identify Unique Visitor counts, and the entire upload will count as just one Unique Visitor (even if there are multiple IP addresses).

## In Data Sources, how can I tell which login belongs to which report suite? {#login}

In Data Sources, the report suite ID is the first part of the login appended by a random number that identifies the specific data source that was set up. For example, `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## How does version 15 and segmentation impact data sources? {#segmentation}

In version 15, Data Sources behave differently based on the source type:

* Full processing, web log, and transaction ID data sources appear as normal. When segments are applied, the data is filtered according to the segment rules.
* Standard or conversion data sources (ad campaigns, CRM, customer satisfaction, site performance, generic summary data, online purchases, leads and quotes, and offline channel data) appear in version 15. However, because those data sources are not tied to visits or visitors, they are filtered out when segments are applied.

## Are metrics that are imported using a transaction ID available in Clickstream data feeds and data warehouse? {#clickstream}

The data feed contains any transaction ID metrics that have been received. However, if you upload transaction ID data for a date in the past, the only way to get that data is to download the data feed again for that day.

## Are eVars that are currently persisting in the Visitor Profile allocated to metrics uploaded using data sources? {#visitor}

No for full processing, yes for transaction ID. Full processing data sources are processed using separate visitor profiles, so even if the visitor IDs match, they won't be tied to together from an eVar allocation perspective. Transaction ID data sources are tied to the main visitor profile, so persisting eVars are allocated to events uploaded using transaction ID.

## Do eVars uploaded using data sources persist to later online behavior? {#evars}

No. eVars uploaded via Transaction ID data sources will only read from the stored profile info, not update the profile.
No. eVars are the only variables that are saved in the snapshot of the visitor profile.

## How do numeric and currency events work with data sources? {#numeric}

Full processing only supports legacy event list formats excluding the numeric/currency/Counter (more than 1) event value directly in the events list, that is `"eventNN,eventKK"` not `"eventNN=#.##"`. It means that it only supports a counter event if it is passed in events column in data source file and it increments by 1.

If numeric, currency or counter (more than 1) events are required, use the product list:

```js

s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";

```

## Why is my ftp upload not getting picked up?

After the .fin file is uploaded, it’s important that you log out of the Data Sources FTP site. The reason is that Analytics uses logout events as a trigger to indicate that files are ready for processing. If you are programmatically uploading the files, it is important that your automated process also logs out of the FTP site after the files have been uploaded.

Verify that your filenames follow the correct format. Leading or trailing whitespace in the filename causes the file to go unrecognized and to not be picked up by the Adobe ingestion process. 
