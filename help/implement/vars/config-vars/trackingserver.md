---
title: trackingServer
description: The domain used to send data to Adobe over HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
---
# trackingServer

>[!IMPORTANT]
>
>This variable is deprecated. With the prevalence of HTTPS, use [`trackingServerSecure`](trackingserversecure.md) instead.

The `trackingServer` variable determines the domain that AppMeasurement uses to send data to Adobe over HTTP. If this variable is not defined correctly, your implementation can experience data loss.

Before the [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/en/docs/id-service/using/home), this variable also determined where third-party cookies were set. Adobe strongly recommends using the ID service in all implementations where possible.

AppMeasurement uses `trackingServer` as a fallback if [`trackingServerSecure`](trackingserversecure.md) is not set. Many older implementations do not set `trackingServerSecure`, using `trackingServer` as a fallback on secure pages. With the prevalence of HTTPS, Adobe recommends using `trackingServerSecure` where possible.
