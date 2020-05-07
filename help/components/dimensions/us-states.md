---
title: US states
description: The US state of the visitor.
---

# US state

The 'US state' dimension reports the state of the visitor in the United States of America. It is similar to the [Regions](regions.md) dimension, except that this dimension is specific to the United States. Using this dimension is valuable if you want insight more granular than [Countries](countries.md) but not as granular as [Cities](cities.md).

## Populate this dimension with data 

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with [Digital Element](https://www.digitalelement.com/) to maintain lookups between IP address and country. This dimension works out of the box for all implementations.

> [!TIP] If your organization follows stringent privacy regulations where [obfuscating IP address](/help/admin/admin/general-acct-settings-admin.md) isn't enough, you can request to disable geolocation data entirely. Contact Customer Care with the report suite ID, and request to turn off 'Geography' for the report suite.

## Dimension values

Dimension values include regions and the country that the region resides in. Example values include `"California"`, `"Texas"`, or `"Virginia"`. The dimension value `"Unspecified"` includes all international traffic outside of the United States.
