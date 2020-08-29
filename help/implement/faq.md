---
title: Implementation FAQ
description: Frequently asked questions about implementation, and links to more information.
---

# FAQs about Analytics implementation

Frequently asked questions about implementation, and links to more information.

## What is the difference between the Experience Cloud visitor ID and Analytics visitor ID?

The Identity Service assigns a unique, persistent identifier that can be shared among other solutions in the Experience Cloud. The Analytics visitor ID is only used by Analytics. Adobe recommends using the Experience Cloud Visitor ID Service in your implementation.

## How do I implement heartbeat video tracking?

See [Measuring audio and video in Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

## Can a service interruption at Adobe affect performance?

No. The JavaScript file is not hosted on Adobe servers, so an Adobe outage does not affect your AppMeasurement library. If you use Adobe Experience Platform Launch, the JavaScript file is hosted by Akamai, or on a server location determined by your organization.

## Can the sending of data from the browser to Adobe services reduce performance?

AppMeasurement creates an image object within the HTML page, and the browser then requests the image object from Adobe data collection servers. If data collection servers were slow or unresponsive, the thread handling that request would be delayed until the image returns or a timeout occurs. Because browsers handle images with multiple threads, an Adobe outage would have a minimal impact on the page load time, tying up one thread while the others continue to function.

## How do I invalidate or remove an Analytics implementation?

Sometimes an organization would like to remove an implementation due to contract expiration or to reduce the number of server calls.

* **Implementations using Launch**: Disable or uninstall the Adobe Analytics extension in the [!UICONTROL Extensions] tab, then publish.
* **Legacy AppMeasurement implementations**: Replace the entire contents of your `s_code.js` file with the following line of code:

```js
var s = new Object();
```

>[!WARNING]
>
>Do not:
>
>* Change the report suite to an invalid value, as it creates unnecessary load on Adobe's servers.
>* Remove the `s_code.js` file altogether, unless you also remove all references to the file on each page.
>* Change the `trackingServer` variable to point away from Adobe. AppMeasurement still sends image requests, which return 404 errors.
