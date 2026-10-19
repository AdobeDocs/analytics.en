---
title: Mobile lifecycle metrics
description: Metrics based on data collected using the Mobile SDK.
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Mobile lifecycle metrics

>[!BEGINSHADEBOX]

*This page references data tracked commonly through the Adobe Experience Platform Mobile SDK. For dimensions tracked using the Mobile SDK, see [Mobile lifecycle dimensions](../dimensions/lifecycle-dimensions.md). For mobile device information using user agent, see [Mobile lookup dimensions](../dimensions/mobile-dimensions.md).*

>[!ENDSHADEBOX]

| Lifecycle metric name | Description | Context data variable |
| --- | --- | --- |
| **[!UICONTROL First Launches]** | The number of times the app was run for the first time after it was installed or reinstalled. | `a.InstallEvent` |
| **[!UICONTROL Upgrades]** | The number of times the app was run for the first time after an upgrade, or after its version number changed. | `a.UpgradeEvent` |
| **[!UICONTROL Launches]** | The number of times the app was run, including runs after crashes and installs. A launch is also counted when the app resumes from the background after the lifecycle session timeout is exceeded. | `a.LaunchEvent` |
| **[!UICONTROL Crashes]** | The number of times the app crashed before it was closed. The crash is reported the next time the app is started. | `a.CrashEvent` |
| **[!UICONTROL Total Session Length]** | The total number of seconds that app sessions lasted, based on how long the app was open and in the foreground. Each launch reports the length of the previous session; this metric is the sum of those values. | `a.PrevSessionLength` |
| **[!UICONTROL Action Time Total]** | The total number of seconds (clock time) between the start and end of a timed action, across sessions. Populated by the `trackTimedAction` methods in the legacy Mobile Services SDK (4.x). | `a.action.time.total` |
| **[!UICONTROL Action Time In App]** | The number of seconds spent in the app between the start and end of a timed action, across sessions. Populated by the `trackTimedAction` methods in the legacy Mobile Services SDK (4.x). | `a.action.time.inapp` |
| **[!UICONTROL Lifetime Value (event)]** | The lifetime value of a user, such as lifetime purchases, ad views, video completes, or social shares. Populated by the `trackLifetimeValueIncrease` method in the legacy Mobile Services SDK (4.x). | `a.ltv.amount` |

>[!NOTE]
>
>The [!UICONTROL Action Time Total], [!UICONTROL Action Time In App], and [!UICONTROL Lifetime Value (event)] metrics are populated by methods in the legacy Mobile Services SDK (4.x), which is no longer supported. The Adobe Experience Platform Mobile SDK does not populate these metrics automatically. See [Adobe Mobile Library (v4) to Experience Platform Analytics migration](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) for alternatives to timed actions and lifetime value tracking.
