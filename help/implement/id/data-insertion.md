---
title: Visitor identification using the Data Insertion API
description: Identify visitors for server-side and direct Adobe Analytics data collection with the Data Insertion API.
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Visitor identification using the Data Insertion API

The [Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) sends hits to Adobe Analytics collection servers without a client-side library such as AppMeasurement or the Web SDK. Because no library is present to manage identity for you, you set the visitor identifier yourself — in the browser for direct image requests, or on your server for server-side collection.

>[!NOTE]
>
>This page covers visitor identity. For building and sending the requests themselves, see the [Data Insertion API documentation](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) on Adobe Developer.

Adobe identifies a visitor using the standard [order of operations](overview.md): the `vid`, then the `aid`, `mid`, `fid`, and finally the IP address and user agent. With the Data Insertion API you typically set one of three identifiers directly: the ECID (`mid`), the Analytics visitor ID (`aid`), or a custom visitor ID (`vid`).

## Using the ECID (recommended)

The ECID (sent as the `mid`) is the modern, cross-solution visitor identifier, shared across Adobe Analytics, Adobe Target, and Adobe Audience Manager. Adobe recommends using it wherever possible.

Obtain the ECID with the [Visitor ID Service](https://experienceleague.adobe.com/en/docs/id-service/using/home) (`VisitorAPI.js`). In a browser, initialize the service with your IMS organization ID using [`getInstance`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getinstance), then read the ECID with [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid):

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

Send that value on each hit as the `mid` query parameter, along with your IMS organization ID as the `mcorgid` parameter so the ECID resolves correctly. If your data forwards to Audience Manager, also send the region from [`getLocationHint`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getlocationhint) as the `aamlh` parameter. To associate your own customer identifiers with the visitor, use [`setCustomerIDs`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/setcustomerids).

For server-side collection, obtain the ECID on the client and forward it to your server to send on each hit. To generate an ECID entirely server-side, without a client, use the ID Service's [direct integration](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration).

## Using the Analytics visitor ID

The Analytics visitor ID (`aid`) is stored in the [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie. When a hit arrives without an identifier, the collection server assigns an `aid` and attempts to set a cookie containing that identifier. Some [response types](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) also include this identifier in the response body.

* **Client-side (direct image requests).** The browser stores the `s_vi` cookie that the server returns and sends it on every later request to the same collection domain. The visitor is then recognized automatically, with no `aid` to set yourself. Because this model depends on cookies, it carries the same durability limits as any cookie-based identity. See [Visitor identification using AppMeasurement](appmeasurement.md) for first-party versus third-party cookie behavior, and the [order of operations](overview.md) for how Adobe chooses which identifier to use. Adobe recommends using an ECID for durable identity.

  >[!NOTE]
  >
  >If you read the visitor ID directly from the `s_vi` cookie, the cookie wraps the ID in additional data (for example, `[CS]v1|<id>[CE]`) — extract only the `<id>` portion. Reading the ID from a visitor response returns it directly, with no parsing.

* **Server-side.** A server has no cookie jar, so you store and resend the `aid` yourself, keyed to the user:

  1. Look up the stored `aid` for the user.
  1. If you have one, send it as the `aid` query parameter.
  1. If you do not, send the hit with no identifier, requesting a response type that returns the assigned `aid`, then store it for next time.

  The first, identifier-less hit is already attributed to the `aid` the server returns, so you lose no data by sending it before you have an ID. For the response types that return the ID (`3` for JavaScript, `11` for XML, `10` for JSON) and the request format, see [Response type](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) in the Data Insertion API documentation.

  A server-side request carries no visitor cookies, and its own IP address and user agent belong to the sender. To attribute hits correctly, also forward the visitor's real IP address (the `X-Forwarded-For` header) and user agent (the `User-Agent` header).

## Using a custom visitor ID

If you already have a durable identifier that you fully control, you can send it as the [`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`) on every hit and own identity end to end. This suits non-browser platforms that provide a stable device identifier. For example, a Unity application can send its device identifier as the `vid`.

>[!IMPORTANT]
>
>Use `vid` only when you can guarantee a stable value on every hit:
>
>* **Browsers are a poor fit.** A browser has no durable identifier you can populate reliably, so a browser-set `vid` tends to fragment or collide. Use the cookie-based client-side model instead.
>* **Be careful with authentication identifiers.** You have no identifier before a user logs in, and if the user logs out, later hits are attributed to a different visitor. These actions split one person's activity across multiple visitors.

See [`visitorID`](/help/implement/vars/config-vars/visitorid.md) for the format and constraints of a custom visitor ID.
