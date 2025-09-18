---
description: Combine both timestamped and non-timestamped data into a single report suite.
title: Timestamps configuration
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
---
# Timestamps configuration

The '[!UICONTROL Timestamps configuration]' admin page allows you to enable **[!UICONTROL Timestamps optional]** for one or more report suites. This setting lets you combine both timestamped and non-timestamped data into a single report suite.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Timestamps optional]**

## Current timestamp setting

This section shows your current timestamp configuration for the selected report suite. It can be one of three possible values:

* **Timestamps not allowed (setting `visitorID` supported)**
* **Timestamps required (setting `visitorID` not supported)**
* **Timestamps optional (setting `visitorID` supported but not on timestamped hits)**

Below this text is a check box labeled **[!UICONTROL Convert selected report suites to Timestamps optional]**. Selecting this check box then selecting **[!UICONTROL Save]** Enables [!UICONTROL Timestamps optional] for the selected report suites.

## Timestamps not allowed

When you send data to a report suite using this timestamp configuration, the timestamp is when Adobe's processing servers receive the hit. If you attempt to set the [`timestamp`](/help/implement/vars/page-vars/timestamp.md) variable, the hit is permanently dropped.

## Timestamps required

When you send data to a report suite using this timestamp configuration, every hit must include the [`timestamp`](/help/implement/vars/page-vars/timestamp.md) variable. If any hit is missing a `timestamp` implementation variable, the hit is permanently dropped.

Timestamp-enabled session data is kept for up to 92 days. In other words, a visit is "held open" for 92 days, allowing any additional hits to be included in the same visit/session. While you can add data to existing sessions, Adobe recommends adding hits in order per visitor. Hits that are received out of order per visitor can produce unexpected reporting results, though many of these limitations are mitigated with report-time processing.

## Timestamps optional

The '[!UICONTROL Timestamps optional]' setting allows you to integrate and report across multiple report suites with or without the [`timestamp`](/help/implement/vars/page-vars/timestamp.md) variable. Ideal use cases for [!UICONTROL Timestamps optional] include:

* Mix timestamped and non-timestamped data in the same global report suite
* Send timestamped data from a mobile app to a global report suite
* Upgrade apps to use offline tracking without having to create a new report suite

This setting is enabled by default for all new report suites, unless the new report suite was copied from a report suite with a different timestamp configuration setting.

>[!WARNING]
>
>If you use [!UICONTROL Timestamps optional], do not set [`visitorID`](/help/implement/vars/config-vars/visitorid.md) on timestamped data. This action can lead to out-of-order data and negatively impact time calculations (such as time spent), attribution, visit number/visit counts, and pathing reports.

Once you enable [!UICONTROL Timestamps optional], you cannot disable it in this interface. In the unlikely scenario that you want to switch back to another timestamp configuration setting, contact Adobe Customer Care.
