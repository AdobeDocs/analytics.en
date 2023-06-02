---
title: Tracking Code
description: The name of the tracking code or campaign.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
---
# Tracking Code

The 'Tracking Code' dimension lists the names of tracking codes on your site. You can place links with different query string parameter values in different places across the internet. This dimension helps you understand which links were the most successful in driving traffic to your site.

Appending tracking code query strings are common in emails, advertisements, social media posts, and other marketing efforts that your organization uses.

## Populate this dimension with data

This dimension retrieves data from the [`v0` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`campaign`](/help/implement/vars/page-vars/campaign.md) variable.

## Dimension items

Dimension items include the names of tracking codes on your site. Your organization determines what specific dimension items you want to use. See [Campaign tracking](/help/implement/use-cases/campaign-tracking.md) for more information.

## Compare the Tracking code dimension with Marketing channels that collect tracking codes

Some users who set up marketing channel processing rules configure a rule that takes all values used in the Tracking code dimension. Though an excellent practice, they are different because of inherent processing and architecture differences. The following list explains why these two methods, though similar at a glance, can change attribution behavior.

### Prior channels in processing rules

Marketing channels processing rules higher up in the list can prevent hits from attributing to your Tracking Codes marketing channel. For example:

  1. You have 'Social Networks' set up as your first rule, and 'Tracking codes' as your second.
  2. A user posts a link to your site containing a tracking code on a social media site, and several of their friends click on that link to your site.

  Since 'Social Networks' is the first marketing channel processing rule, these users attribute to the 'Social Networks' marketing channel, and not your Tracking codes marketing channel.
  
### Other marketing channels can take attribution through last touch

When dealing with a standard Tracking Codes dimension, you don't need to worry about other parts of your site stealing attribution. However, with Marketing channels, a user can match a different rule, giving different attribution. For example:
  1. You have 'Tracking codes' as your first channel, and 'Direct' as your second.
  2. A user initially arrives to your site through a tracking code, but then leaves.
  3. The next day, they type your URL into their address bar, then make a purchase.

  In this example, the Tracking codes marketing channel would not get last touch credit for that purchase. Instead, it would go to the 'Direct' marketing channel.
  
  
### Expiration differences

Marketing channels have a rolling 30-day visitor engagement expiration, whether a channel was touched or not. Tracking codes have an expiration based on when the variable was set. For example:
  1. You have a visitor engagement expiration of 30 days, and also configured the Tracking Code dimension to expire after 30 days.
  2. A user arrives to your site through a tracking code. They browse the site, then leave.
  3. Three weeks later, they come back without a tracking code or marketing channel, then leave again.
  4. Another two weeks later (five weeks from their initial visit), they come back without a tracking code or marketing channel, then make a purchase.

  The user ultimately made a purchase beyond 30 days, but was never inactive for more than 30 days. In this case, you would see revenue attributed to the the Tracking codes marketing channel, but not for the Tracking code dimension itself. 
  
  
  
