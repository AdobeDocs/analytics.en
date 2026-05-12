---
title: Troubleshoot Data Warehouse Request Delivery Times
description: Determine potential issues with a Data Warehouse request that can prolong delivery times.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
TQID: https://experienceleague.adobe.com/oWkM-wTuJ75sR6AzkjD8WfY9DYLUdtToSGyu8hJIXVk
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Troubleshoot Data Warehouse request delivery times

A given Data Warehouse request can take anywhere from less than an hour to several days or more. It is difficult to estimate the exact amount of time it takes for a request to process, due to the following factors:

* The date range of the request
* The amount of traffic your report suite received during the requested time period
* The number of rules within a segment, and which variables within a segment used
* How much data is included within the segment
* The number of breakdowns used, and the number of unique values within each breakdown
* The number of metrics used
* The number of concurrent requests being processed
* VISTA rules, if configured to apply to DataWarehouse requests

## Alter requests to speed up delivery

If Data Warehouse requests consistently take a long time, consider altering your requests. Altering a request is the only way to speed up the delivery of a Data Warehouse request.

To speed up the delivery of a Data Warehouse request, you can alter it in any of the following ways:

* **Use a segment containing a smaller sample of data**: The less data a request works with, the faster it returns a report.
* **Run requests in 14-day increments or less**: Smaller requests are processed faster than large requests.
* **Use fewer breakdowns:** Many breakdowns in a request exponentially increase the time it takes to process it.

## Use an alternate method

If you require these types of reports in a more timely fashion, consider the following alternatives:

* **Analysis Workspace**: Though unlimited dimension items are not available, it includes almost all other use cases that Data Warehouse provides.
* **Data feed**: Takes all raw data in a report suite daily and sends it to a cloud destination. You can then import the data into your own database and run queries in order to get the data you need.
* **Custom Engineering Services solution**: Adobe Engineering Services can provide a custom solution for your organization at an additional cost. Contact your Adobe Account Team for additional details.
