---
description: Add or enable marketing channels in the Marketing Channel Manager. For report suites that have no marketing channels, an automatic setup lets you create several channels for you, along with their rules. You can edit predefined channels to suit your needs, or create your own (up to a total of 25).
seo-description: Add or enable marketing channels in the Marketing Channel Manager. For report suites that have no marketing channels, an automatic setup lets you create several channels for you, along with their rules. You can edit predefined channels to suit your needs, or create your own (up to a total of 25).
seo-title: Manage marketing channels
solution: Analytics
subtopic: Marketing channels
title: Manage marketing channels
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
---

# Manage marketing channels

Add or enable marketing channels in the Marketing Channel Manager. For report suites that have no marketing channels, an automatic setup lets you create several channels for you, along with their rules. You can edit predefined channels to suit your needs, or create your own (up to a total of 25).

## Manage marketing channels {#topic_45CF1C6A783B4F96ABF6317EAB6A854F}

Add or enable marketing channels in the [!UICONTROL Marketing Channel Manager]. For report suites that have no marketing channels, an automatic setup lets you create several channels for you, along with their rules. You can edit predefined channels to suit your needs, or create your own (up to a total of 25). 

Here are guidelines for creating channels:

* Plan ahead by making a list of all your channels, so that all of your visitor hits are categorized to the right channel. 
* Always include channels for the categories of [Internal](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947) hits and [Direct](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A) hits.

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08) page. You associate rules with channels when creating the rule. 

## Add marketing channels {#task_98C9D3F5DBBC4B198E0A9ED4D3891E03}

Add marketing channels in the Marketing Channel Manager.

>[!NOTE]
>
>You cannot delete a channel. If you do not want to use a channel, you can disable or rename it, and preserve it for later use.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.

   If you select multiple report suites, select a template that copies settings from the template to the selected report suites.

   See [Apply template report suite settings to multiple report suites](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC). 

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) page displays. 

1. On the [!UICONTROL Marketing Channel Manager] page, click **[!UICONTROL Add Channel]**.

   This option is not available when 25 channels are defined. 

1. Click **[!UICONTROL Save.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08). 

## Marketing Channel Manager - interface definitions {#reference_01779A2928054BF48339897D4033AFB9}

Field definitions for the [!UICONTROL Marketing Channel Manager] page.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enabled </p> </td> 
   <td colname="col2"> <p> Enables or disables this marketing channel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Channel Name </p> </td> 
   <td colname="col2"> <p>The friendly name of the marketing channel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Override Last-Touch Channel </p> </td> 
   <td colname="col2"> <p> Lets you choose whether to override an existing, persistent last-touch channel with the selected channel. If you select this checkbox, any channel (including Direct and Internal) would override an existing last-touch channel. The result is conversion being attributed to a channel that might not deserve credit. For example, this option can ensure that the Direct channel does not receive credit for conversion if the user had previously been acquired via the Natural Search channel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Channel Breakdown </p> </td> 
   <td colname="col2"> <p>Lets you break down a channel by this value. You can add possible channel breakdowns (subchannels) when creating marketing channel classifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p> Specifies how the user came to your site. You can select <span class="uicontrol"> Online</span> or <span class="uicontrol"> Offline</span>. Use Online channels for visitors who come through a search engine or email campaign. Offline channels apply to visitors who found your site through newspaper coupons or magazine advertisements. Offline channels usually include data imported through reporting Data Sources. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" scope="external" format="http"> Data Sources</a>. </p> <p>See <a href="../../components/c-marketing-channels/t-offline-data.md#task_FC96E6A48F0D4D37A79BD234E90DAA26" type="task" format="dita" scope="local"> Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Color </p> </td> 
   <td colname="col2"> <p>The color associated with this marketing channel. This color represents the channel in the <span class="wintitle"> Marketing Channel</span> report. </p> </td> 
  </tr> 
 </tbody> 
</table>

