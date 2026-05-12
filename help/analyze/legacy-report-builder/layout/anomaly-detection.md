---
description: Learn about Anomaly Detection and how it's calculated.
title: How Anomaly Detection is used to automatically find trends
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
TQID: https://experienceleague.adobe.com/P2dvU8YgWcjCZ6h4oTxK-2-z1X3-wl-oMp70UIJGeXo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
  - id: c67272a6-888e-425e-9e97-a87304637eed
    internal-label: Anomaly Detection
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Anomaly Detection{#anomaly-detection}

{{legacy-arb}}

Anomaly detection uses statistical modeling to automatically find unexpected trends in your data. The model analyzes metrics and determines a lower bound, upper bound, and expected range of values. When an unexpected spike or drop occurs, the system alerts you in the report.

Examples of anomalies you might investigate include:

* Drastic drops in average order value 
* Spikes in orders with low revenue 
* Spikes or drops in trial registrations 
* Drops in landing page views 
* Spices in video buffer events 
* Spikes in low video bit-rates

>[!NOTE]
>
>Anomaly detection is available only when you select the Day granularity.

<p class="head"> <b>Anomaly Detection Metrics</b> </p>

Anomaly detection adds new metric values for each metric you select, including: 

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Lower Bound </td> 
   <td colname="col2"> <p>Lower level of the prediction interval. Values below this level are considered anomalous. </p> <p>Represents a 95% confidence that values will be above this level. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expected </td> 
   <td colname="col2"> <p>The predicted value based on the data analysis. This value is also the middle point between the upper and lower bounds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Upper Bound </td> 
   <td colname="col2"> <p>Upper level of the prediction interval. Values above this level are considered anomalous. </p> <p>Represents a 95% confidence that values will be below this level. </p> </td> 
  </tr> 
 </tbody> 
</table>

Report builder applies these values to selected metrics. For example, if you select a Page Views metric and apply anomaly detection, a *`Page Views Lower Bound`* metric is used.

**How Anomaly Detection Is Calculated**

Anomaly detection uses a training period to calculate, learn, and report prediction interval data per day. The training period is the historical period that identifies what is normal vs. anomalous, and applies what is learned to the reporting period. In marketing reports, training periods of 30, 60, and 90 are available. In Report Builder, 30 days are available.

The training period is not necessarily the same as the selected reporting period. A report graph displays the date range period you specify in the calendar.

To calculate the data, the daily total for each metric is compared with the training period using each of the following algorithms:

* Holt Winters Multiplicative (Triple Exponential Smoothing) 
* Holt Winters Additive (Triple Exponential Smoothing) 
* Holts Trend Corrected (Double Exponential Smoothing)

Each algorithm is applied to determine the algorithm with the smallest Sum of Squared Errors (SSE). The Mean Absolute Percent Error (MAPE) and the current Standard Error are then calculated to make sure that the model is statistically valid.

These algorithms can be extended to provide predictive forecasts of metrics in future periods.

Because the training period varies based on the start of the reporting period, you might see differences in the data reported for the same date as part of two different time periods.

For example, if you run a report for January 1-14, and then run a report for January 7-21, you might see different prediction data for the same metric between January 7-14 in the two different reports. This is a result of the difference in training periods.

| Reporting Range  | Training Period  |
|--- |--- |
|January 1-14|November 27 - December 31|
|January 7-21|December 4 - January 6|
