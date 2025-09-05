---
description: Enable dimensions and metrics for use in mobile application tracking.
title: App Reporting
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
---
# App Reporting

The App Reporting interface allows you to enable lifecycle dimensions and metrics that are dedicated for use in mobile application tracking.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**

>[!IMPORTANT]
>
>Once any of these features are enabled, they cannot be disabled. Enabling a given feature makes its respective dimensions and metrics permanently available in Analysis Workspace.

## [!UICONTROL App Reports]

[!UICONTROL App Reports] dimensions and metrics are used for the following purposes:

* **Acquisition**: Track referring URLs for app download campaigns.
* **Lifecycle**: Foundation level of reporting provided by measurement sent on each app launch.
* **App Actions**: Reports and pathing based on in-app actions.
* **Lifetime Value**: Understand how users accrue value over time using app KPIs (such as purchases, ad views, video completes, social shares, photo uploads).
* **Timed Events**: Measure the amount of time that elapses (in-app & total time) between key app actions (such as time before first purchase).

When you enable [!UICONTROL App Reports], the following dimensions are available:

* [!UICONTROL Action Name] (with [Entry](/help/components/dimensions/entry-dimensions.md) and [Exit](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL App Id]
* [!UICONTROL Acquisition Content]
* [!UICONTROL Acquisition Medium]
* [!UICONTROL Acquisition Name]
* [!UICONTROL Acquisition Source]
* [!UICONTROL Acquisition Term]
* [!UICONTROL Day of Week (SDK)]
* [!UICONTROL Days Since First Use]
* [!UICONTROL Days Since Last Use]
* [!UICONTROL Device Name (SDK)]
* [!UICONTROL Hour of Day (SDK)]
* [!UICONTROL First Launch Date]
* [!UICONTROL Launch Number]
* [!UICONTROL Lifetime Value (evar)]
* [!UICONTROL Operating System Version (SDK)]
* [!UICONTROL Resolution (SDK)]

The following metrics are available:

* [!UICONTROL Action Time In App]
* [!UICONTROL Action Time Total]
* [!UICONTROL Crashes]
* [!UICONTROL First Launches]
* [!UICONTROL Launches]
* [!UICONTROL Lifetime Value (event)]
* [!UICONTROL Total Session Length]
* [!UICONTROL Upgrades]

## [!UICONTROL Location Tracking]

[!UICONTROL Location Tracking] dimensions are used for the following purposes:

* Track latitude and longitude data
* Identify, create, and visualize specific Points of interest. Points of interest must be defined in the mobile SDK configuration file.
* Track bluetooth beacons (UUID, major, minor, and proximity).

When you enable [!UICONTROL Location Tracking], the following dimensions are available:

* [!UICONTROL Beacon Major] (with [Entry](/help/components/dimensions/entry-dimensions.md) and [Exit](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Beacon Minor] (with [Entry](/help/components/dimensions/entry-dimensions.md) and [Exit](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Beacon Proximity] (with [Entry](/help/components/dimensions/entry-dimensions.md) and [Exit](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Beacon UUID] (with [Entry](/help/components/dimensions/entry-dimensions.md) and [Exit](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Location (down to 10 km)]
* [!UICONTROL Location (down to 100 m)]
* [!UICONTROL Location (down to 1 m)]
* [!UICONTROL Point of Interest Name]
* [!UICONTROL Distance to Point of Interest Center]
* [!UICONTROL Point of Interest ID]

## [!UICONTROL Voice and Chatbots]

[!UICONTROL Voice and Chatbots] dimensions and metrics allow you to measure voice assistants such as Alexa or Google Home. It also allows you to measure home-grown chat bots. Measurement properties include:

* **Lifecycle**: Foundation level of reporting for any app, such as the number of launches and platform type.
* **Conversations**: Measures intents, responses, and other metrics and dimensions related to the conversation.

When you enable [!UICONTROL Voice and Chatbots], the following dimensions are available:

* [!UICONTROL Voice Device Capabilities] (with [Entry](/help/components/dimensions/entry-dimensions.md) and [Exit](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Voice Authentication]
* [!UICONTROL Voice Error Type]
* [!UICONTROL Voice Intent]
* [!UICONTROL Voice App Response]
* [!UICONTROL Voice Language]

The following metrics are available:

* [!UICONTROL Voice End Session]
* [!UICONTROL Voice Error]
* [!UICONTROL Voice Utterances]

## Legacy Reporting and Attribution for Background Hits

Legacy reporting means that hits generated when an app is in the background are treated as regular foreground hits. They show up in reports and affect attribution. This legacy configuration is typically desirable to maintain consistency with legacy implementations.

Adobe recommends disabling legacy reporting so that background hits are not visible. If you want to include background hits in your analysis, you can enable the [Virtual report suite](/help/components/vrs/vrs-about.md) setting **[!UICONTROL Include background hits]**.
