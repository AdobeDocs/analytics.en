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
* Always include channels for the categories of [Internal](/help/components/c-marketing-channels/mc-faq/c-faq.md) hits and [Direct](/help/components/c-marketing-channels/mc-faq/c-faq.md) hits.

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) page. You associate rules with channels when creating the rule.

## Add marketing channels {#add-mktg-channels}

Add marketing channels in the Marketing Channel Manager.

> [!NOTE] You cannot delete a channel. If you do not want to use a channel, you can disable or rename it, and preserve it for later use.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.

   If you select multiple report suites, select a template that copies settings from the template to the selected report suites.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/getting-started/t-template.md).

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md) page displays.

1. On the [!UICONTROL Marketing Channel Manager] page, click **[!UICONTROL Add Channel]**.

   This option is not available when 25 channels are defined.

1. Click **[!UICONTROL Save.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md).

## Marketing Channel Manager - interface definitions {#mktg-channel-mgr}

Field definitions for the [!UICONTROL Marketing Channel Manager] page.

| Field  | Definition  |
|--- |--- |
|Enabled|Enables or disables this marketing channel.|
|Channel Name|The friendly name of the marketing channel.|
|Override Last-Touch Channel|Lets you choose whether to override an existing, persistent last-touch channel with the selected channel. If you select this checkbox, any channel (including Direct and Internal) would override an existing last-touch channel. The result is conversion being attributed to a channel that might not deserve credit. For example, this option can ensure that the Direct channel does not receive credit for conversion if the user had previously been acquired via the Natural Search channel.|
|Channel Breakdown|Lets you break down a channel by this value. You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/mc-classifications/classifictions-mchannel.md).|
|Type|Specifies how the user came to your site. You can select Online or Offline. Use Online channels for visitors who come through a search engine or email campaign. Offline channels apply to visitors who found your site through newspaper coupons or magazine advertisements. Offline channels usually include data imported through reporting Data Sources. See [Data Sources](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). See [Add Offline Data](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).|
|Color|The color associated with this marketing channel. This color represents the channel in the  Marketing Channel report.|