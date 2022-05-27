---
title: Lifecycle mapping for dimensions and metrics
description: See how the Edge Network automatically maps Lifecycle variables to XDM fields.
---

# Lifecycle mapping for dimensions and metrics

When you send Mobile SDK data to Adobe Experience Platform Edge, some variables are automatically mapped to XDM fields. The following tables show which lifecycle dimensions and metrics are automatically mapped, and which XDM fields that they automatically map to.

If you want to populate a given dimension or metric with data, make sure that the mapped XDM field contains data. Adobe automatically translates that content to the associated context data variable when sending it to Analytics.

## Dimensions

| Dimension | Context data variable | Mapped XDM field | Notes |
| --- | --- | --- | --- |
| App ID | `a.AppID` | `id` | Currently being populated by `id`. A future release will change this to `<name> <version>`. |
| Operating System Version | `a.OSVersion` | `Environment.operatingSystem` + `Environment.operatingSystemVersion` | |
| Device Name | `a.DeviceName` | `Device.model` | |
| Carrier Name | `a.CarrierName` | `Environment.carrier` | |
| Resolution | `a.Resolution` | `Device.screenWidth` + `Device.screenHeight` | |

The following dimensions are automatically derived in CJA based on other fields, and do not need XDM mappings:

* Install Date (`a.InstallDate`)
* Launch Number (`a.Launchees`)
* Days Since First Use (`a.DaysSinceFirstUse`)
* Days Since Last Use (`a.DaysSinceLastUse`)
* Hour of Day (`a.HourOfDay`)
* Day of Week (`a.DayOfWeek`)
* Days Since Last Upgrade (`a.DaysSinceLastUpgrade`)
* Launches Since Upgrade (`a.LaunchesSinceUpgrade`)

## Metrics

| Metric | Context data variable | Mapped XDM field | Notes |
| --- | --- | --- | --- |
| First Launches | `a.InstallEvent` | `isLaunch` and `isInstall` | |
| Upgrades | `a.UpgradeEvent` | `isUpgrade` | |
| Launches | `a.LaunchEvent` | `isLaunch` | An increase of this metric is expected, as it now counts every app launch or when the app is brought into the foreground |
| Crashes | `a.CrashEvent` | `isClose` and `closeType=unknown` | An increase of this metric is expected, as it is now sent on every launch instead of when the Analytics session times out. |
| Previous Session Length | `a.PrevSessionLength` | `Application.sessionLength` | |

The following metrics are automatically derived in CJA based on other fields, and do not need XDM mappings:

* Daily Engaged Users (`a.DailyEngUserEvent`)
* Monthly Engaged Users (`a.MonthlyEngUserEvent`)
