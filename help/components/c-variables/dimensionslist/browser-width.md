---
description: Metrics that refer to the horizontal/vertical distance of the data in the browser window only. More specifically, the browser
solution: Analytics
title: Browser Width/Height
topic: Metrics
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
---

# Browser Width/Height

Metrics that refer to the horizontal/vertical distance of the data in the browser window only. More specifically, the browser

Adobe Analytics uses the browser height and width only from the first hit of a visit. The rest of the hits do not get the attribution for the same visit.
The browser width/height dimensions capture similar but distinct values when compared with [mobile screen size](/help/components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

For example, when you break down browser width or height by mobile resolution, you need to be aware of these distinctions:

* The Mobile Device Resolutions are the physical values associated with the device. For example, under Mobile Device Resolutions the Galaxy S8 would appear as 2,960 x 1,440. The Mobile Device Resolution is retrieved from a 3rd-party service after the device is identified.
* By contrast, under the Browser Height and Width values, you see the CSS (logical) values of 740 x 360. The Browser values rely on the Javascript/CSS data.
* For a brief discussion, see [this thread](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

