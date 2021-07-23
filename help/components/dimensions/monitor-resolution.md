---
title: Monitor resolution
description: The resolution of the visitor's monitor in pixels.
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
---
# Monitor resolution

The 'Monitor resolution' dimension shows the height and width of the active display in pixels. This dimension is useful when you want to understand where the "fold" is on your site to visitors, or how wide visitors can make their browser window. Understanding where your fold is can allow you to optimize content for viewing.

This dimension is different than browser height and width. Browser height/width is the number of pixels within the viewable browser space, while monitor resolution is the number of pixels of the entire monitor. If you would like to see the difference between these two variables on your own machine, open the browser console (F12 on most browsers) and copy + paste the following code into the console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Browser dimensions are always smaller than monitor resolution, since browser dimensions don't include browser navigation or borders.

## Populate this dimension with data

This dimension retrieves data from the [`s` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `screen.width` and `screen.height` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `s` query string parameter in image requests.

## Dimension items

Dimension items include all collected monitor resolutions. Example values include `1920 x 1080`, `1366 x 768`, and `1280 x 720`.
