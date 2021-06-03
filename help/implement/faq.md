---
title: Implementation FAQ
description: Frequently asked questions about implementation, and links to more information.
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
---
# FAQs about Analytics implementation

Frequently asked questions about implementation, and links to more information.

## What is the difference between the Experience Cloud visitor ID and Analytics visitor ID?

The Identity Service assigns a unique, persistent identifier that can be shared among other solutions in the Experience Cloud. The Analytics visitor ID is only used by Analytics. Adobe recommends using the Experience Cloud Visitor ID Service in your implementation.

## How do I implement heartbeat video tracking?

See [Measuring audio and video in Adobe Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html).

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

## I ran AppMeasurement through a code analyzer, and it flagged its usage of `Math.random()` as a potential security risk. Is `Math.random()` used with any sensitive data?

No. The numbers that use `Math.random()` are not used to mask, send, or receive any sensitive data. Data sent to Adobe data collection servers rely on the security of the underlying HTTPS connection. <!-- AN-173590 -->

AppMeasurement uses `Math.random()` in three key areas:

* **Sampling**: Depending on your implementation, some information could be gathered for only a small percentage of visitors to your site. `Math.random()` is used to determine if a given visitor should send data. Most implementations do not use sampling.
* **Fallback visitor ID**: If the visitor ID cannot be retrieved from cookies, a random visitor ID is generated. This part of AppMeasurement uses two calls to `Math.random()`.
* **Cache busting**: A random number is added to the end of image request URLs to help prevent browser caching.
