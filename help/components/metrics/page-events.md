---
title: Page events
description: The number of link tracking actions triggered.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
---
# Page events

The 'Page events' [metric](overview.md) shows the number of times any link tracking call was made. This metric is helpful when you want to understand which pages have the most engaging content. Measurement for this metric is most valuable when a visitor can perform an action on the page without navigating to a new page.

For example, in a typical journey of an eCommerce site, a visitor can have several interactions on a single page. A typical Analytics implementation has these interactions configured as a link tracking ([`tl()`](/help/implement/vars/functions/tl-method.md)) call, while a page view ([`t()`](/help/implement/vars/functions/t-method.md)) call is reserved for the initial page load. This implementation method provides enriched event tracking that provides insight around what interactions happen before a visitor continues their journey.

## How this metric is calculated

This metric counts all link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)) in a report suite. All link types are included in this metric, specifically [Custom links](../dimensions/custom-link.md), [Download links](../dimensions/download-link.md), and [Exit links](../dimensions/exit-link.md). It does not include page view calls ([`t()`](/help/implement/vars/functions/t-method.md)).

## Compare to similar metrics

* **Page events vs. [Page views](page-views.md)**: Page events count the number of link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)), and exclude page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)). Page views are the opposite; it counts the number of page view tracking calls, and excludes links.
