---
description: Before channels and channel data can be displayed in the report, create the channels and the underlying rules that process data. You can also create cost and budget amounts for associated channels, and specify how long you want the visitor engagement period to last. You perform report configuration tasks in Admin Tools.
subtopic: Marketing channels
title: About channels and rules
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
---

# About channels and rules

Before channels and channel data can be displayed in the report, create the channels and the underlying rules that process data. You can also create cost and budget amounts for associated channels, and specify how long you want the visitor engagement period to last. You perform report configuration tasks in Admin Tools.

Think of a channel as a container for visits. The rules assign visits to the proper container.

![](assets/buckets_2.png)

Adobe provides several predefined channels during an [automatic setup](/help/components/c-marketing-channels/c-channel-autosetup.md) that you can edit to suit your needs.

>[!NOTE]
>
>Adobe recommends that you set up your report in a report suite that you can use as a template for testing purposes. You can use the template to apply channel and rule sets globally to one or more production report suites.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/t-template.md).

Review the following topics:

* [Prerequisites](/help/components/c-marketing-channels/c-channels-rules.md#prereqs) 
* [Important processing notes](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## Prerequisites {#prereqs}

If necessary, contact Customer Care to assist you with these prerequisites:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

  See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Set up user group access to the **[!UICONTROL Marketing Channel Report]**.

  See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#important-proc-rules}

* The system processes the rules in the order you specify, and when a rule is met, the system stops processing the remaining rules.
* Rules can access variables that VISTA has set, but cannot access data that VISTA has deleted.
* Channels store only conversion metrics. Traffic metrics are not available.
* Two marketing channels never receive credit for the same event (such as purchases or clicks). In this way, marketing channels differ from eVars (where two eVars might receive credit for the same event).
* The report can process up to 25 channels at a time.

