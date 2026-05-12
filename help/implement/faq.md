---
title: Implementation FAQ
description: Frequently asked questions about implementation, and links to more information.
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/Hm9pIJE9P3jEljJAgB69k2M9-fTa9G0wsCjfvN4xH3E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# FAQs about Analytics implementation

Frequently asked questions about implementation, and links to more information.

## What is the difference between the CX Enterprise visitor ID and Analytics visitor ID?

The Identity Service assigns a unique, persistent identifier that can be shared among other solutions in the CX Enterprise. The Analytics visitor ID is only used by Analytics. Adobe recommends using the CX Enterprise Visitor ID Service in your implementation.

## How do I implement heartbeat video tracking?

See [Measuring audio and video in Adobe Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-overview).

## Can a service interruption at Adobe affect performance?

No. The JavaScript file is not hosted on Adobe servers, so an Adobe outage does not affect your AppMeasurement library. If you use tags in Adobe Experience Platform, the JavaScript file is hosted by Akamai, or on a server location determined by your organization.

## Can the sending of data from the browser to Adobe services reduce performance?

AppMeasurement creates an image object within the HTML page, and the browser then requests the image object from Adobe data collection servers. If data collection servers were slow or unresponsive, the thread handling that request would be delayed until the image returns or a timeout occurs. Because browsers handle images with multiple threads, an Adobe outage would have a minimal impact on the page load time, tying up one thread while the others continue to function.

## How do I invalidate or remove an Analytics implementation?

Sometimes an organization would like to remove an implementation due to contract expiration or to reduce the number of server calls.

* **Implementations using Adobe Experience Platform Data Collection**: Disable or uninstall the applicable Adobe Analytics, Web SDK, or Mobile SDK extension in the [!UICONTROL Extensions] tab, then publish.
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
