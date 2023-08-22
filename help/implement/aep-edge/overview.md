---
title: Implement Adobe Analytics with Adobe Experience Platform Edge
description: Overview of using XDM data from Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
---
# Implement Adobe Analytics with Adobe Experience Platform Edge

Adobe Experience Platform Edge allows you to send data destined to multiple products to a centralized location. Experience Edge forwards the appropriate information to the desired products. This concept allows you to consolidate implementation efforts, especially spanning multiple data solutions.

Adobe offers three main ways to send data to Experience Edge:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: Use the Web SDK extension in Adobe Experience Platform Data Collection to send data to Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: Use the Mobile SDK extension in Adobe Experience Platform Data Collection to send data to Edge.
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**: Send data directly to Edge using an API.



## How Adobe Analytics handles Experience Edge data

Data send to Experience Edge has to conform to schemas based on [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en). XDM gives you flexibility in what fields are defined as part of events. At the time events reach Adobe Analytics, these events are translated into more structured data that Adobe Analytics can handle: page views or link events.

 XDM does not itself prescribe how to define page views or link events, nor does it instruct Adobe Analytics how to treat its payload. For example, certain out of the box XDM fields that appear to be related to page views or link events, like `eventType`, `web.webPageDetails.pageViews`, or `web.webInteraction.linkEvents` are completely implementation agnostic and have no relevance for Adobe Analytics.

To properly handle page views and link events, the following logic is applied to data send to the Adobe Experience Edge network and forwarded to Adobe Analytics.

| XDM payload contains... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` or `web.webPageDetails.URL` | considers payload a **page view** |
| `web.webInteraction.type` and (`web.webInteraction.name` or `web.webInteraction.url`) | considers payload a **link event** |
| `web.webInteraction.type` and (`web.webPageDetails.name` or `web.webPageDetails.url`) | considers payload a **link event** <br/>`web.webPageDetails.name` and `web.webPageDetails.URL` are set to `null` |
| no `webPageDetails.name` and no `web.webPageDetails.URL` and no `web.webInteraction.type` | drops the payload and ignores the data |

{style="table-layout:auto"}

