---
description: Standard reports display data for website and visitor activity, traffic patterns, referral data, advertising campaigns, visitor retention, product data, and more. You can run reports and then access tools to configure segments, metrics, and report comparisons.
title: Reports overview
topic: Ad hoc analysis
uuid: 36722dcd-5dc9-4047-8a17-16de876193bf
---

# Reports overview

Standard reports display data for website and visitor activity, traffic patterns, referral data, advertising campaigns, visitor retention, product data, and more. You can run reports and then access tools to configure segments, metrics, and report comparisons.

## Reports overview {#concept_41459A705F2048EEA4EFA80F6BD9FFAB}

Standard reports display data for website and visitor activity, traffic patterns, referral data, advertising campaigns, visitor retention, product data, and more. You can run reports and then access tools to configure segments, metrics, and report comparisons.

You can gather custom data to create reports specific to your website. For example, if you have a search feature on your website, you can track the search terms submitted and create a report that shows these terms and the results of the searches.

The standard report set covers topics common to every website. Reports include (but are not limited to):

* Website data 
* Visitor data 
* Traffic patterns 
* Referral data 
* Advertising campaigns 
* Visitor retention 
* Product information

If you use marketing reports and analytics, the report types and menus will be familiar. Ad hoc analysis categorizes reports based on the following types:

**Summary Reports**

Includes reports such as the [!UICONTROL Totals Report], which shows data designed for quick overviews. These are intended for executives who want a general overview of the data.

**Conversion Reports**

Conversion reports provide comprehensive, accurate, and detailed analysis of customer activity. Metrics such as campaign management, sales cycle, customer fallout, and customer conversion let you measure e-commerce transactions, sources of sales, advertising effectiveness, customer loyalty, and more.

**Traffic Reports**

Traffic reports give you in-depth insight into how visitors interact with your website.

* Analyze critical aspects of visitor behavior.
* Monitor and understand traffic patterns.
* Determine popular site content.
* Segment visitors by any measurable criteria.

## Campaigns {#concept_A407CDF1D4AA49BAB396A1666E67FC87}

Displays information about the effectiveness of your advertising efforts. You can see which types of advertising efforts give you the most traffic and which of your employees is responsible for driving those efforts.

<!-- 

c_reports_campaigns.xml

 -->

These reports are usually customized and thus different for every analyst. See [Campaign Manager](https://marketing.adobe.com/resources/help/en_US/reference/campaign_manager_admin.html) in the [!DNL Admin Console] help for more information.

## Statistical Calculations {#concept_83FF70DB7895435E985699FE9012D585}

You can customize the default statistics to show up in a ranked report.

<!-- 

c_Statistical_Calculation_ad_hoc.xml

 -->

Additional default statistical calculations can be added to ranked reports based to display when you run the report, including mean, median, standard deviation, and other mathematical calculations assessed across your data based on your specific reporting needs.

**To open the statistical calculations for Ranked Reports:**

1. Select **[!UICONTROL Tools]** > **[!UICONTROL Ranked]** from the menu.

1. Select **[!UICONTROL Settings]**.
1. Select **[!UICONTROL Default Statistics]**.

**[!UICONTROL Ignore zeros in statistical calculations]**. Select this option to ignore zeros and ensure that adding another metric won't change the averages already calculated. All the statistics are affected by this setting (although for Sum it has no effect).

| Calculation | Description |
|--- |--- |
|Max|Identifies the maximum value across all rows for a specified dataset.|
|Min|Identifies the minimum value across all rows for a specified dataset.|
|Sum|A calculation of all the values for each row in the dataset.  For example, the sum aggregates all visits by a visitor rather than counting the visitor only once (regardless of the number of visits). It is a comprehensive total of collected data points.|
|Mean|The mean is the arithmetic average of the values of rows in a dataset, calculated by the sum divided by the count (sum/count). The mean is influenced by outlying data, unlike the median which is generally used for skewed distributions.|
|Standard Deviation|The standard deviation shows how much variation exists from the expected mean. A lower standard deviation shows the data points close to the mean. A higher standard deviation shows that the data points are spread across a large range of values.|
|Median|The median is the numerical value separating the higher half of a data from the lower half for the rows in a dataset. Unlike the mean, it is generally used to avoid outlying values.|
|Quartiles|A quartile is the set of values in the dataset identified by three points that divide the data set into four equal groups, each comprising a quarter of the dataset. The first quartile is the 25th percentile, and the third quartile is the 75th percentile. (The second quartile is the Median and the fourth quartile is the Sum.)|
|Count|Returns the number of rows in a dataset.|

## Example of Mean vs. Metric Total Calculations {#section_7C49196503964FB0A429FA347BC92D09}

The Mean function is calculated similar to columns of data in Microsoft Excel. In particular, this means that the **Mean** of a ratio (such as determining the average bounce rate) would be the average of the ratios, not the ratio of the averages. The ratio of the averages includes the **Total** of the bounce rate metric.

<table id="table_9EC56B15C6A340DA8917CB0DBCAC2355"> 
 <thead> 
  <tr> 
   <th colname="col1" align="center" class="entry"> Date </th> 
   <th colname="col2" align="center" class="entry"> Single Visits </th> 
   <th colname="col3" align="center" class="entry"> Entries </th> 
   <th colname="col4" align="center" class="entry"> Bounce Rate </th> 
   <th colname="col5" align="center" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>June 2013 </p> <p>July 2013 </p> <p>August 2013 </p> </td> 
   <td colname="col2" align="center"> <p>344 </p> <p>297 </p> <p>41 </p> </td> 
   <td colname="col3" align="center"> <p>1000 </p> <p>1000 </p> <p>1000 </p> </td> 
   <td colname="col4" align="center"> <p>34.4% </p> <p>29.7% </p> <p>41.0% </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Mean</b> </td> 
   <td colname="col2" valign="middle"> (344+297+41)/3 </td> 
   <td colname="col3" valign="middle"> (1000+1000+100)/3 </td> 
   <td colname="col4" valign="middle" align="right"> (34.4 + 29.7 + 41.0) / 3 = <b>35.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Mean of ratios</b> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Metric Total</b> </td> 
   <td colname="col2" valign="middle"> 682 </td> 
   <td colname="col3" valign="middle"> 2100 </td> 
   <td colname="col4" valign="middle" align="right"> 682 / 2100 = <b>32.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Ratio of means</b> </td> 
  </tr> 
 </tbody> 
</table>

## Statistical Calculation Overlays {#concept_97E1B32DAC734C7B9F8899717283CEEC}

Ad hoc analysis now provides overlay visualizations of statistical calculations for reports that display data over time (minutes, hours, days, weeks).

<!-- 

c_overlay_calculations.xml

 -->

In a report that identifies data over a period of time, the **[!UICONTROL Statistics]** button lets you select calculations that will display as overlays across the report time line.

![](assets/overlay_calculations.png)

In addition to standard [Statistical Calculations](/help/analyze/ad-hoc-analysis/c-overview-standard-reports.md#concept_83FF70DB7895435E985699FE9012D585), you can select the 1st, 2nd, and 3rd standard deviations in the overlays.

## Group Manager {#concept_E1433974A61144858E87334C006982B2}

Rather than using a single page in a report, you can group multiple pages and use them as categories for starting, intermediate, or destination location in the [!UICONTROL Fallout] and [!UICONTROL Site Analysis] reports. You can edit groups from the main menu, or from within the report. Categories that you have created in marketing reports and analytics also appear in the [!UICONTROL Checkpoint Selector] list.

<!-- 

c_groups.xml

 -->

Click **[!UICONTROL Tools]** > **[!UICONTROL Group Manager]**.
