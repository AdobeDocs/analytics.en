---
title: First touch channel detail
description: Details for the first marketing channel within the visitor's engagement expiration.
feature: Dimensions
exl-id: a155182d-7bc0-4c7d-9de7-680bfe2d6432
---
# First touch channel detail

The 'First touch channel detail' dimension reports details around the first marketing channel a visitor matches with during that visitor's engagement period (30 days by default). This dimension is valuable in understanding what contributed to the hit matching a marketing channel. For example, if a visitor arrived to your site and matched with the 'Paid search' Marketing channel, you could use the channel detail to see which search engine was used, or which keyword they searched for.

## Populate this dimension with data

This dimension copies values from other variables. The variable used references the channel value within each [Marketing channel processing rule](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md). When a hit matches a marketing channel processing rule, the [Last touch channel](last-touch-channel.md) dimension is set to the channel name, and this dimension is set to the channel value set in the rule.

If you want to set this dimension to a specific value, the following steps are required:

* Make sure that the desired dimension item is in a hit attribute or custom variable.
* Set a Marketing channel processing rule that contains the desired criteria for the hit.
* Select the desired dropdown value under [!UICONTROL Set the channel's value] within the Marketing channel processing rule.
* The visitor's hit to your site must match the criteria outlined in the Marketing channel processing rule _and_ must be the first marketing channel value to do so in the visitor's engagement period.

If a subsequent hit matches criteria under a different Marketing channel, this dimension is not overwritten with the new marketing channel.

## Dimension items

Dimension items depend on the channel value dropdown. For example, if you set the channel's value to 'Page URL', dimension items include page URLs on your site. If you set the channel's value to Referring domain, dimension items include domains that visitors clicked through to get to your site. This dimension aggregates all detail dimension items, regardless of which channel they are in.

Adobe recommends setting channel values related to the marketing channel for insight around channel details.
