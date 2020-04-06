---
description: Selecting the gear icon next to a metric lets you specify the metric type and the attribution model.
title: Metric Type and Attribution
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
---

# Metric Type and Attribution

Selecting the gear icon next to a metric lets you specify the metric type and the attribution model.

* [Metric Type](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7) 
* [Column Attribution Model](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032) 
* [How Linear Allocation works (as of July 19, 2018)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Metric Type {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png) 

|  Metric Type  | Definition  |
|---|---|
|  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
|  Total  | Use the total for the reporting period in every line item. If a formula consisted of a single total metric, it displays the same total number on every line item. Total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## Column Attribution Model {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>In July 2018, [!DNL Analytics] introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. As part of this change, calculated metrics that use a non-default allocation model were migrated to new improved attribution models: 
>
>* For a full list of non-default attribution models and lookback windows supported, see the [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) documentation.
>* "Marketing Channel Last Touch" and "Marketing Channel First Touch" allocation models will be migrated to new "Last Touch" and "First Touch" attribution models respectively (Note: "Marketing Channels" will not be deprecated - only the two allocation models that appear in calculated metrics will be).
>* In addition, we will correct the way Linear allocation is calculated. For customers using calculated metrics with "Linear" allocation models, the reports may change slightly to reflect the new, corrected attribution model. This change to calculated metrics will be reflected in Analysis Workspace, Reports & Analytics, the Reporting API, Report Builder, and Ad Hoc Analysis. For more information, see **How Linear Allocation works (as of July 19, 2018**, below.
>

## How Linear Allocation works (as of July 19, 2018) 

In July 2018, Adobe changed how linear allocation is reported for Calculated Metrics. This change impacts Analysis Workspace, Ad Hoc Analysis, Reports & Analytics, Report Builder, Activity Map, and the Reporting APIs. The change will primarily impact eVars and other dimensions that have persistence. Note that these changes will only apply to calculated metrics and will not impact other reports using linear allocation (such as the Pages report in Reports & Analytics). Other reports using linear allocation will continue to use the existing method of linear allocation.

The following example illustrates how calculated metrics with linear allocation will change in reporting: 

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Hit 1 </th> 
   <th colname="col3" class="entry"> Hit 2 </th> 
   <th colname="col4" class="entry"> Hit 3 </th> 
   <th colname="col5" class="entry"> Hit 4 </th> 
   <th colname="col6" class="entry"> Hit 5 </th> 
   <th colname="col7" class="entry"> Hit 6 </th> 
   <th colname="col8" class="entry"> Hit 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data Sent In </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Last Touch eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> PROMO B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>First Touch eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO A </td> 
   <td colname="col6"> PROMO A </td> 
   <td colname="col7"> PROMO A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example prop </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

## How linear allocation worked prior to July 2018

Prior to July 19, 2018, linear attribution was calculated after first touch or last touch persistence has already occurred. This meant that for the last touch eVar above, the $10 would be distributed as follows: A = 10 &#42; (3/6) = $5, B = 10 &#42; (2/6) = $3.33, C = 10 &#42; (1/6) = $1.67.

For the first touch eVar above, all $10 would be given to A. For the prop: A = 10 &#42; (2/4) = $5, B = 10 &#42; (1/4) = $2.50, and C = 10 &#42; (1/4) = $2.50. To summarize linear allocation as it worked previously: 

|  Values  | Current Last Touch eVar  | Current First Touch eVar  | Current Prop  |
|---|---|---|---|
|  PROMO A  | $5.00  | $10.00  | $5.00  |
|  PROMO B  | $3.33  | $0  | $2.50  |
|  PROMO C  | $1.67  | $0  | $2.50  |
|  Total  | $10.00  | $10.00  | $10.00  |

**Summary of how linear allocation works as of July 19, 2018**

After July 19th, we corrected this behavior in calculated metrics. Instead of using the persisted values based on last touch or first touch, [!DNL Analytics] now uses only the values that were passed in (the first row of the top table). As such, the dimension allocation settings no longer impact the way linear allocation is calculated (meaning props and eVars will be treated in the same way), and the results reflect what was originally passed in rather than the first or last touch values that may have persisted. So, in all three cases, A = 10 &#42; (2/4) = $5, B = 10 &#42; (1/4) = $2.50, and C = 10 &#42; (1/4) = $2.50.

|  Values  | New Last Touch eVar  | New First Touch eVar  | New Prop  |
|---|---|---|---|
|  PROMO A  | $5.00  | $5.00  | $5.00  |
|  PROMO B  | $2.50  | $2.50  | $2.50  |
|  PROMO C  | $2.50  | $2.50  | $2.50  |
|  Total  | $10.00  | $10.00  | $10.00  |

