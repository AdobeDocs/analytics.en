---
title: Mobile lifecycle dimensions
description: Dimensions based on data collected using the Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
---
# Mobile lifecycle dimensions

*This page reference data tracked commonly through the Adobe Experience Platform Mobile SDK. For mobile device information using user agent, see [Mobile lookup dimensions](mobile-dimensions.md). For metrics tracked using the Mobile SDK, see [Mobile lifecycle metrics](../metrics/lifecycle-metrics.md).*

| Lifecycle dimension name | Description | Context data variable |
| --- | --- | --- |
| [!UICONTROL First Launch Date] | | |
| [!UICONTROL Device Name (SDK)] | | `a.DeviceName` |
| [!UICONTROL Operating System Version (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Acquisition Source] | | `a.referrer.campaign.source` |
| [!UICONTROL App Id] | | `a.AppID` |
| [!UICONTROL Acquisition Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL Acquisition Term] | | `a.referrer.campaign.term` |
| [!UICONTROL Acquisition Content] | | `a.refferer.campaign.content` |
| [!UICONTROL Acquisition Name] | | `a.referrer.campaign.name` |
| [!UICONTROL Location (down to 10 km)] | The visitor's latitude and longitude, accurate to the first decimal place. For example, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Location (down to 100 m)] | The visitor's latitude and longitude, accurate to the third decimal place. For example, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL Location (down to 1 m)] | The visitor's latitude and longitude, accurate to the fifth decimal place. For example, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL Point of Interest Name] | | `a.loc.poi` |
| [!UICONTROL Distance to Point of Interest Center] | | `a.loc.dist` |
| [!UICONTROL Launch Number] | | `a.Launches` |
| [!UICONTROL Days Since First Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Action Name] | | |
| [!UICONTROL Lifetime Value (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon Major] | | |
| [!UICONTROL Beacon Minor] | | |
| [!UICONTROL Beacon UUID] | | |
| [!UICONTROL Beacon Proximity] | | |
| [!UICONTROL Days Since Last Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hour of Day (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Day of Week (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Point of Interest ID] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
