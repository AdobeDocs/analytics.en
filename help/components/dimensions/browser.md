---
title: Browser
description: The name and version of the browser used.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
# Browser

The '[!UICONTROL Browser]' [dimension](overview.md) reports the name and version of the browser sending the hit. This dimension is useful when you want to measure the most common browsers that visitors use. When testing new versions of your site, you can run those tests on the top browsers in this dimension to maximize quality control efforts.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and browser.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Device Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include the browser names and versions used. Different versions of the same browser are separate dimension items.

Some dimension items contain `"(unknown version)"` instead of their version number. This dimension item references a recent browser release that Adobe has not yet added to their lookup tables. Since browsers frequently update, the `"(unknown version)"` for a given browser is common and temporary. Adobe typically updates lookup tables during monthly maintenance releases.