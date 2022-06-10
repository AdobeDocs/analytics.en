---
title: US DMA
description: The designated market area of the hit.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
---
# US DMA

The 'US DMA' dimension reports the designated market area (DMA) of the visitor. It is based on media markets compiled by [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Populate this dimension with data 

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with Nielsen to maintain lookups between IP address and DMA. This dimension works out of the box for all implementations.

## Dimension items

Dimension items include the DMA and DMA code of the visitor. The 3-digit code is not a zip code, but rather the DMA code from Nielsen. Example values include `"Dallas-Ft. Worth (623)"`, `"New York (501)"`, or `"Los Angeles (803)"`. The dimension item `"No Metro (0)"` includes all international traffic outside of the United States.

## Differences between reported and actual location

Since this dimension is based on IP address, some scenarios can show a difference between reported location and actual location:

* **IP addresses that represent corporate proxies**: These visitors can appear as traffic coming through the user's corporate network, which can be a different location if the user is working remotely.
* **Mobile IP addresses**: Mobile IP targeting works at varying levels depending on the location and the network. A number of carriers backhaul IP traffic through centralized or regional points of presence.
* **Satellite ISP users**: Identifying the specific location of these users is difficult, as they typically appear to originate from the uplink location.
* **Military and government IPs**: Represents personnel traveling around the globe and entering through their home location, rather than the base or office where they are currently stationed.
