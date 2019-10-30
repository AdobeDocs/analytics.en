---
description: Real-time page analytics (Live Mode) lets you obtain results with minute granularity in real time.
seo-description: Real-time page analytics (Live Mode) lets you obtain results with minute granularity in real time.
seo-title: Real-time (Live) page analytics
solution: Analytics
title: Real-time (Live) page analytics
topic: Activity map
uuid: a3faa9bd-73d8-48b3-be2b-f818ed7456fb
---

# Real-time (Live) page analytics

Real-time page analytics (Live Mode) lets you obtain results with minute granularity in real time.

[!DNL Activity Map] now displays analytical data in 1 to 15 minute increments to monitor link popularity based on micro-trends for selected pages. This is especially important for publishing enterprises in tracking and responding to increasing or diminishing interest in stories and to monitor real-time traffic flow.

As a site content owner, part of your job is to understand when to promote and remove content and keep our experience constantly relevant. Real-time data is the lifeblood of this responsibility. If you can understand what links and content are trending right now, you can act quickly and decisively to keep readers and customers engaged with your brand.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

After the A4T integration is enabled in Adobe Target, you will experience an additional 5-10 minutes of latency in Adobe Analytics. This latency increase allows data from Analytics and Target to be stored on the same hit, allowing you to break down tests by page and site section.

This increase is reflected in all Adobe Analytics services and tools, including the live stream and real-time reporting, and applies in the following scenarios:

* For live stream, real-time reports & API requests, and current data for traffic variables, only hits with a supplemental data ID are delayed.
* For current data on conversion metrics, finalized data, and data feeds, all hits are delayed an additional 5-7 minutes.

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
