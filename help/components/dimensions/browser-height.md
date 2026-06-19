---
title: Browser height - bucketed
description: The height of the browser window in pixels.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
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
# Browser height

The 'Browser height - bucketed' [dimension](overview.md) shows the height of the browser window, classified into predefined groups. This dimension is useful when you want to understand where the "fold" is on your site to visitors. Understanding where your fold is can allow you to optimize content for viewing.

This dimension is different from screen height. Browser height is the number of pixels within the viewable browser space, while screen height is the height of the entire monitor in pixels. If you would like to see the difference between these two variables on your own machine, open the browser console (F12 on most browsers) and copy + paste the following code into the console:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

Browser height is always smaller than or equal to screen height, since browser height doesn't include browser navigation or borders.

>[!NOTE]
>
>Data Warehouse also provides a '[!UICONTROL Browser height - granular]' dimension, which reports the exact pixel height instead of grouping values into predefined buckets.

## Populate this dimension with data

This dimension retrieves data from the [`bh` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `window.innerHeight` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `bh` query string parameter on the first hit of each visit.

Adobe persists browser height for a visit. If browser height is adjusted mid-visit, the adjustment is not recorded.

## Dimension items

Dimension items include all collected browser heights, classified into predefined groups. For example, if the browser height of a hit is `720`, then it is grouped in the dimension item `700 to 799`.
