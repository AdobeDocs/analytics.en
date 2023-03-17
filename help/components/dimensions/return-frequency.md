---
title: Return frequency
description: The bucketed amount of time between the current visit and previous visit.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
---
# Return frequency

The 'Return frequency' dimension shows the length of time that passes between visits from returning visitors. When a visitor returns to your site, Adobe looks at how long ago the previous visit was, and buckets the hit in the appropriate dimension item. This dimension is valuable to help gauge your website's appeal and relevance to visitors over time. It can also help identify the impact of your site's content and promotions on your visitors.

>[!TIP]
>
>This dimension does not include first-time visitors.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

Data for this dimension is set on the first hit of the visit, and persists for the entirety of the visit. The value cannot change mid-visit.

## Dimension items

Dimension items include time-based buckets, depending on elapsed time from their previous visit.

* Less than 1 day
* 1 to 3 days
* 3 to 7 days
* 7 to 14 days
* 14 days to 1 month
* Longer than 1 month

## Dimension items appear under buckets outside the project's date range

When you set a project's date range, it is common to see dimension items attribute to visits outside the date range. For example, a visitor comes to your site in July, then comes back twice in the same day in September. The Return frequency dimension for the month of September would show one visit under 'Longer than 1 month', and one visit under 'Less than 1 day'.
