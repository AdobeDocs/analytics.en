---
title: Import Paid Search metrics
description: Steps to configure Adobe Analytics to track your paid search metrics (e.g., Google AdWords, MSN, Yahoo, etc.) using Data Sources.
---

# Import [!UICONTROL Paid Search metrics] using Data Sources

For many marketing organizations, paid search is one of the most valuable and reliable ways both​ to reach new customers and to retain existing ones. The Data Sources capability in Adobe Analytics makes it easy to import advanced paid search data from digital advertising platforms like Google AdWords. You can  integrate it with the rest of your marketing data, alongside on-site behavioral and customer attribute data, to allow you better insights into your organization's paid search efforts.

These steps show you how to configure an integration with AdWords to import keyword data as well as metrics such as impressions, clicks, cost per click, and more.

The steps explain how to set up a one-time import of Pay-Per-Click data. However, Data Sources allows for the ongoing import of data using the file format described here. Depending on your paid search platform, you may be able to schedule periodic exports (daily, monthly, etc.), set up automated processes for transforming those exports into the file format that Adobe Analytics requires, and upload these files into Adobe Analytics for going paid search integration reporting.

## Prerequisites

* You have implemented paid search detection.
* You are capturing tracking code data.
* You have unique tracking codes for each Ad Group.

## Configure [!UICONTROL Success Events]

Our first step is to prepare Adobe Analytics to receive the metrics. To do this, you need to set up some success events.

Success events are actions that can be tracked. You determine what a success event is. For our purposes of tracking paid search metrics, we want to set up success events around clicks, impressions, and total cost and enable tracking codes.

1. Go to Adobe Analytics > Admin > Report Suites.
1. Select a report suite.
1. Click Edit Settings > Conversion > Success Events.

    ![Success Events](assets/success-events.png)

1. Under Custom Success Events, use Add New to create 3 custom success events: Clicks (Counter), Impressions (Counter) and Total Cost (Currency).

    ![New success event](assets/new-success-events.png)

1. Click Save.
   You should receive a message that your saves were approved.
1. Navigate to Admin > Report Suites > Edit Settings > Conversion > Conversion Variables.
1. Enable tracking codes by selecting the checkbox next to Tracking Code under Campaign > Campaign Variable.

    ![Campaign variable](assets/campaign-variable.png)

## Set up Data Sources

Data Sources allow you to share non-clickstream data with Adobe Analytics. In this case we use Adobe Analytics to track paid search metrics. We use the tracking code as our key to tie the two pieces of data - paid search metrics and Adobe Analytics metrics - together.

1. Navigate to Adobe Analytics > Admin > Data Sources.
1. Select the Create tab to start activating new data sources.
1. Under Select Category, select Ad Campaign.

    ![Data Sources](assets/data-sources.png)

1. Under Select Type, select Generic Pay-Per-Click Service.
1. Click Activate.
    The Data Source Activation Wizard displays:

    ![Activation Wizard](assets/ds-activation-wizard.png)

1. Click Next and name your data source. This name appears in the Data Source Manager.
1. Accept the service agreement and click Next.
1. Select the three standard metrics: Impressions, Clicks and Total Cost and click Next.
1. Now “map” this new data source to the custom events we created in Configure Success Events.

    ![Mapping](assets/data-source-mapping.png)

1. Choose data dimensions
    Check the box next to Tracking Codes and click Next.
1. Map data Dimensions.
    Map the imported data dimension (attribute) to the Adobe Analytics attribute that you want to store it in. This may be a standard dimension or an eVar. After you click Next, the resulting mappings are shown in the summary:

    ![Summary](assets/data-source-summary.png)

1. Click Save.
1. Click Download to download the template file for this data source.
    The file name corresponds to the data source type you initially specified - in this case, Generic Pay-Per-Click Service template.txt.
1. Open the template in your favorite text editor.
    The file is already populated with the metrics and dimensions and their mappings.

## Export PPC data and upload it to Analytics

Steps similar to these work for Google Adwords, MSN, Yahoo, and other PPC accounts.

