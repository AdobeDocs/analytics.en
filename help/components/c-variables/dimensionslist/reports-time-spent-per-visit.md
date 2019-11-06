---
description: null
solution: Analytics
title: Time Spent per Visit
topic: Reports
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
---

# Time Spent per Visit

Adobe Analytics offers several ways to determine time spent in Analytics reports. In most cases, time spent is calculated using the following steps:

1. For a given visit, look at the timestamp of the first hit.
2. Compare this hit with the timestamp of the last hit of the visit.
3. The amount of time that elapsed between these two hits determines the amount of time spent for that visit.

When viewing time spent dimension data, keep the following in mind:

* Both page views and link tracking hit types are considered when calculating time spent data.
* Time spent is not measured during the last hit of the visit, since there is no subsequent image request to measure elapsed time.
* Bounces cannot measure time spent, since the visit consists of a single hit.

Time spent per visit measures the total elapsed time in a visit. Separate dimensions exist between **granular** and **bucketed**.

* **Granular:** Each dimension value is a different number of seconds making up a visit.
* **Bucketed:** Each dimension value is a pre-defined bucket:
  * Less than 1 minute
  * 1-5 minutes
  * 5-10 minutes
  * 30-60 minutes
  * 1-2 hours
  * 2-5 hours
  * 5-10 hours
  * 10-15 hours
  * 15+ hours

> [!NOTE] [Visits](../c-metrics/metrics-visit.md) typically end after 12 hours of activity. However, visits can exceed 12 hours if using timestamped hits or data sources.

This dimension is visit-based. Compare this dimension to [Time spent on page](reports-time-spent-on-page.md), which is a hit-based dimension.
