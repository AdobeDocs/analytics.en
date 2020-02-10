---

title: Processing rules for Marketing Channels
description: Marketing Channel processing rules determine if a visitor hit meets the criteria assigned to a channel. The rules process every hit a visitor makes on your site. When a rule does not meet the criteria for a channel, or if rules are not configured correctly, the system assigns the hit to No Channel Identified.
---

# Processing rules for Marketing Channels

Marketing Channel processing rules determine if a visitor hit meets the criteria assigned to a channel. The rules process every hit a visitor makes on your site. When a rule does not meet the criteria for a channel, or if rules are not configured correctly, the system assigns the hit to No Channel Identified.

Here are important guidelines for creating rules:

* Sort the rules in the order that you want them to be processed.
* At the end of your list, include a catch-all rule, such as Other. This rule identifies external traffic but not internal traffic.

   See [No Channel Identified.](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified)

> [!NOTE] Although these rules do not affect reporting outside of marketing channels, they affect marketing channel data collection. Data collected with these rules are 100% permanent, and rules altered after data is collected is not retroactive. It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## Prerequisites

* Review the conceptual information in [Getting Started with Marketing Channels](/help/components/c-marketing-channels/getting-started/c-getting-started-mchannel.md).
* Create one or more channels so that you can assign rules to them. See [Add marketing channels.](/help/components/c-marketing-channels/mark-channel-mgr/c-channels.md)
