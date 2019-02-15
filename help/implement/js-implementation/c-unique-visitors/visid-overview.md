---
description: Adobe uses a cookie to track unique browsers/devices.
keywords: Analytics Implementation
seo-description: Adobe uses a cookie to track unique browsers/devices.
seo-title: Identify unique visitors
solution: Analytics
subtopic: Visitors
title: Identify unique visitors
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
---

# Identify unique visitors

Adobe uses a cookie to track unique browsers/devices.

## Analytics Visitor ID Order {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics provides several mechanisms to identify visitors. The following table lists the different ways a visitor can be identified in Analytics (in order of preference): 

|  Order Used  | Query Parameter (collection method)  | Present When  |
|---|---|---|
|   ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8)  | s.visitorID is set  |
|   ![](assets/step2_icon.png) | [aid (s_vi cookie)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC)  | Visitor had an existing s_vi cookie before you deployed the Visitor ID service, or you have a visitor ID grace period configured.  |
|   ![](assets/step3_icon.png) | [mid (AMCV_ cookie set by Experience Cloud Visitor ID service)](https://marketing.adobe.com/resources/help/en_US/mcvid/)  | Visitor's browser accepts cookies (first-party)  |
|   ![](assets/step4_icon.png) | [fid (fallback cookie on H.25.3 or newer, or AppMeasurement for JavaScript)](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505)  | Visitor's browser accepts cookies (first-party)  |
|   ![](assets/step5_icon.png) | [IP Address, User Agent, Gateway IP Address](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF)  | Visitor's browser does not accept cookies.  |

In many scenarios you might see 2 or 3 different IDs on a call, but Analytics will use the first ID present from the previous table as the official visitor ID. For example, if you are setting a custom visitor ID (included in the "vid" query parameter), that ID will be used before other IDs that might be present on that same hit.

>[!NOTE]
>
>Each Analytics visitor ID is associated with a visitor profile on Adobe servers. Visitor profiles are deleted after at least 13 months of inactivity regardless of any visitor ID cookie expiration.
