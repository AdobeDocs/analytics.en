---
description: Calculated and Advanced Calculated (or Derived) Metrics are custom metrics that you can create from existing metrics.
keywords: Calculated Metrics;Derived Metrics;Advanced Calculated Metrics
seo-description: Calculated and Advanced Calculated (or Derived) Metrics are custom metrics that you can create from existing metrics.
seo-title: Calculated and Advanced Calculated (Derived) Metrics
title: Calculated and Advanced Calculated (Derived) Metrics
uuid: 2553c115-b15a-4109-8de2-733dbc1eeb9e
index: y
internal: n
snippet: y
---

# Calculated and Advanced Calculated (Derived) Metrics

Calculated and Advanced Calculated (or Derived) Metrics are custom metrics that you can create from existing metrics.

>[!IMPORTANT]
>
>In July 2018, Adobe Analytics introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. As part of this change, calculated metrics that use a non-default allocation model were migrated to new improved attribution models: 
>
>* “Marketing Channel Last Touch” and “Marketing Channel First Touch” allocation models will be migrated to new “Last Touch” and “First Touch” attribution models respectively (Note: “Marketing Channels” will not be deprecated - only the two allocation models that appear in calculated metrics will be). 
>* In addition, we will be correcting the way Linear allocation is calculated. For customers using calculated metrics with “Linear” allocation models, the reports may change slightly to reflect the new, corrected attribution model. This change to calculated metrics will be reflected in Analysis Workspace, Reports and Analytics, the Reporting API, Report Builder, and Ad Hoc Analysis. For more information, see [How Linear Allocation will work as of July 19, 2018](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1). 
>

Our Calculated Metrics tools offer a highly flexible way of building, managing and curating metrics. They allow you as marketers, product managers and analysts to ask questions of the data without having to change your Adobe Analytics implementation. The custom metrics available in each Analytics package are:

* Adobe Analytics Foundation: Calculated 
* [Adobe Analytics Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html): Calculated + Advanced Calculated 
* [Adobe Analytics Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html): Calculated + Advanced Calculated 
* [Adobe Analytics Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html): Calculated + Advanced Calculated

Here is a comparison of Calculated Metrics and Advanced Calculated Metrics capabilities: 

