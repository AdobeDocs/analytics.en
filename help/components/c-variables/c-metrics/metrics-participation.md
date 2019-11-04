---
description: Participation metrics assign full credit from success events to all values of an eVar that were passed during a visit. Participation metrics are useful to determine which pages, campaigns, or other custom variable values are contributing most to the success of your site. Participation is visit based. All eVar values in a visit prior to and including the hit when an event occurs receive participation credit regardless of the expiration setting.
seo-description: Participation metrics assign full credit from success events to all values of an eVar that were passed during a visit. Participation metrics are useful to determine which pages, campaigns, or other custom variable values are contributing most to the success of your site. Participation is visit based. All eVar values in a visit prior to and including the hit when an event occurs receive participation credit regardless of the expiration setting.
seo-title: Participation
solution: Analytics
title: Participation
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
---

# Participation

Participation metrics assign full credit from success events to all values of an eVar that were passed during a visit. Participation metrics are useful to determine which pages, campaigns, or other custom variable values are contributing most to the success of your site. Participation is visit based. All eVar values in a visit prior to and including the hit when an event occurs receive participation credit regardless of the expiration setting.

See [Visitor Participation - Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) for more information about how Ad Hoc Analysis uses participation.

Participation metrics have two settings per conversion event:

* **Disabled**: The default state of each conversion event. Participation data will not be gathered for this event.
* **Enabled**: Participation data is collected for this event.

>[!NOTE]
>
>You can enable participation for up to 100 custom events. Beyond that, you can create participation metrics in the [Calculated Metrics](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html) builder.

Once enabled, participation metrics are automatically available in all conversion reports. However, participation metrics also can be viewed in specific traffic reports at your request. You can optionally request participation metrics be available in certain custom traffic reports.

## Revenue Participation Example {#section_DAB6C348201B454BB4ED01313AA777AF}

Assume the following sequence:

1. A user navigates to your site and searches for "shoes".
1. The user then searches for "tennis shoes".
1. The user clicks a links to the product page, adds the item to the cart, and makes a $120 purchase.

When displaying Revenue in the Internal Search Terms Report, you would see the following based on the selected allocation:

* **First**: "shoes" would get credit for the $120. "tennis shoes" would get $0.
* **Last**: "tennis shoes" would get credit for the $120. "shoes" would get $0.
* **Linear**: Each campaign would get $60 credit.

  Participation is similar to linear allocation, except full credit is given to all values. If you use Revenue (Participation) as the metric, allocation is disregarded. Revenue (Participation) in this example would report $120 for both search terms.

>[!MORE_LIKE_THIS]
>
>* [Metric Calculations](/help/components/c-variables/c-metrics/metrics-calculations.md)
