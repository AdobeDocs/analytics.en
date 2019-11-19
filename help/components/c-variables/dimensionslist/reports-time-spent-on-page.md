---
description: Displays the amount of time visitors spend on the page
solution: Analytics
title: Time Spent on Page
topic: Reports
---

# Time spent on page

Adobe Analytics offers several ways to determine time spent in Analytics reports. In most cases, time spent is calculated using the following steps:

1. For a given hit, look at the timestamp and dimension value.
2. Compare this hit with the timestamp of the next hit in the visit.
3. The amount of time that elapsed between these two hits contributes to the time spent for that page.

When viewing time spent dimension data, keep the following in mind:

* Time spent takes allocation and expiration into account.
* Both page views and link tracking hit types are considered when calculating time spent data.
* Time spent is not measured during the last hit of the visit, since there is no subsequent image request to measure elapsed time.
* Bounces cannot measure time spent, since the visit consists of a single hit.

Time spent on page measures the elapsed time between hits in a visit. Separate dimensions exist between **granular** and **bucketed**.

* **Granular:** Each dimension value is a different number of seconds spent between two hits.
* **Bucketed:** Each dimension value is a pre-defined bucket:
  * Less than 15 seconds
  * 15 to 29 seconds
  * 1 to 3 minutes
  * 3 to 5 minutes
  * 5 to 10 minutes
  * 10 to 15 minutes
  * 15 to 20 minutes
  * 20 to 30 minutes
  * More than 30 minutes

This dimension is hit-based, which if used as a breakdown can provide more meaningful data. Compare this dimension to [Time spent per visit](reports-time-spent-per-visit.md), which is a visit-based dimension.

![Time spent](/help/components/c-variables/c-metrics/assets/time-spent1.png)
