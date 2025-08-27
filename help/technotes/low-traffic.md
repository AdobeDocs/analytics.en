---
description: When a report has many unique values, Adobe uses the Low-Traffic dimension item to improve report performance.
title: Low-traffic value in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
---
# [!UICONTROL Low-Traffic] value in Adobe Analytics

When a dimension contains millions of unique values, Adobe provides functionality to ensure that the most important values appear in your report in a timely manner. Unique values collected beyond a certain threshold are listed under a dimension item labeled **[!UICONTROL Low-Traffic]**.

The [!UICONTROL Low-Traffic] dimension item allows Adobe to ensure that reports are returned in a timely manner by taking excessive unique values and bucketing them together.

Note that [!UICONTROL Low-traffic] logic works best with dimensions that have items that recur many times during the month. If dimension items are nearly or entirely unique on every hit, the number of unique values reaches the threshold quickly and all subsequent values for the month end up in the [!UICONTROL Low-Traffic] bucket.

## How values enter [!UICONTROL Low-Traffic]

By default, a threshold of **2,000,000 unique values** is set per dimension, per report suite, per calendar month. Dimension items that exceed this unique value threshold are bucketed under [!UICONTROL Low-Traffic].

* Dimension items collected before the threshold is hit are calculated normally.
* Dimension items collected after the threshold is exceeded are bucketed under [!UICONTROL Low-Traffic].

>[!NOTE]
>The [Page](../components/dimensions/page.md) dimension uses several backend columns that all count towards the unique threshold, including `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, and `click_context`. These backend columns can cause [!UICONTROL Low-Traffic] logic to apply well before the number of unique Page dimension items in Workspace reaches the threshold.

The 2,000,000 unique limit can be changed on a per-dimension basis. See [Changing unique limit thresholds](#changing-unique-limit-thresholds) below. At the end of a calendar month, the number of tracked unique values is reset globally.

## How values can escape [!UICONTROL Low-Traffic] after exceeding the threshold

If a given dimension collects over 2,000,000 unique values in a given month, individual dimension items can return to reporting their own dimension item. The primary use case of this feature is to allow the reporting of crucial dimension items that might receive a surge of popularity late in the month after the unique threshold is exceeded. For example, if your organization runs a site with millions of articles and a new article becomes popular towards the end of the month, you can still analyze the performance of that article. This logic is not intended to un-bucket everything that gets a certain number of page views per day or per month, but rather offer an avenue to analyze content that receives an influx of traffic.

The requirements for an individual dimension item to escape [!UICONTROL Low-Traffic] depend on many factors, many of which prevent the ability to calculate an exact threshold:

* **Number of servers processing data for the report suite**: Report suites with more traffic require more instances of a single dimension item to escape [!UICONTROL Low-Traffic].
* **Amount of time between each dimension item instance**: Hits containing a dimension item spread throughout the day require more instances than a concentrated surge of hits.
* **Number of unique values for the dimension**: Each dimension has a second threshold set to a value of 2,100,000 unique values by default. If the number of unique values in a dimension exceeds this higher threshold, much more aggressive filtering is applied.

Taking the above factors into consideration, expect **hundreds to thousands** of instances for a single dimension item to escape [!UICONTROL Low-Traffic] if only the first threshold is exceeded. Expect **thousands to tens of thousands** of instances for a single dimension item to escape [!UICONTROL Low-Traffic] if the higher threshold is exceeded. Adobe does not guarantee that dimension items reliably escape the [!UICONTROL Low-Traffic] bucket. This concept is typically reserved for unusually high-volume dimension items late in the month.

When a dimension item escapes the [!UICONTROL Low-Traffic] bucket, instances collected before the influx of traffic remain under [!UICONTROL Low-Traffic].

## Changing unique limit thresholds

Threshold limits can sometimes be changed on a per-dimension basis. Contact Adobe Customer Care or your Adobe Account Team to request this change. The extent to which the thresholds can be increased depends on multiple factors; Adobe does not guarantee that all threshold increase requests can be accommodated. When requesting a change, include:

* The report suite ID
* The dimension you want to increase the threshold for
* Both the first and second threshold desired:
  * The first threshold (initial bucketing) is set to **2,000,000** by default.
  * The second threshold (more aggressive filtering) is set to **2,100,000** by default.

>[!IMPORTANT]
>
>Changes to thresholds can impact report performance. Adobe highly recommends using good judgment when requesting an increase to unique values for a dimension. Only increase unique limits for dimensions that are critical to your organization's reporting needs.

[!UICONTROL Low-Traffic] thresholds are not visible in the Analytics UI. Contact Adobe Customer Care if you would like more information on existing thresholds.

## Interactions with other capabilities

Different capabilities treat [!UICONTROL Low-Traffic] values in different ways.

* **Data Warehouse:** In most cases, there is no limit to the number of unique values in Data Warehouse reports. Its unique architecture allows the reporting of any number of unique values. However, [!UICONTROL Low-Traffic] values can still appear in some limited scenarios. Examples include list variables, list props, merchandising eVars, and marketing channel detail dimensions.
* **Segmentation:** If the segment criteria includes a dimension with a high number of unique values, values captured under [!UICONTROL Low-Traffic] are not included.
* **Classifications:** Classification reports are also subject to unique limits. If a classification's parent dimension item is included under [!UICONTROL Low-Traffic], the value is not classified.
  * [!UICONTROL Low-Traffic] values classified through the importer can be viewed in Data Warehouse. <!-- AN-115871 -->
  * [!UICONTROL Low-Traffic] values classified through the rule builder *cannot* be viewed in Data Warehouse. <!-- AN-122872 -->
