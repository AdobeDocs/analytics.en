---
description: When a mobile device requests a page from a Web server, the request is sent through a gateway, which converts the mobile request (usually in the WAP or I-Mode protocol) into an HTTP request that is sent to a Web server.
keywords: Analytics Implementation;gateway;wap;i-mode;wbmp
seo-description: When a mobile device requests a page from a Web server, the request is sent through a gateway, which converts the mobile request (usually in the WAP or I-Mode protocol) into an HTTP request that is sent to a Web server.
seo-title: Mobile protocol network gateway
solution: Analytics
title: Mobile protocol network gateway
topic: Developer and implementation
uuid: df6a96b0-8d19-4dc4-a78d-6d284552e754
index: y
internal: n
snippet: y
---

# Mobile protocol network gateway

When a mobile device requests a page from a Web server, the request is sent through a gateway, which converts the mobile request (usually in the WAP or I-Mode protocol) into an HTTP request that is sent to a Web server.

 When a mobile device requests a page from a Web server, the request is sent through a gateway, which converts the mobile request (usually in the WAP or I-Mode protocol) into an HTTP request that is sent to a Web server. The Web server responds to the gateway, which forwards the request to the phone. This gateway acts much like a standard proxy server. The gateway does, however, pass the user agent string of the mobile device on to the Web server. This lets the Web server respond with a page that is built specifically for the device requesting it.

Because screen size on WAP mobile devices is so limited, mobile pages are very light, often containing only text and one cached image. When the image tag is added to the pages, a request is sent on every page for an image from Adobe servers. When the image, a WBMP, is returned, Adobe servers instruct the browser not to cache it. Consequently, the image is requested again on subsequent pages. The random number described above should be used to protect against browsers that do not obey the Adobe no-cache directives. 
