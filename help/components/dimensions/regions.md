---
title: Regions
description: The geographic region of the visitor.
---

# Regions

The 'Regions' dimension reports the geographic region of the visitor, typically a state, province, or large city within a country. It is similar to the [US states](us-states.md) dimension, except that it is not limited to the United States. Using this dimension is valuable if you want insight more granular than [Countries](countries.md) but not as granular as [Cities](cities.md).

## Populate this dimension with data 

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with [Digital Element](https://www.digitalelement.com/) to maintain lookups between IP address and country. This dimension works out of the box for all implementations.

> [!TIP] If your organization follows stringent privacy regulations where [obfuscating IP address](/help/admin/admin/general-acct-settings-admin.md) isn't enough, you can request to disable geolocation data entirely. Contact Customer Care with the report suite ID, and request to turn off 'Geography' for the report suite.

## Dimension values

Dimension values include regions and the country that the region resides in. Example values include `"California (United States)"`, `"Tokyo (Japan)"`, or `"Sao Paulo (Brazil)"`.
