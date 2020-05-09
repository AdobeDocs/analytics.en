---
title: US DMA
description: The designated market area of the hit.
---

# US DMA

The 'US DMA' dimension reports the designated market area (DMA) of the visitor. It is based on media markets compiled by [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Populate this dimension with data 

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with Nielsen to maintain lookups between IP address and DMA. This dimension works out of the box for all implementations.

> [!TIP] If your organization follows stringent privacy regulations where [obfuscating IP address](/help/admin/admin/general-acct-settings-admin.md) isn't enough, you can request to disable geolocation data entirely. Contact Customer Care with the report suite ID, and request to turn off 'Geography' for the report suite.

## Dimension values

Dimension values include the DMA and DMA code of the visitor. The 3-digit code is not a zip code, but rather the DMA code from Nielsen. Example values include `"Dallas-Ft. Worth (623)"`, `"New York (501)"`, or `"Los Angeles (803)"`. The dimension value `"No Metro (0)"` includes all international traffic outside of the United States.
