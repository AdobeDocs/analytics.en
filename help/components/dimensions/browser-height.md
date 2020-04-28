---
title: Browser height - bucketed
description: The height of the browser window in pixels.
---

# Browser height

The 'Browser height - bucketed' dimension shows the height of the browser window, classified in groups of 100 pixels. This dimension is useful when you want to understand where the "fold" is on your site to visitors. Understanding where your fold is can allow you to optimize content for viewing.

This dimension is different than screen height. Browser height is the number of pixels within the viewable browser space, while screen height is the height of the entire monitor in pixels. If you would like to see the difference between these two variables on your own machine, open the browser console (F12 on most browsers) and copy + paste the following code into the console:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

Browser height is always smaller than screen height, since browser height doesn't include browser navigation or borders.

## Populate this dimension with data

This dimension retrieves data from the [`bh` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `window.innerHeight` in the browser. If you use an AppMeasurement library (such as through Adobe Experience Platform Launch), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `bh` query string parameter on the first hit of each visit.

Adobe persists browser height for a visit. If browser height is adjusted mid-visit, the adjustment is not recorded.

## Dimension values

Dimension values include all collected browser heights, classified into groups of 100 pixels. For example, if the browser height of a hit is `720`, then it is grouped in the dimension value `700 to 799`.
