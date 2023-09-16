---
title: bufferRequests
description: Enhance the reliability of capturing link tracking requests for browsers that immediately unload the page.
feature: Variables
---
# bufferRequests

The `bufferRequests()` method allows you to cache image requests on the current page instead of sending them to Adobe. Triggering this method is useful in scenarios where a browser doesn't support [`navigator.sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon) or otherwise cancels image requests when a page unloads. Many versions of WebKit browsers, such as Safari, commonly exhibit the behavior of stopping an image request when clicking a link. The `bufferRequests()` method is available on all versions of AppMeasurement v2.25.0 or later.

When you call [`t()`](t-method.md) or [`tl()`](tl-method.md) on a subsequent page in the same browser session and `bufferRequests()` was not yet called on that page, all buffered requests are sent in addition to that page's image request. Buffered requests are sent in the correct order, where the current page's image request is sent last.

>[!TIP]
>
>The timestamp of buffered requests are shared with the page that data is sent; if you want more precision in the exact second a buffered request is recorded, you can set the [`timestamp`](../page-vars/timestamp.md) variable before buffering the request. If you use this variable, make sure that [Timestamps optional](/help/technotes/timestamps-optional.md) is enabled - if it is not, all timestamped hits are permanently lost!

## Limitations

When calling the `bufferRequests()` method, keep in mind the following limitations. Since this method uses [`sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), many of the same limitations apply:

* The destination link must reside on the same domain and subdomain. Buffered requests do not work across domains or subdomains, even if both have the same Adobe Analytics implementation. This limitation also means that you cannot use buffered requests to track exit links.
* The destination link must use the same protocol as the current page. You cannot send buffered requests between HTTP and HTTPS.
* Buffered requests are stored until you call `t()` or `tl()` without calling `bufferRequests()` first, or until the browser or tab is closed. If a browser session ends before you can send that data to Adobe, unsent buffered requests are permanently lost.
* If a browser does not support the [Session storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) or the [JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), a warning is output to the browser console and AppMeasurement attempts to immediately send the image request using the `t()` method.

## Buffered requests in the Web SDK

The Web SDK currently does not offer the ability to buffer requests.

## Buffered requests using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.bufferRequests() in AppMeasurement and the Analytics extension custom code editor

Call the `bufferRequests()` method before calling `t()` or `tl()`. When `bufferRequests()` is called, subsequent tracking calls are written to session storage instead of sent to Adobe data collection servers.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```

<!-- TODO: insert a link to this page in AppMeasurement release notes, and also add content to Analytics release notes -->