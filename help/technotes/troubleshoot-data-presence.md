---
title: Troubleshoot data presence
description: Learn what steps you can take when you do not see data in reports.
---

# Troubleshoot data presence

In Analysis Workspace, some project setups return zero rows. In Reports & Analytics, viewing certain reports returns the following message:

**"There is no data for the selected criteria."**

Use the following steps to determine why a report doesn't show data.

## Data exists but is filtered out

Your report suite contains data, but the specific components used in the report filters all the data out.

* **Segments**: Segments can easily prevent all data from appearing in a report. Check all segment definitions and remove all segments to see if a segment is causing your data to not appear.
* **Metrics**: Check to make sure the correct metrics are used. Change the metric to [Occurrences](/help/components/metrics/occurrences.md) to make sure that the metric is not the contributor to a report without data.
* **Date ranges**: Date ranges too far in the past or anytime in the future do not return data. Your organization's [data retention policy](data-retention.md) determines how far back data is kept.
* **Filters**: Remove all search filters from the report.

## Data does not exist

If there are no segments, the metric is Occurrences, the date range is the current month, and there are no search filters, check the following:

* **Verify the report suite**: Make sure that you're in a report suite that contains data. Many organizations have new, testing, or development report suites that typically don't contain much data.
* **Latency**: If viewing recent data, the data might just be delayed. See [Latency](latency.md) for more information.
* **Validate data collection**: Navigate to the web property that your report suite is supposed to track, and open the [Adobe debugger](https://experienceleague.adobe.com/docs/ debugger/using/experience-cloud-debugger.html). Make sure that an Analytics image request is present when loading a page. If you see an image request, make sure that it uses the correct report suite ID, that it includes a valid [currencyCode](/help/implement/vars/config-vars/currencycode.md), and that [timestamp support](/help/implement/vars/page-vars/timestamp.md) matches between the image request and report suite.
