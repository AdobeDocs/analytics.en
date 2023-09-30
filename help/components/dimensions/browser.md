---
title: Browser
description: The name and version of the browser used.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
---
# Browser

The '[!UICONTROL Browser]' [dimension](overview.md) reports the name and version of the browser sending the hit. This dimension is useful when you want to measure the most common browsers that visitors use. When testing new versions of your site, you can run those tests on the top browsers in this dimension to maximize quality control efforts.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and browser.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Device Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include the browser names and versions used. Different versions of the same browser are separate dimension items.

Some dimension items contain `"(unknown version)"` instead of their version number. This dimension item references a recent browser release that Adobe has not yet added to their lookup tables. Since browsers frequently update, the `"(unknown version)"` for a given browser is common and temporary. Adobe typically updates lookup tables during monthly maintenance releases.