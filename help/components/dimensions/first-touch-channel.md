---
title: First touch channel
description: The first marketing channel within the visitor's engagement expiration.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
---
# First touch channel

The 'First touch channel' dimension reports the first marketing channel a visitor matches with during that visitor's engagement period (30 days by default). This dimension is valuable in understanding which marketing channels drive initial traffic to your site, allowing you to focus marketing efforts in areas that are most effective.

## Populate this dimension with data

This dimension directly references channel names that you have defined in the [Marketing channel manager](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Every hit sent to Adobe data collection servers run through your report suite's Marketing channel processing rules. It iterates through each rule in numeric order until it finds a match, in which that marketing channel ties to the hit. The first touch channel persists with the visitor until they don't visit the site for longer than the visitor engagement period (30 days by default).

If you want to set this dimension to a specific value, the following steps are required:

* Set the desired dimension item as a channel in the Marketing channel manager under Report suite settings.
* Set a Marketing channel processing rule that contains the desired criteria for the hit.
* The visitor's hit to your site must match the criteria outlined in the Marketing channel processing rule, _and_ must be the first marketing channel value to do so in the visitor's engagement period.

If a subsequent hit matches criteria under a different Marketing channel, this dimension is not overwritten with the new marketing channel.

## Dimension items

Dimension items include any channel name in the Marketing channel manager. By default, values include `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`, and `"Referring domains"`. You can add or delete channels in the Marketing channel manager, which affect this dimension's values.
