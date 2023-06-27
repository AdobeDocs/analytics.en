---
title: Entry dimensions
description: Lists entry dimensions and their use.
keywords: entry page, entry site section, entry server, entry custom insight
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
---
# Entry dimensions

*This help page describes how entries work as a dimension. For information on how entries work as a metric, see the [Entries](../metrics/entries.md) metric.*

Entry dimensions are [visit-based](../metrics/visits.md). They record the first dimension item, and persist it for the entire duration of that visit. Entry dimensions are available for all variables with pathing enabled under [Traffic variables](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) in Report suite settings.

## Populate entry dimensions with data

A given entry dimension is based on its associated traffic variable. If the non-entry variable has data, its associated entry dimension also contains data. No implementation changes are required for entry dimensions if your traffic variables contain data.

## Dimension items

Since entry variables are typically based on custom strings in your implementation, your organization determines what the dimension items are. Values in a given entry dimension match dimension items in its associated non-entry dimension. For example, dimension items in the 'Entry page' dimension contain similar dimension items in the 'Page' dimension.

## Entry page original

The 'Entry page original' dimension operates differently than other entry dimensions. Instead of preserving the entry page for a given visit, it preserves the very first entry page for the entire life of that visitor's cookie. For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The 'Entry page original' dimension lists `https://example.com/page4` as the dimension item.
