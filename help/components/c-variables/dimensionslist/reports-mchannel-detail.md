---
title: Marketing channel detail - first and last touch
description: Allocate success metrics and revenue to various channel details without regard to the overall channel they are in.
---

# Marketing channel detail - first and last touch

These reports provide insight on the specific campaigns or keywords are most effective on your site. You can use this report to allocate success metrics and revenue to various channel details, without regard to the overall channel they are in. For example, you can see how a certain paid search keyword compares against an email campaign. As opposed to the Marketing Channel Overview report, this report resembles a standard report.

## Report properties

* This report runs on rules defined in marketing channels. See [Channels and Rules](/help/components/c-marketing-channels/c-channels.md).

  Specifically, the report uses the **[!UICONTROL Set the channel's value to]** part of each rule. Changing these rules or the how the channel's value is set changes how data in this report is calculated. See the Marketing Channel processing rules [FAQ](/help/components/c-marketing-channels/c-faq.md) for more information.

* Differences between *First* and *Last Touch* are located in [About Marketing Channel Reports](/help/components/c-marketing-channels/analyze-mc.md).

* The order of processing rules is crucial to how Marketing Channels work. Each hit checks criteria at the top of your processing rules first, then filters down from there.
* This report can be viewed in trended and ranked formats.
* This report can use a search filter to locate specific line items.
* In addition to various channels collected by standard methods, [offline data sources](/help/components/c-marketing-channels/c-getting-started-mchannel.md) can be used.
* You can use [Classifications](/help/components/c-classifications2/c-classifications.md) in this report, allowing you to rename and consolidate line items. Details specific to Marketing Channels can be found [here](/help/components/c-marketing-channels/classifictions-mchannel.md).

* This report can be broken down by all other Marketing Channel reports.
* The following metrics can be used in this report (depending on organization and report suite settings):
  * Click-throughs: the number of times the *`s.campaign`* variable is defined.
  * New Engagements: the number of visitors who have received a new First Touch Channel.
  * All standard eCommerce metrics: Revenue, Orders, Units, Carts, Cart Views, Checkouts, Cart Additions, Cart Removals.
  * All custom events: Events 1-80, and Events 81-100 if on H22 code or higher.
  * Visits and Visitors: availability is dependent on organization and report suite. Contact your Account Manager for additional details.

  See [Metrics](https://marketing.adobe.com/resources/help/en_US/mchannel/c_overview_metrics.html) in [!UICONTROL Marketing Channel] Help.
