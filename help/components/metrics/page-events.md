---
title: Page events
description: The number of link tracking actions triggered.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
---
# Page events

The 'Page events' metric shows the number of times any link tracking call was made. This metric is helpful when you want to understand which pages have the most engaging content. Measurement for this metric is most valuable when a visitor can perform an action on the page without navigating to a new page.

## How this metric is calculated

This metric counts all [Link tracking calls (`tl()`)](/help/implement/vars/functions/tl-method.md) in a report suite. All link types are included (custom links, download links, and exit links). It does not include [Page view tracking calls (`t()`)](/help/implement/vars/functions/t-method.md).

## Compare to similar metrics

* **Page events vs. [Page views](page-views.md)**: Page events count the number of link tracking calls (`tl()`), and exclude page view tracking calls (`t()`). Page views are the opposite; it counts the number of page view tracking calls, and excludes links.
