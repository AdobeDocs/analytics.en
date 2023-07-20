---
title: Page Views
description: The number of times a dimension item was set or persisted in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
---
# Page Views

The **[!UICONTROL Page views]** metric shows the number of times a given dimension item (dimension value) was defined or persisted (i.e. when it expires) on a page. It is one of the most common and basic metrics in reports.

For example, the [!UICONTROL Days of Week] dimension is composed of the following dimension items: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, and Saturday. 

## How this metric is calculated

This metric counts all page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)) in a report suite. For dimensions, it includes hits where a dimension item is defined or persisted. It does not include link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)) or data from summary [Data sources](/help/import/data-sources/overview.md).

## Compare to similar metrics

* **Page views vs. [Visits](visits.md)**: Page views count the number of times a page is viewed. Visits count the number of sessions for visitors. One visit can consist of one or more page views.
* **Page views vs. [Page events](page-events.md)**: Page views count the number of page view tracking calls (`t()`), and excludes link tracking calls (`tl()`). Page events are the opposite; they count the number of link tracking calls, and exclude page view tracking calls.
