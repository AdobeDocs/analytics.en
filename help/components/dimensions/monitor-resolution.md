---
title: Monitor resolution
description: The resolution of the visitor's monitor in pixels.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Monitor resolution

The 'Monitor resolution' [dimension](overview.md) shows the height and width of the active display in pixels. This dimension is useful when you want to understand where the "fold" is on your site to visitors, or how wide visitors can make their browser window. Understanding where your fold is can allow you to optimize content for viewing.

This dimension is different than browser [height](browser-height.md) and [width](browser-width.md). Browser height/width is the number of pixels within the viewable browser space, while monitor resolution is the number of pixels of the entire monitor. If you would like to see the difference between these two variables on your own machine, open the browser console (F12 on most browsers) and copy + paste the following code into the console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Browser dimensions are always smaller than monitor resolution, since browser dimensions don't include browser navigation or borders.

## Populate this dimension with data

This dimension retrieves data from the [`s` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `screen.width` and `screen.height` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `s` query string parameter in image requests. If the `s` query string is missing or a data collection library otherwise cannot collect monitor resolution, that data is listed under [!UICONTROL `Not Specified`].

## Dimension items

Dimension items include all collected monitor resolutions. Example values include `1920 x 1080`, `1366 x 768`, and `1280 x 720`.
