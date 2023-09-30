---
title: Mobile lifecycle dimensions
description: Dimensions based on data collected using the Mobile SDK.
feature: Dimensions
---
# Mobile lifecycle dimensions

*This page reference data tracked commonly through the Adobe Experience Platform Mobile SDK. For mobile device information using user agent, see [Mobile lookup dimensions](mobile-dimensions.md). For metrics tracked using the Mobile SDK, see [Mobile lifecycle metrics](../metrics/lifecycle-metrics.md).*

| Lifecycle dimension name | Description | Context data variable |
| --- | --- | --- |
| [!UICONTROL First Launch Date] | | TBD (is this install date?) |
| [!UICONTROL Device Name (SDK)] | | `a.DeviceName` |
| [!UICONTROL Operating System Version (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Acquisition Source] | | `a.referrer.campaign.source` |
| [!UICONTROL App Id] | | `a.AppID` |
| [!UICONTROL Acquisition Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL Acquisition Term] | | `a.referrer.campaign.term` |
| [!UICONTROL Acquisition Content] | | `a.refferer.campaign.content` |
| [!UICONTROL Acquisition Name] | | `a.referrer.campaign.name` |
| [!UICONTROL Location (down to 10 km)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Location (down to 100 m)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL Location (down to 1 m)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL Point of Interest Name] | | `a.loc.poi` |
| [!UICONTROL Distance to Point of Interest Center] | | `a.loc.dist` |
| [!UICONTROL Launch Number] | | `a.Launches` |
| [!UICONTROL Days Since First Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Action Name] | | TBD |
| [!UICONTROL Lifetime Value (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon Major] | | TBD |
| [!UICONTROL Beacon Minor] | | TBD |
| [!UICONTROL Beacon UUID] | | TBD |
| [!UICONTROL Beacon Proximity] | | TBD |
| [!UICONTROL Days Since Last Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hour of Day (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Day of Week (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Point of Interest ID] | | TBD |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
