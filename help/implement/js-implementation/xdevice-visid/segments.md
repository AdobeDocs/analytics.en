---
description: You can create a segment whenever an association occurs for a given visitor ID cookie.
keywords: Analytics Implementation
seo-description: You can create a segment whenever an association occurs for a given visitor ID cookie.
seo-title: Create segments
solution: Analytics
title: Create segments
topic: Developer and implementation
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
---

# Create segments

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

You can create a segment whenever an association occurs for a given visitor ID cookie.

Based on the [previous table](/help/implement/js-implementation/xdevice-visid/visit-example.md), if you created a segment where visit number equals 9, it would include server calls 12 and 13. Even through server call 11 was technically part of the same visit, the historical data for that server call is not altered and the visit number remains unchanged.
