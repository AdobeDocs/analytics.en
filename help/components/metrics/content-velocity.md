---
title: Content Velocity
description: Content Velocity measures the impact of content on downstream content.
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
---
# Content Velocity

The 'Content Velocity' calculated metric helps you measure how a dimension (typically [[!UICONTROL Page]](/help/components/dimensions/page.md)) contributes toward users spending time on your website or app.

This metric uses [Participation attribution](/help/analyze/analysis-workspace/attribution/models.md) on the [Page views](page-views.md) metric as part of its calculation. With Visit participation, every time a page is hit, all pages that were previously hit during the same visit also receive credit for the page view. This formula typically means that the earlier a page is hit during a visit, the more credit it receives. (See [Page Views (Participation | Visit) or 'Visit participation'](#page-views-participation--visit-or-visit-participation) for more information.)

## Calculation

'Content Velocity' is a default calculated [metric](overview.md) and it uses the formula `Page views (Visit participation)` divided by `Visits`.

![](assets/cont-velo-1.png)

## Common uses

[!UICONTROL Content Velocity] is commonly used in content analysis alongside other key metrics such as [!UICONTROL Page Views], [!UICONTROL Visits], and [!UICONTROL Bounce Rate].

![](assets/cont-velo-3.png)

## Example

The following example breaks down the 2 parts of Content Velocity: 'Page Views (Participation | Visit)' and 'Visits'.

### Page Views (Participation | Visit) or 'Visit participation'

Consider the following example of how Visit participation affects attribution:

On a website, a user visits the following pages in this order:

* Page A
* Page B
* Page C
* Page D

In the above example, Page A would receive credit for 4 hits, Page B for 3 hits, Page C for 2 hits, and Page D for 1 hits. 

The following example illustrates the same principle, but with some pages being visited more than once.

* Page A
* Page B
* Page C
* Page B
* Page D
* Page A

In the above example, Page A would receive credit for 7 hits, Page B for 8 hits, Page C for 4 hits, and Page D for 2 hits.

### Visits

After Visit participation is calculated, the result is divided by the number of visits. 
