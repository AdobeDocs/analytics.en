---
title: Browser type
description: The organization that made the browser.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
---
# Browser type

The 'Browser type' [dimension](overview.md) lists organizations who made the browser that the visitor uses. This dimension is useful when you want to see which overarching browsers visitors use. It provides value over the 'Browsers' dimension in that it does not list different versions of the same browser as separate dimension items.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and browser.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Device Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include organizations that make browsers. Common dimension items include `"Google"` (the creators of [!DNL Chrome]), `"Apple"` (the creators of [!DNL Safari]), `"Microsoft"` (the creators of [!DNL Edge]), and `"Mozilla"` (the creators of [!DNL Firefox]).
