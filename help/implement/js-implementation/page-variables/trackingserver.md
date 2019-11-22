---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# trackingServer

The  variable is used for first-party cookie implementation to specify the domain at which the image request and cookie is written.


<!-- 

trackingServer.xml

 -->

Used for non-secure pages. If *`trackingServer`* is defined, nothing goes to 2o7.net. If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | ""  |

A list of Adobe data centers can be found [here](https://helpx.adobe.com/analytics/kb/determining-data-center.html).