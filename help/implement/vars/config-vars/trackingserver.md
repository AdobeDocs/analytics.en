---
title: trackingServer
description: The domain used to send data to Adobe over HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# trackingServer

>[!IMPORTANT]
>
>This variable is deprecated. With the prevalence of HTTPS, use [`trackingServerSecure`](trackingserversecure.md) instead.

The `trackingServer` variable determines the domain that AppMeasurement uses to send data to Adobe over HTTP. If this variable is not defined correctly, your implementation can experience data loss.

Before the [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/en/docs/id-service/using/home), this variable also determined where third-party cookies were set. Adobe strongly recommends using the ID service in all implementations where possible.

AppMeasurement uses `trackingServer` as a fallback if [`trackingServerSecure`](trackingserversecure.md) is not set. Many older implementations do not set `trackingServerSecure`, using `trackingServer` as a fallback on secure pages. With the prevalence of HTTPS, Adobe recommends using `trackingServerSecure` where possible.
