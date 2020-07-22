---
title: Tracking Code
description: The name of the tracking code or campaign.
---

# Tracking Code

The 'Tracking Code' dimension lists the names of tracking codes on your site. This dimension is typically collected using query string parameters. You can place links with different query string parameter values in different places across the internet. This dimension reports which links were the most successful in driving traffic to your site.

## Populate this dimension with data

This dimension retrieves data from the [`v0` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`campaign`](/help/implement/vars/page-vars/campaign.md) variable.

## Dimension items

Dimension items include the names of tracking codes on your site. Your organization determines what specific dimension items you want to use.
