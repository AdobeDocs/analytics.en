---
title: Browser width - bucketed
description: The width of the browser window in pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
---
# Browser width

The 'Browser width - bucketed' dimension shows the width of the browser window, classified in groups of 100 pixels. This dimension is useful when you want to understand how wide visitors see your content. Understanding how wide your content is typically viewed can allow you to optimize content for viewing.

This dimension is different than screen width. Browser width is the number of pixels within the viewable browser space, while screen width is the width of the entire monitor in pixels. If you would like to see the difference between these two variables on your own machine, open the browser console (F12 on most browsers) and copy + paste the following code into the console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

Browser width is always smaller than or equal to screen width, since browser width doesn't include scroll bars or borders.

## Populate this dimension with data

This dimension retrieves data from the [`bw` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `window.innerWidth` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `bw` query string parameter on the first hit of each visit.

Adobe persists browser width for a visit. If browser width is adjusted mid-visit, the adjustment is not recorded.

## Dimension items

Dimension items include all collected browser widths, classified into groups of 100 pixels. For example, if the browser width of a hit is `1280`, then it is grouped in the dimension item `1200 to 1299`.
