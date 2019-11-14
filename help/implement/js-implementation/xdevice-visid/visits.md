---
description: Analytics counts a visit each time a server call occurs with a Visit Page Number equal to 1.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Visits
topic: Developer and implementation
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
---

# Visits

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics counts a visit each time a server call occurs with a Visit Page Number equal to 1.

 If you look at the [previous table](/help/implement/js-implementation/xdevice-visid/visit-example.md), this occurred 4 times: at hits 1, 9, 11, and 12. Similar to visitors, this value returns to normal after the initial association because the [!UICONTROL Visit Page Number] is reset back to 1 due to a change in the effective [!UICONTROL visitor ID].
