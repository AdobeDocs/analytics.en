---
title: FAQs about Analytics implementation
description: Frequently asked questions about implementation, and links to more information.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
---

# FAQs about Analytics implementation

Frequently asked questions about implementation, and links to more information.

**What is the difference between variable allocation and expiration?**

Allocation and expiration are both settings you can apply to custom variables. *Allocation* comes into play when you have an persisted variable value and a new variable value. It determines if the old value or new value is kept. *Expiration* comes into play when you don't want a variable value to continue persisting.

**What is the difference between the Experience Cloud visitor ID and Analytics visitor ID?**

The Identity Service assigns a unique, persistent identifier that can be shared among other solutions in the Experience Cloud. The Analytics visitor ID is only used by Analytics. Adobe recommends using the Experience Cloud Visitor ID Service in your implementation.

**How is a visitor ID set if cookies are blocked?**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**How do I implement heartbeat video tracking?**

See [Measuring audio and video in Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

**Can a service interruption at Adobe affect performance?**

No. The JavaScript file is not hosted on Adobe servers, so an Adobe outage does not affect your AppMeasurement library. If you use Adobe Experience Platform Launch, the JavaScript file is hosted by Akamai, or on a server location determined by your organization.

**Can the sending of data from the browser to Adobe services reduce performance?**

AppMeasurement creates an image object within the HTML page, and the browser then requests the image object from Adobe data collection servers. If data collection servers were slow or unresponsive, the thread handling that request would be delayed until the image returns or a timeout occurs. Because browsers handle images with multiple threads, an Adobe outage would have a minimal impact on the page load time, tying up one thread while the others continue to function.

**How do I track a mobile app?**

You can use the Adobe Experience Platform SDK. See [Adobe Experience Platform SDK overview](https://aep-sdks.gitbook.io/docs/) for more information.

**What are plug-ins?**

Plug-ins are snippets of code that perform advanced functions. They extend the capabilities of AppMeasurement to give your more functionality in your implementation.
