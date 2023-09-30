---
title: Mobile lifecycle dimensions
description: Dimensions based on data collected using the Mobile SDK.
feature: Dimensions
---
# Mobile lifecycle dimensions


| Lifecycle dimension name | Description | Context data variable |
| --- | --- | --- |
| First Launch Date | | TBD (is this install date?) |
| Device Name (SDK) | | `a.DeviceName` |
| Operating System Version (SDK) | | `a.OSVersion` |
| Resolution (SDK) | | `a.Resolution` |
| Acquisition Source | | `a.referrer.campaign.source` |
| App Id | | `a.AppID` |
| Acquisition Medium | | `a.referrer.campaign.medium` |
| Acquisition Term | | `a.referrer.campaign.term` |
| Acquisition Content | | `a.refferer.campaign.content` |
| Acquisition Name | | `a.referrer.campaign.name` |
| Location (down to 10 km) | | `a.loc.lat.a` + `a.loc.lon.a` |
| Location (down to 100 m) | | `a.loc.lat.b` + `a.loc.lon.b` |
| Location (down to 1 m) | | `a.loc.lat.c` + `a.loc.lon.c` |
| Point of Interest Name | | `a.loc.poi` |
| Distance to Point of Interest Center | | `a.loc.dist` |
| Launch Number | | `a.Launches` |
| Days Since First Use | | `a.DaysSinceFirstUse` |
| Action Name | | TBD |
| Lifetime Value (evar) | | `a.ltv.amount` |
| Beacon Major | | TBD |
| Beacon Minor | | TBD |
| Beacon UUID | | TBD |
| Beacon Proximity | | TBD |
| Days Since Last Use | | `a.DaysSinceFirstUse` |
| Hour of Day (SDK) | | `a.HourOfDay` |
| Day of Week (SDK) | | `a.DayOfWeek` |
| Point of Interest ID | | TBD |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
