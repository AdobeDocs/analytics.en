---
title: Browser width - bucketed
description: The width of the browser window in pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
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
# Browser width

The 'Browser width - bucketed' [dimension](overview.md) shows the width of the browser window, classified into predefined groups. This dimension is useful when you want to understand how wide visitors see your content. Understanding the width that your content is typically viewed in can allow you to optimize that content.

This dimension is different from screen width. Browser width is the number of pixels within the viewable browser space, while screen width is the width of the entire monitor in pixels. If you would like to see the difference between these two variables on your own machine, open the browser console (F12 on most browsers) and copy + paste the following code into the console:

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

Browser width is always smaller than or equal to screen width, since browser width doesn't include scroll bars or borders.

## Populate this dimension with data

This dimension retrieves data from the [`bw` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `window.innerWidth` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `bw` query string parameter on the first hit of each visit.

Adobe persists browser width for a visit. If browser width is adjusted mid-visit, the adjustment is not recorded.

## Dimension items

Dimension items include all collected browser widths, classified into predefined groups. For example, if the browser width of a hit is `1280`, then it is grouped in the dimension item `1200 to 1299`.
