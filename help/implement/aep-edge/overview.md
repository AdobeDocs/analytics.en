---
title: Using XDM data with Analytics
description: Overview of using XDM data from Experience Platform in Adobe Analytics
feature: AEP Edge
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
---
# Implement Adobe Analytics with Adobe Experience Platform Edge

Adobe Experience Platform Edge allows you to send data destined to multiple products to a centralized location. Experience Edge forwards the appropriate information to the desired products. This concept allows you to consolidate implementation efforts, especially spanning multiple data solutions.

Adobe offers three main ways to send data to Experience Edge:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: Use the Web SDK extension in the Data Collection UI to send data to Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: Use the Mobile SDK extension in the Data Collection UI to send data to Edge.
* **[Edge Network Server API](edge-api/overview.md)**: Send data directly to Edge using an API.

## Setup

To set up Analytics to receive XDM data:

1. Install and [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

1. Make sure the applicable report suites are mapped to the data you want. XDM data automatically flows to the report suite from Adobe Experience Edge.
