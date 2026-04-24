---
title: Browser type
description: The organization that made the browser.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
TQID: https://experienceleague.adobe.com/Qb4g-5RXrK42ui4xG86YEv3ozVqmqHrn9Bj5zqXmzPU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
# Browser type

The 'Browser type' [dimension](overview.md) lists the organizations who made the browser that the visitor uses. This dimension is useful when you want to see which overarching browsers visitors use. It provides value over the 'Browsers' dimension in that it does not list different versions of the same browser as separate dimension items.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and browser.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Device Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include organizations that make browsers. Common dimension items include `"Google"` (the creators of [!DNL Chrome]), `"Apple"` (the creators of [!DNL Safari]), `"Microsoft"` (the creators of [!DNL Edge]), and `"Mozilla"` (the creators of [!DNL Firefox]).
