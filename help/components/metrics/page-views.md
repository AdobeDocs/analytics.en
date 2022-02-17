---
title: Page Views Metric Explained | Adobe Analytics 
description: Learn how the page views metric is worked out in Adobe Analytics and also understand the difference between page views and visits.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
---
# Learn about Page Views with Adobe Analytics

The 'Page views' metric shows the number of times a given dimension item was set or persisted on a page. It is one of the most common and basic metrics in reports.

## How this metric is calculated

This metric counts all page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)) in a report suite. For dimensions, it include hits where a dimension item is defined or persisted. It does not include link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Compare to similar metrics

* **Page views vs. [Visits](visits.md)**: Page views counts the number of times a page is viewed. Visits counts the number of sessions for visitors. One visit consists of one or more page.
* **Page views vs. [Page events](page-events.md)**: Page views counts the number of page view tracking calls (`t()`), and excludes link tracking calls (`tl()`). Page events is the opposite; it counts the number of link tracking calls, and excludes page views.
