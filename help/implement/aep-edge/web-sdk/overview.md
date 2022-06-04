---
title: Implement Adobe Analytics using the Adobe Experience Platform Web SDK
description: Use the Web SDK extension in Adobe Experience Platform Data Collection to send data to Adobe Analytics.
---

# Implement Adobe Analytics using the Adobe Experience Platform Web SDK

You can use the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) to send data to Adobe Analytics. This works by translating the [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) into a format used by Analytics.

## Setup

To set up Analytics to receive XDM data:

1. Install and [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

1. Make sure the applicable report suites are mapped to the data you want. XDM data automatically flows to the report suite from Adobe Experience Edge.
