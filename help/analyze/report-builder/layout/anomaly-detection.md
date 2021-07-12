---
description: Anomaly detection uses statistical modeling to automatically find unexpected trends in your data. The model analyzes metrics and determines a lower bound, upper bound, and expected range of values. When an unexpected spike or drop occurs, the system alerts you in the report.
title: Anomaly Detection
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
---
# Anomaly Detection{#anomaly-detection}

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

Anomaly detection uses a training period to calculate, learn, and report prediction interval data per day. The training period is the historical period that identifies what is normal vs. anomalous, and applies what is learned to the reporting period. In marketing reports, training periods of 30, 60, and 90 are available. In report builder, 30 days are available.

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
