---
description: When a report has many unique values, Adobe uses the Low-Traffic dimension item to improve report performance.
title: Low-traffic value in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
---
# Low-traffic value in Adobe Analytics

When a dimension contains millions of unique values, Adobe provides functionality to ensure that the most important values appear in your report in a timely manner. Unique variable values collected beyond a certain threshold are listed under a dimension item labeled **[!UICONTROL Low-Traffic]**.

The Low-Traffic dimension item allows Adobe to ensure that reports are returned in a timely manner by taking excessive unique values and bucketing them together.

## How values enter [!UICONTROL Low-Traffic]

By default, a given dimension must receive approximately **2,000,000 unique values** before subsequent unique values are bucketed under Low-Traffic.

* Line items collected before the threshold is hit are calculated normally.
* Line items collected after the threshold is exceeded are bucketed under Low-Traffic.

>[!NOTE]
>The [Page](../components/dimensions/page.md) dimension uses several backend columns that all count towards the unique threshold, including `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, and `click_context`. These backend columns can cause [!UICONTROL Low-Traffic] logic to apply well before the number of unique Page dimension items in Workspace reaches the threshold.

The 2,000,000 unique limit can be changed on a per-dimension basis. See [Changing unique limit thresholds](#changing-unique-limit-thresholds) below.

## How values can escape [!UICONTROL Low-Traffic] after exceeding the threshold

If a given dimension collects over 2,000,000 unique values in a given month, individual dimension items can return to reporting their own dimension item. The primary use case of this feature is to allow the reporting of something that might receive a surge of popularity late in the month after the unique threshold is exceeded.

The requirements for an individual dimension item to escape Low-Traffic depend on many factors, many of which prevent the ability to calculate an exact threshold:

* **Number of servers processing data for the report suite**: Report suites with more traffic require more occurrences of a single dimension item to escape Low-Traffic.
* **Amount of time between each dimension item occurrence**: Hits containing a dimension item spread throughout the day require more occurrences than a concentrated surge of hits.
* **Number of unique values for the dimension**: Adobe has a second threshold set to a value of 2,100,000 unique values by default. If the number of unique values in a dimension exceeds this higher threshold, much more aggressive filtering is applied.

Taking the above factors into consideration, expect **hundreds to thousands** of occurrences for a single dimension item to escape Low-Traffic if only the first threshold is exceeded. Expect **thousands to tens of thousands** of occurrences for a single dimension item to escape Low-Traffic if the higher threshold is exceeded.

When a dimension item escapes the Low-Traffic bucket, occurrences collected before the influx of traffic remain under [!UICONTROL Low-Traffic].



  * If a value is not yet seen in reports, initially add it to the [!UICONTROL Low-Traffic] dimension item.
  * If a value that is bucketed under [!UICONTROL Low-Traffic] receives an influx of traffic (typically instances in the double digits in a single day), recognize it as its own dimension item. . The exact point at which the dimension item begins showing up in reports has many dependencies, such as the number of servers processing data for the report suite and the amount of time between each dimension item instance.
* If a variable reaches the high threshold, more aggressive filtering is applied. Unique values require instances in the triple digits in a single day before being recognized as its own dimension item.

This logic allows Adobe to optimize reporting capabilities while still allowing your organization to report on crucial dimension items collected later in the month. For example, if your organization runs a site with millions of articles and a new article becomes popular towards the end of the month (after exceeding both unique thresholds), you can still analyze the performance of that article without it being bucketed under [!UICONTROL Low-Traffic]. This logic is not intended to un-bucket everything that gets a certain number of page views per day or per month.



Note that low-traffic logic works best with variables that have dimension items that recur many times during the month. If a variable's dimension items are nearly or entirely unique on every hit, the variable's number of unique values reaches both thresholds quickly and all subsequent dimension items for the month end up in the low-traffic bucket.

## Changing unique limit thresholds

Threshold limits can sometimes be changed on a per-variable basis. Contact Adobe Customer Care or your Adobe Account Team to request this change. The extent to which the thresholds can be increased depends on multiple factors and Adobe may not be able to accommodate threshold increases in all cases. When requesting a change, include:

* The report suite ID
* The variable you would like to increase the threshold for
* Both the first and second threshold desired

Changes to thresholds can impact report performance. Adobe highly recommends using good judgment when requesting an increase to unique values in a variable. Only increase unique limits for variables that are critical to your organization's reporting needs.

Low-traffic thresholds are not visible in the Analytics UI. Contact Adobe Customer Care if you would like more information on existing thresholds.

## Low-traffic using components and other capabilities

Different capabilities treat low-traffic values in different ways.

* **Data Warehouse:** There is no limit to the number of unique values in Data Warehouse reports. Its unique architecture allows the reporting of any number of unique values.
  * In some limited scenarios, low-traffic values can still appear. Examples include list vars, list props, merchandising eVars, and marketing channel detail dimensions.
* **Segmentation:** If the segment criteria includes a variable with a high number of unique values, values captured under low-traffic are not included.
* **Classifications:** Classification reports are also subject to unique limits. If a classification's parent variable value is included under low-traffic, the value is not classified.
  * Low-traffic classification values obtained through the importer can be viewed in Data Warehouse. <!-- AN-115871 -->
  * Low-traffic classification values obtained through the rule builder *cannot* be viewed in Data Warehouse. <!-- AN-122872 -->
