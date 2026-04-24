---
description: Learn about examples of filtered and weighted metrics.
title: Filtered And Weighted Metrics
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Filtered and weighted metrics

This article shows examples of filtered and weighted metrics.

## Filtered bounce rate

This simple filtered metric shows the bounce rate for only those pages with over 100 visits:

![Filtered bounce rate](assets/filtered-bounce-rate.png){zoomable="yes"}

Keep in mind that this formula is dependent on a consistent time range. If you run a report for a single day, any page with more than 20 visits is worth looking at. If you run it for a month, you may want the filter to include more visits.

## Filtered bounce rate with percentile

This filter shows the bounce rate for the top 30 percent of pages, when sorted by visits.

![Filtered bounce rate with percentile](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Weighted bounce rate

Suppose you want to sort by bounce rate in general, but pages with higher visits should be higher on the list. You could create a Weighted Bounce Rate that looks like this:

![](assets/weighted-bounce-rate.png)
