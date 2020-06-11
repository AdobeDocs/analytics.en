---
title: Last touch channel
description: The most recent marketing channel within the visitor's engagement expiration.
---

# Last touch channel

The 'Last touch channel' dimension reports the most recent marketing channel a visitor matches with during that visitor's engagement period (30 days by default). This dimension is valuable in understanding which marketing channels drive traffic to your site that result in conversions, allowing you to focus marketing efforts in areas that are most effective.

## Populate this dimension with data

This dimension directly references channel names that you have defined in the [Marketing channel manager](/help/admin/admin/marketing-channels-admin.md).

Every hit sent to Adobe data collection servers run through your report suite's Marketing channel processing rules. It iterates through each rule in numeric order until it finds a match, in which that marketing channel ties to the hit. The last touch channel persists with the visitor until they don't visit the site for longer than the visitor engagement period (30 days by default).

If you want to set this dimension to a specific value, the following steps are required:

* Set the desired dimension value as a channel in the Marketing channel manager under Report suite settings.
* Set a Marketing channel processing rule that contains the desired criteria for the hit.
* The visitor's hit to your site must match the criteria outlined in the Marketing channel processing rule.

## Dimension values

Dimension values include any channel name in the Marketing channel manager. By default, values include `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`, and `"Referring domains"`. You can add or delete channels in the Marketing channel manager, which affect this dimension's values.
