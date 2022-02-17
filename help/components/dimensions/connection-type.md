---
title: Connection type
description: How the visitor connects to the internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
---
# Connection type

The 'Connection type' dimension shows how the visitor connected to the internet. This dimension is useful to determine how visitors connect to the internet to browse your site. You can use it to optimize site content based on the connection speed of visitors.

## Populate this dimension with data

This dimension uses a combination of the [`ct` query string](/help/implement/validate/query-parameters.md) and Adobe server-side logic. Adobe uses the following rules in order to determine its value:

1. If the `ct` query string equals `"modem"`, set the dimension item to `"Modem"`. AppMeasurement only collects this data on unsupported Internet Explorer browsers, making this dimension item uncommon.
1. Check the IP address of the hit and reference it to a lookup table internal to Adobe. If the IP address is from a mobile carrier, set the dimension item to `"Mobile Carrier"`.
1. If the `ct` query string equals `"lan"`, set the dimension item to `"LAN/Wifi"`.
1. If the hit originates from a [Data source](/help/import/c-data-sources/datasrc-home.md) or is otherwise considered a special type of hit, set the dimension item to `"Not specified"`.
1. If none of the above rules are met, default to the value of `"LAN/Wifi"`.

## Dimension items

Dimension items include `LAN/Wifi`, `Mobile Carrier`, `Modem`, and `Not Specified`.

* **`LAN/Wifi`**: The visitor connected to the internet through a landline or wifi hotspot.
* **`Mobile Carrier`**: The visitor connected to the internet through a mobile carrier.
* **`Modem`**: The visitor connected to the internet through a modem on an unsupported Internet Explorer browser.
* **`Not Specified`**: The hit did not have a connection type.
