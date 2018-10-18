---
description: Before channels and channel data can be displayed in the report, create the channels and the underlying rules that process data. You can also create cost and budget amounts for associated channels, and specify how long you want the visitor engagement period to last. You perform report configuration tasks in Admin Tools.
seo-description: Before channels and channel data can be displayed in the report, create the channels and the underlying rules that process data. You can also create cost and budget amounts for associated channels, and specify how long you want the visitor engagement period to last. You perform report configuration tasks in Admin Tools.
seo-title: About channels and rules
solution: Analytics
subtopic: Marketing channels
title: About channels and rules
topic: Reports and analytics
uuid: baef8dc4-ee2e-4ca8-b7b3-b469d6691ed9
index: y
internal: n
snippet: y
---

# About channels and rules

Before channels and channel data can be displayed in the report, create the channels and the underlying rules that process data. You can also create cost and budget amounts for associated channels, and specify how long you want the visitor engagement period to last. You perform report configuration tasks in Admin Tools.

Think of a channel as a container for visits. The rules assign visits to the proper container.

![](assets/buckets_2.png)

Adobe provides several predefined channels during an [automatic setup](../c_marketing_channels/c_channel_autosetup.md#concept_2EC91690B4F94889ADE935AB69B9025D) that you can edit to suit your needs.

>[!NOTE]
>
>Adobe recommends that you set up your report in a report suite that you can use as a template for testing purposes. You can use the template to apply channel and rule sets globally to one or more production report suites. 
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](../c_marketing_channels/t_template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

Review the following topics:

* [Prerequisites](../c_marketing_channels/c_channels_rules.md#section_9913D2932E3140C099B7978CA95378B2) 
* [Important processing notes](../c_marketing_channels/c_channels_rules.md#section_DE372EEF02314F2395750CF2892DAAE1)

## Prerequisites {#section_9913D2932E3140C099B7978CA95378B2}

If necessary, contact Customer Care to assist you with these prerequisites:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

  See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information. 

* Set up user group access to the **[!UICONTROL Marketing Channel Report]**.

  See [Configure User Group Access](../c_marketing_channels/t_user_groups.md#task_B156E7527FE94055A43A697338FE8C8C). 

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#section_DE372EEF02314F2395750CF2892DAAE1}

* The system processes the rules in the order you specify, and when a rule is met, the system stops processing the remaining rules. 
* Rules can access variables that VISTA has set, but cannot access data that VISTA has deleted. 
* Channels store only conversion metrics. Traffic metrics are not available. 
* Two marketing channels never receive credit for the same event (such as purchases or clicks). In this way, marketing channels differ from eVars (where two eVars might receive credit for the same event). 
* The report can process up to 25 channels at a time.

