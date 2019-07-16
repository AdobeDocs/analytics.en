---
description: Overview of how enabling cross-device visitor identification affects the data that you see in reports.
keywords: Analytics Implementation
seo-description: Overview of how enabling cross-device visitor identification affects the data that you see in reports.
seo-title: Data impact of cross-device visitor identification
solution: Analytics
subtopic: Visitors
title: Data impact of cross-device visitor identification
topic: Developer and implementation
uuid: 1db4d149-cd50-4b41-a850-988901f25051
---

# Data impact of cross-device visitor identification

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Overview of how enabling cross-device visitor identification affects the data that you see in reports.

 To understand how this feature affects data collection, it is useful to understand the visitor data fields in a visitor profile: 

|  Data Field  | Description  |
|---|---|
|  Visitor ID cookie  |ID generated automatically on the first visit from a device or browser and stored in the `s_vi` cookie.  |
|  Visitor ID variable  |Optional [!UICONTROL visitor ID] that is set using the `s.visitorID` variable. This value is populated after a user authenticates and might match an ID that your company uses to track a user across multiple digital marketing channels.  |
|  Effective Visitor ID  |The effective [!UICONTROL visitor ID] is the actual ID for the user profile. This value is set to the [!UICONTROL visitor ID] cookie, or to the [!UICONTROL visitor ID] variable if one is provided.  |

