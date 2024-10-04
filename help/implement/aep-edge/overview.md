---
title: Implement Adobe Analytics with Adobe Experience Platform Edge
description: Overview of using XDM data from Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
---
# Implement Adobe Analytics with the Adobe Experience Platform Edge Network

The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. The Edge Network forwards the appropriate information to the desired products. This concept allows you to consolidate implementation efforts, especially spanning multiple data solutions.

Adobe offers three main ways to send data to the Edge Network:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: Use the Web SDK extension in Adobe Experience Platform Data Collection to send data to Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: Use the Mobile SDK extension in Adobe Experience Platform Data Collection to send data to Edge.
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**: Send data directly to Edge using an API.



## How Adobe Analytics handles Edge Network data

Data sent to the Adobe Experience Platform Edge Network can follow two formats:

* XDM object: Conform to schemas based on [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html). XDM gives you flexibility in what fields are defined as part of events. At the time events reach Adobe Analytics, they are translated into a format that Adobe Analytics can handle.
* Data object: Send data to the Edge Network using specific fields mapped to Adobe Analytics. The Edge Network detects the presence of these fields and forwards them to Adobe Analytics without the need to conform to a schema.

The Edge Network uses the following logic to determine Adobe Analytics page views and link events:

| XDM payload contains... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL` and no `xdm.web.webInteraction.type` | considers payload a **page view** |
| `xdm.eventType = web.webPageDetails.pageViews` | considers payload a **page view** |
| `xdm.web.webInteraction.type` and (`xdm.web.webInteraction.name` or `xdm.web.webInteraction.url`) | considers payload a **link event** |
| `xdm.web.webInteraction.type` and (`xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.url`) | considers payload a **link event** <br/>Also sets `xdm.web.webPageDetails.name` and `xdm.web.webPageDetails.URL` to `null` |
| no `xdm.web.webInteraction.type` and (no `xdm.webPageDetails.name` and no `xdm.web.webPageDetails.URL`) | drops the payload and ignores the data |

{style="table-layout:auto"}

In addition to differentiating page views and link clicks, the following logic is in place that determines if certain events are categorized as A4T or are discarded.

| XDM payload contains... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` or <br/>`xdm.eventType = decisioning.propositionDisplay` or <br/>`xdm.eventType = personalization.request` or <br/>`xdm.eventType = decisioning.propositionFetch` and `xdm._experience.decisioning` | considers payload an **A4T** call. |
| `xdm.eventType = display` or <br/>`xdm.eventType = decisioning.propositionDisplay` or <br/>`xdm.eventType = personalization.request` or <br/>`xdm.eventType = decisioning.propositionFetch` and no `xdm._experience.decisioning` | drops the payload and ignores the data |
| `xdm.eventType = click` or `xdm.eventType = decisioning.propositionInteract` and `xdm._experience.decisioning` and no `web.webInteraction.type` | considers payload an **A4T** call. |
| `xdm.eventType = click` or `xdm.eventType = decisioning.propositionInteract` and no `xdm._experience.decisioning` and no `web.webInteraction.type` | drops the payload and ignores the data. |

{style="table-layout:auto"}

See the [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) for more information.
