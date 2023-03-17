---
title: Page Views
description: The number of times a dimension item was set or persisted in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
---
# Page Views

The 'Page views' metric shows the number of times a given dimension item was set or persisted on a page. It is one of the most common and basic metrics in reports.

## How this metric is calculated

This metric counts all page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)) in a report suite. For dimensions, it includes hits where a dimension item is defined or persisted. It does not include link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Compare to similar metrics

* **Page views vs. [Visits](visits.md)**: Page views count the number of times a page is viewed. Visits count the number of sessions for visitors. One visit consists of one or more page views.
* **Page views vs. [Page events](page-events.md)**: Page views count the number of page view tracking calls (`t()`), and excludes link tracking calls (`tl()`). Page events are the opposite; they count the number of link tracking calls, and exclude page view tracking calls.
