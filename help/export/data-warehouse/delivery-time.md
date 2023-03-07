---
title: Troubleshoot Data Warehouse request delivery times
description: Determine potential issues with a Data Warehouse request that can prolong delivery times.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
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

If you see data warehouse requests consistently take a long time, consider altering your requests to accommodate the following:

* **Use a segment containing a smaller sample of data**: The less data a request works with, the faster it returns a report.
* **Run requests in 14 day increments or less**: Smaller requests are processed faster than large requests.
* **Use fewer breakdowns:** Many breakdowns in a Data Warehouse request exponentially increase the time it takes to process.

>[!IMPORTANT]
>
> *There is no way to speed up delivery of a Data Warehouse request.*

If you require these types of reports in a more timely fashion, consider the following alternatives:

* **Analysis Workspace**: Though unlimited dimension items are not available, it includes almost all other use cases that Data Warehouse provides.
* **Data feed**: Takes all raw data in a report suite daily and sends it to an FTP site. You can then import this data into your own database and run queries to obtain the data you are looking for.
* **Custom Engineering Services solution**: Adobe Engineering Services can provide a custom solution for your organization at an additional cost. Contact your Adobe Account Team for additional details.
