---
description: Overview of how enabling cross-device visitor identification affects the data that you see in reports.
keywords: Analytics Implementation
seo-description: Overview of how enabling cross-device visitor identification affects the data that you see in reports.
seo-title: Data impact of cross-device visitor identification
solution: Analytics
subtopic: Visitors
title: Data impact of cross-device visitor identification
topic: Developer and implementation
uuid: 4931e4c4-5879-48f8-9d0f-fd7f0b3ae8f7
index: y
internal: n
snippet: y
---

# Data impact of cross-device visitor identification

Overview of how enabling cross-device visitor identification affects the data that you see in reports.

 To understand how this feature affects data collection, it is useful to understand the visitor data fields in a visitor profile: 

|  Data Field  | Description  |
|---|---|
|  Visitor ID cookie  |ID generated automatically on the first visit from a device or browser and stored in the `s_vi` cookie.  |
|  Visitor ID variable  |Optional [!UICONTROL visitor ID] that is set using the `s.visitorID` variable. This value is populated after a user authenticates and might match an ID that your company uses to track a user across multiple digital marketing channels.  |
|  Effective Visitor ID  |The effective [!UICONTROL visitor ID] is the actual ID for the user profile. This value is set to the [!UICONTROL visitor ID] cookie, or to the [!UICONTROL visitor ID] variable if one is provided.  |

