---
title: Countries
description: The country where the hit originated from.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
---
# Countries

The 'Countries' dimension reports the country where the hit originated from. This dimension is useful to help determine what the most popular countries visitors originate from when visiting your site. You could use this data to focus on marketing efforts in these countries, or make sure your site experience is optimal in countries that have different primary languages.

## Populate this dimension with data

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with [Digital Element](https://www.digitalelement.com/) to maintain lookups between IP address and country. This dimension works out of the box for all implementations.

## Dimension items

Dimension items include countries all over the world. Example values include `"United States"`, `"United Kingdom"`, or `"India"`.

## Differences between reported and actual location

Since this dimension is based on IP address, some scenarios can show a difference between reported location and actual location:

* **IP addresses that represent corporate proxies**: These visitors can appear as traffic coming through the user's corporate network, which can be a different location if the user is working remotely.
* **Mobile IP addresses**: Mobile IP targeting works at varying levels depending on the location and the network. A number of carriers backhaul IP traffic through centralized or regional points of presence.
* **Satellite ISP users**: Identifying the specific location of these users is difficult, as they typically appear to originate from the uplink location.
* **Military and government IPs**: Represents personnel traveling around the globe and entering through their home location, rather than the base or office where they are currently stationed.
