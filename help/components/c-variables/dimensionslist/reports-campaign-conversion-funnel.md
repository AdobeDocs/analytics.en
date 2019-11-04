---
description: Displays averages for metrics in the Campaigns reporting group. Default metrics are Click-throughs, Total Sales, Orders, and Revenue.
seo-description: Displays averages for metrics in the Campaigns reporting group. Default metrics are Click-throughs, Total Sales, Orders, and Revenue.
seo-title: Campaign Conversion Funnel
solution: Analytics
title: Campaign Conversion Funnel
topic: Reports
uuid: b0a90917-e4c7-40da-854e-58649de09742
---

# Campaign Conversion Funnel

Displays averages for metrics in the Campaigns reporting group. Default metrics are Click-throughs, Total Sales, Orders, and Revenue.

 **[!UICONTROL Campaigns]** > **[!UICONTROL Campaign Conversion Funnel]**

The top of a funnel graphic displays conversion data. The bottom displays statistics for all events in the top area, based on Orders and up to two other metrics, Revenue and Units.

Keep in mind the following information when interpreting conversion funnel data:

* Statistics for current time periods might not be completed when you view data, which can affect trends from a previous day to the current one.
* When no filter is applied to the funnel, the Visits metric represents conversion visits, or visits during which the campaign variable, any eVar variable, or a success event was fired. Visits during which none of these properties were passed into reports are not included in this total.
* When a filter is applied to the funnel, the Visits metric represents instances (or click-throughs). This value is the total number of times that the given variable was populated by users on your site, excluding those instances that do not meet the filter requirements. A single visit can involve multiple instances.
* It is possible for deeper levels on the funnel to report higher numbers than shallower levels. For example, you might see more orders than click-throughs, or more checkouts than product views. There are a number of reasons why this situation occurs:

    * You have more orders than click-throughs if the Tracking Code variable is set to a long cookie expiration (for example, a month), and users perform only one click-through but return several times and place orders during the period, before the Tracking Code value expires.
    * You have more checkouts than product views if the user is able to skip the product view page (as in the case of an upsell page), or if the user is able to save his shopping cart and return later to complete the order. If the product view occurs before the date range selected and the checkout occurs afterwards, you will see one checkout and zero product views. If you notice such a discrepancy, it does not indicate a problem with reporting or even an implementation error. Rather, you can use this data to understand how users are interacting with your site, even if it does not fit the funnel in the way that you expect.

