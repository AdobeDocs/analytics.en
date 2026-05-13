---
title: Persistent cookie support
description: Determines if the visitor has the ability to support persistent cookies.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Persistent cookie support

The 'Persistent cookie support' [dimension](overview.md) shows if the hit used a visitor identifier that originated from a persistent source. The most common persistent source is from a cookie, but can also use mobile headers and other sources.

## Populate this dimension with data

Adobe determines the value of this dimension server-side based on the source of the hit's identifier. There is not a way to directly set it. It works out of the box for all implementations.

## Dimension items

* **`Enabled`**: The hit's visitor identifier come from a source that typically persists. The most common examples include `aid`, `fid`, or `mid` query string parameters, as they derive their values from a cookie.
* **`Disabled`**: The hit's visitor identifier came from a source that Adobe does not recognize as persistent, such as IP + user agent string. This dimension item also includes custom visitor ID's using the [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable.

## Difference between 'Cookie support' and 'Persistent cookie support'

* **Cookie support**: AppMeasurement tries to set a generic cookie. The dimension item is based on if the cookie was successfully set.
* **Persistent cookie support**: The dimension item is based on if the hit's identifier originated from a persistent source, such as a cookie.
