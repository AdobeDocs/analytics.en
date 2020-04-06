---
description: Add or enable marketing channels in the Marketing Channel Manager. For report suites that have no marketing channels, an automatic setup lets you create several channels for you, along with their rules. You can edit predefined channels to suit your needs, or create your own (up to a total of 25).
subtopic: Marketing channels
title: Manage marketing channels
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
---

# Manage marketing channels

Add or enable marketing channels in the Marketing Channel Manager. For report suites that have no marketing channels, an automatic setup lets you create several channels for you, along with their rules. You can edit predefined channels to suit your needs, or create your own (up to a total of 25).

Here are guidelines for creating channels:

* Plan ahead by making a list of all your channels, so that all of your visitor hits are categorized to the right channel.
* Always include channels for the categories of [Internal](/help/components/c-marketing-channels/c-faq.md) hits and [Direct](/help/components/c-marketing-channels/c-faq.md) hits.

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) page. You associate rules with channels when creating the rule.

## Add marketing channels {#add-mktg-channels}

Add marketing channels in the Marketing Channel Manager.

>[!NOTE] You cannot delete a channel. If you do not want to use a channel, you can disable or rename it, and preserve it for later use.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.

   If you select multiple report suites, select a template that copies settings from the template to the selected report suites.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md) page displays.

1. On the [!UICONTROL Marketing Channel Manager] page, click **[!UICONTROL Add Channel]**.

   This option is not available when 25 channels are defined.

1. Click **[!UICONTROL Save.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](/help/components/c-marketing-channels/c-rules.md).

## Marketing Channel Manager - interface definitions {#mktg-channel-mgr}

Field definitions for the [!UICONTROL Marketing Channel Manager] page.

| Field  | Definition  |
|--- |--- |
|Enabled|Enables or disables this marketing channel.|
|Channel Name|The friendly name of the marketing channel.|
|Override Last-Touch Channel|Lets you choose whether to override an existing, persistent last-touch channel with the selected channel. If you select this checkbox, any channel (including Direct and Internal) would override an existing last-touch channel. The result is conversion being attributed to a channel that might not deserve credit. For example, this option can ensure that the Direct channel does not receive credit for conversion if the user had previously been acquired via the Natural Search channel.|
|Channel Breakdown|Lets you break down a channel by this value. You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/classifictions-mchannel.md).|
|Type|Specifies how the user came to your site. You can select Online or Offline. Use Online channels for visitors who come through a search engine or email campaign. Offline channels apply to visitors who found your site through newspaper coupons or magazine advertisements. Offline channels usually include data imported through reporting Data Sources. See [Data Sources](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). See [Add Offline Data](/help/components/c-marketing-channels/c-getting-started-mchannel.md).|
|Color|The color associated with this marketing channel. This color represents the channel in the  Marketing Channel report.|

## Define channels

Before channels and channel data can be displayed in the report, create the channels and the underlying rules that process data. You can also create cost and budget amounts for associated channels, and specify how long you want the visitor engagement period to last. You perform report configuration tasks in Admin Tools.

Think of a channel as a container for visits. The rules assign visits to the proper container.

![](assets/buckets_2.png)

Adobe provides several predefined channels during an [automatic setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md) that you can edit to suit your needs.

>[!NOTE]
>
>Adobe recommends that you set up your report in a report suite that you can use as a template for testing purposes. You can use the template to apply channel and rule sets globally to one or more production report suites.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Prerequisites {#prereqs}

If necessary, contact Customer Care to assist you with these prerequisites:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

  See [General Account Settings](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) in Analytics help for more information.

* Set up access to the Marketing Channel dimensions.

  See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### Important processing notes {#important-proc-rules}

* The system processes the rules in the order you specify, and when a rule is met, the system stops processing the remaining rules.
* Rules can access variables that VISTA has set, but cannot access data that VISTA has deleted.
* Channels store only conversion metrics. Traffic metrics are not available.
* Two marketing channels never receive credit for the same event (such as purchases or clicks). In this way, marketing channels differ from eVars (where two eVars might receive credit for the same event).
* The report can process up to 25 channels at a time.

