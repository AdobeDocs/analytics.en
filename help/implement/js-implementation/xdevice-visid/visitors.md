---
description: Analytics counts each unique effective visitor ID as a unique visitor.
keywords: Analytics Implementation
seo-description: Analytics counts each unique effective visitor ID as a unique visitor.
seo-title: Visitors
solution: Analytics
subtopic: Visitors
title: Visitors
topic: Developer and implementation
uuid: 82b6c434-cc7c-4140-bb4c-221d56506055
index: y
internal: n
snippet: y
---

# Visitors

Analytics counts each unique effective visitor ID as a unique visitor.

 If you look at the [previous table](../../js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 3 times: at hits 1, 9, and 10. This occurs because the effective [!UICONTROL visitor ID] is the same for both server calls, and occurs even though the visits might be several hours apart and on different devices.

This can increase the number of unique visitors you see when cross-device visitor identification is enabled. The visitor might be counted twice on the same visit: once for the initial visit and again after the user is authenticated.

When a new visitor views your site, the `s_vi`cookie is populated and stored. On the data collection server, a new visitor profile is created for this visitor ID, and the effective [!UICONTROL visitor ID] on the profile is set to match the cookie.

When cross-device visitor identification is enabled, if a [!UICONTROL visitor ID] variable is provided in a subsequent hit (for example, after authentication), the effective [!UICONTROL visitor ID] is updated to match the custom value. This can cause the effective [!UICONTROL visitor ID] to change directly after authentication, resulting in multiple visitor counts. 

![](assets/visitors.png)

After the initial association, visit counts return to normal because the visitor is associated through the [!UICONTROL visitor ID] cookie. If the visitor later views your site and then authenticates, the visitor count is not inflated because the effective [!UICONTROL visitor ID] doesn't change after authentication. 

![](assets/visitors_2.png)

