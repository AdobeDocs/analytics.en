---
description: Add offline data to Marketing Channel reports.
seo-description: Add offline data to Marketing Channel reports.
seo-title: Add offline data
solution: Analytics
subtopic: Marketing channels
title: Add offline data
topic: Reports and analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
---

# Add offline data

Add offline data to Marketing Channel reports.

Online Channels let you categorize data for visitors who come through sources like a search engine, Internet ad, referring domain, or email campaign. Offline Channels apply to visitors who found your site through television ads, newspapers, or magazine advertisements.

**Integrate data sources into Marketing Channel reports**

If you want to integrate [data sourced data](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_faq) into Marketing Channel reports, keep in mind the following:

* Any standard hits passed in to analytics reports with a [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID) are processed through marketing channel processing rules as normal. 
* Any `transactionID` data sources passed into analytics are automatically associate with the same marketing channel on which the standard hit was processed. 
* Any other data sourced data does not go through marketing channel processing rules.

See [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html) help for more information about Data Sources.

To classify offline channel data, activate the data in Data Sources, then download and edit the template.

See "Working with Data Sources" in the [Data Sources User Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

**Add offline data** 

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Data Sources]**.
1. On the Data Sources page, click **[!UICONTROL Create.]**
1. Under **[!UICONTROL 1. Select Category]**, select **[!UICONTROL Offline Channel Data]**.
1. Under **[!UICONTROL 2. Select Type]**, select **[!UICONTROL Offline Channel Data]**.
1. Click **[!UICONTROL Activate.]**
1. Map offline metrics to reporting metrics by following the prompts on the Data Source Activation Wizard.
1. Download and edit the template file in an editor, such as Excel.

   See "Creating a Data Sources File" in the [Data Sources User Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html). 

1. Upload the file as described in "Uploading a Data Sources File" in the [Data Sources User Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).
