---
title: US states
description: The US state of the visitor.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
---
# US state

The 'US state' dimension reports the state of the visitor in the United States of America. It is similar to the [Regions](regions.md) dimension, except that this dimension is specific to the United States. Using this dimension is valuable if you want insight more granular than [Countries](countries.md) but not as granular as [Cities](cities.md).

## Populate this dimension with data 

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with [Digital Element](https://www.digitalelement.com/) to maintain lookups between IP address and country. This dimension works out of the box for all implementations.

## Dimension items

Dimension items include regions and the country that the region resides in. Example values include `"California"`, `"Texas"`, or `"Virginia"`. The dimension item `"Unspecified"` includes all international traffic outside of the United States.

This dimension can include `"AOL"`, a dial-up internet service provider. Subscribers to this service are assigned an access point. AOL users use the IP address of this access point. Since this dimension is based on IP address, the geolocation of the access point is used instead of the visitor's actual location.

## Differences between reported and actual location

Since this dimension is based on IP address, some scenarios can show a difference between reported location and actual location:

* **IP addresses that represent corporate proxies**: These visitors can appear as traffic coming through the user's corporate network, which can be a different location if the user is working remotely.
* **Mobile IP addresses**: Mobile IP targeting works at varying levels depending on the location and the network. A number of carriers backhaul IP traffic through centralized or regional points of presence.
* **Satellite ISP users**: Identifying the specific location of these users is difficult, as they typically appear to originate from the uplink location.
* **Military and government IPs**: Represents personnel traveling around the globe and entering through their home location, rather than the base or office where they are currently stationed.
* **Proxies that obscure IP addresses for privacy reasons**: Services like Apple's Private Relay hide the true IP address by randomly sending data through an intermediary or proxy. This proxy then substitutes a different IP address before forwarding to Adobe.
