---
description: Placing the call to the JavaScript library file at the top of the page ensures that the image is among the first elements to be downloaded.
keywords: Analytics Implementation
seo-description: Placing the call to the JavaScript library file at the top of the page ensures that the image is among the first elements to be downloaded.
seo-title: JavaScript file location and concurrence
solution: Analytics
subtopic: Troubleshooting
title: JavaScript file location and concurrence
topic: Developer and implementation
uuid: f6bd850f-8fc8-427d-a8f6-8f0133988967
index: y
internal: n
snippet: y
---

# JavaScript file location and concurrence

Placing the call to the JavaScript library file at the top of the page ensures that the image is among the first elements to be downloaded.

 Most Web browsers download images concurrently. Typically three to four images can be downloaded simultaneously.

Because most Web browsers download elements concurrently, the Status Bar of many common browsers (including Internet Explorer) does not accurately reflect which element the browser is trying to load. For example, your Status Bar may report that your browser is waiting for image 1 to download. The network packet tests show your browser has already received image 1 and is currently waiting for image 2.

>[!NOTE]
>
>Because third-party Internet Performance Audit providers (such as Keynote Systems) download page image elements sequentially, not concurrently, they do not mimic the typical user experience.

