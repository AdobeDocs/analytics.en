---
title: Persistent cookie support
description: Determines if the visitor has the ability to support persistent cookies.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
---
# Persistent cookie support

The 'Persistent cookie support' dimension shows if the hit used a visitor identifier that originated from a persistent source. The most common persistent source is from a cookie, but can also use mobile headers and other sources.

## Populate this dimension with data

Adobe determines the value of this dimension server-side based on the source of the hit's identifier. There is not a way to directly set it. It works out of the box for all implementations.

## Dimension items

* **`Enabled`**: The hit's visitor identifier come from a source that typically persists. The most common examples include `aid`, `fid`, or `mid` query string parameters, as they derive their values from a cookie.
* **`Disabled`**: The hit's visitor identifier came from a source that Adobe does not recognize as persistent, such as IP + user agent string. This dimension item also includes custom visitor ID's using the [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable.

## Difference between 'Cookie support' and 'Persistent cookie support'

* **Cookie support**: AppMeasurement tries to set a generic cookie. The dimension item is based on if the cookie was successfully set.
* **Persistent cookie support**: The dimension item is based on if the hit's identifier originated from a persistent source, such as a cookie.
