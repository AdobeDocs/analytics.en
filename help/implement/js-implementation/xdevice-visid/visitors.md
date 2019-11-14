---
description: Analytics counts each unique effective visitor ID as a unique visitor.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Visitors
topic: Developer and implementation
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
---

# Visitors

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics counts each unique effective visitor ID as a unique visitor.

 If you look at the [previous table](/help/implement/js-implementation/xdevice-visid/visit-example.md), this occurred 3 times: at hits 1, 9, and 10. This occurs because the effective [!UICONTROL visitor ID] is the same for both server calls, and occurs even though the visits might be several hours apart and on different devices.

This can increase the number of unique visitors you see when cross-device visitor identification is enabled. The visitor might be counted twice on the same visit: once for the initial visit and again after the user is authenticated.

When a new visitor views your site, the `s_vi`cookie is populated and stored. On the data collection server, a new visitor profile is created for this visitor ID, and the effective [!UICONTROL visitor ID] on the profile is set to match the cookie.

When cross-device visitor identification is enabled, if a [!UICONTROL visitor ID] variable is provided in a subsequent hit (for example, after authentication), the effective [!UICONTROL visitor ID] is updated to match the custom value. This can cause the effective [!UICONTROL visitor ID] to change directly after authentication, resulting in multiple visitor counts.

![](assets/visitors.png)

After the initial association, visit counts return to normal because the visitor is associated through the [!UICONTROL visitor ID] cookie. If the visitor later views your site and then authenticates, the visitor count is not inflated because the effective [!UICONTROL visitor ID] doesn't change after authentication.

![](assets/visitors_2.png)

