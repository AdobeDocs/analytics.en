---
title: Browser
description: The name and version of the browser used.
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
---
# Browser

The 'Browser' dimension reports the name and version of the browser sending the hit. This dimension is useful to understand what the most common browsers that visitors use. When testing new versions of your site, you can run those tests on the top browsers in this dimension to maximize quality control efforts.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include the browser names and versions used. Different versions of the same browser are separate dimension items.

Some dimension items contain `"(unknown version)"` instead of their version number. This dimension item references a recent browser release that Adobe has not added to their lookup tables. Since browsers frequently update, the `"(unknown version)"` for a given browser is common and temporary. Adobe typically updates lookup tables during monthly maintenance releases.
