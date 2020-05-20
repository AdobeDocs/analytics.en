---
title: Cities
description: The city where the hit originated from.
---

# Cities

The 'Cities' dimension reports the city where the hit originated from. This dimension is useful to help determine what the most popular cities visitors originate from when visiting your site. You could use this data to focus on local advertising in these cities, such as billboards or commercials.

## Populate this dimension with data

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with [Digital Element](https://www.digitalelement.com/) to maintain lookups between IP address and city. This dimension works out of the box for all implementations.

> [!TIP] If your organization follows stringent privacy regulations where [obfuscating IP address](/help/admin/admin/general-acct-settings-admin.md) isn't enough, you can request to disable geolocation data entirely. Contact Customer Care with the report suite ID, and request to turn off 'Geography' for the report suite.

## Dimension values

Dimension values include cities all over the world. Example values include `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"`, or `"London (London, United Kingdom)"`.

## Differences between reported and actual location

Since this dimension is based on IP address, some scenarios can show a difference between reported location and actual location:

* **IP addresses that represent corporate proxies**: These can appear as traffic coming through the user's corporate network, which can be a different location if the user is working remotely.
* **Mobile IP addresses**: Mobile IP targeting works at varying levels depending on the location and the network. A number of carriers backhaul IP traffic through centralized or regional points of presence.
* **Satellite ISP users**: Identifying the specific location of these users is difficult, as they typically appear to originate from the uplink location.
* **Military and government IPs**: Represents personnel traveling around the globe and entering through their home location, rather than the base or office where they are currently stationed.