|  Builder Options  | Calculated Metrics  | Advanced Calculated (Derived) Metrics  |
|---|---|---|
| [Format types (decimal, time, percent, currency)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18)  | Yes  | Yes  |
| [Attribution changes (default, linear, participation, etc.)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E)  | Yes  | Yes  |
| [Metric types (standard, total)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E)  | Yes  | Yes  |
|  Basic operators (add, subtract, multiply, divide)  | Yes  | Yes  |
| [Applying segments](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md#concept_21C77BD86E7E45E79AF030D8ED54DB3E)  | No  | Yes  |
| [Basic functions (count, abs value, mean, etc)](../../components/c-calcmetrics/cm-reference/cm-functions.md#concept_E3022D5EEEE145B69A23438BAF7016B2)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](../../components/c-calcmetrics/cm-reference/cm-adv-functions.md#concept_A5FB9127D70F4E1AA02D1ACBF4F54174)  | No  | Yes  |

## Capabilities {#section_A0A5C275B68A4D628950BBB0B1EE631F}

You can

* Create metrics across Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Anomaly Detection, and Contribution Analysis. 
* Create segmented metrics that are derived at report run time, [without having to change the implementation](https://youtu.be/CuQTm9RaUpY). These can be viewed historically because they are based on segments. 
* Share metrics across report suites. This means that all newly created metrics apply to all reports suites in the same login company. 
* (Advanced Calculated Metrics only) Segment on metrics. For example, you can create a metric for "New visitors", with a count of people for whom this is the first session. 
* (Advanced Calculated Metrics only) Incorporate statistical functions to help you better describe your data. For example, you can count the number of items in a report or add in the number of standard deviations for each item. 
* Utilize metrics created in Ad Hoc Analysis in the other Analytics tools and vice versa. 

  >[!NOTE]
  >
  >You can continue to create metrics in Ad Hoc Analysis. Its calculated metric builder user interface is now similar to the new metric builder.

## Limitations {#section_CB878B02451541D68A68B508D4DBD19A}

Some Adobe Analytics features let you use events but not calculated metrics:

* Funnels in Reports & Analytics 
* Fallout in Analysis Workspace 
* Cohort Analysis in Analysis Workspace 
* Data Warehouse 
* Segments 
* Real-Time reports 
* Current Data reports 
* Analytics for Target

## Tools {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Here is a short overview of the Calculated Metrics tools: 

<table id="table_520AFE97DB514958ABE23FD3C9CE0ABD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tool </th> 
   <th colname="col2" class="entry"> Capabilities </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18" format="dita" scope="local"> Calculated Metric Builder</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E6F02AB9DF204C2F9A0AC92A31594B3E"> 
     <li id="li_A4A6E716374243A190C539A3F4A41C0C">Create calculated and advanced calculated metrics using advanced allocation models. </li> 
     <li id="li_C8C97BA4E227463E98077ABA5818FFC6">Add segments inline to metric formulas. </li> 
     <li id="li_8503D9E06A3C46569B5CDB4B90F72446">Compare segments in the same report. For example, compare local visitors vs. international visitors. </li> 
     <li id="li_4B528FDE1F96400DBA0D3276408FF919">Use statistical functions. </li> 
     <li id="li_C1162B1EA6784B8189A8A87E2B0DA79A">Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it). </li> 
     <li id="li_DEA13F5E8BF94AF1B311C467FE6E2A74">Copy definitions into new metrics. </li> 
     <li id="li_8C21F55015D44910904202D2BF74221C">Provide an inline metric preview. </li> 
     <li id="li_3704F66C321C477F9D4F52E068C231BD">Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up. </li> 
     <li id="li_9D45319FA965476FB1C90DE8AA72BBD7">Tag metrics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md#concept_BA6815CB06D842D5825766396B691653" format="dita" scope="local"> Calculated Metric Manager</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E4D20D5DD3904CC6A85785B5BD4C1B1E"> 
     <li id="li_E0B216BA1478406EB6212263DF71D85B">Share metrics with others. </li> 
     <li id="li_96EB16FAF3454211AAEF78EA5B08927F">Approve and curate metrics. </li> 
     <li id="li_3ADBD2428EAC4B0AA61222D87C3AF2B7">Organize (tag) your metrics so people can find them. </li> 
     <li id="li_726F3C3390744E49BA63606FE196880E">Delete metrics. </li> 
     <li id="li_F306BA4FA8AF4A6E987BA62634659A2F">Rename metrics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metric Selector rail </td> 
   <td colname="col2"> <p>Replaces the <span class="uicontrol"> Show Metrics</span> popup in Reports &amp; Analytics. </p> <p>It lets you search for and add/apply metrics to the report. You can also change the <a href="../../components/c-calcmetrics/c-workflow/cm-workflow/cm-finding.md#concept_A09845053A934CB7B755391D76E76C08" format="dita" scope="local"> sort</a> order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite. </p> <p>To access this Metric Selector, click the Metrics icon <img placement="inline" href="assets/metrics_icon.png" width="30px" id="image_2C6F20B4E634486B95BACD4CA47EF991" /> to the left of a report. This is what the Metric Selector looks like: </p> <p style="text-align: center;"><img placement="break" align="center" href="assets/metrics_rail.png" width="200px" id="image_379523E9AFEC4CF08D20C42C740AA358" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://marketing.adobe.com/developer/blog/new-calculated-metrics-and-the-apis" format="https" scope="external"> API for Calculated Metrics</a> </td> 
   <td colname="col2"> <p>Part of the Admin API set. </p> </td> 
  </tr> 
 </tbody> 
</table>

