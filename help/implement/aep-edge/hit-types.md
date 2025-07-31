---
title: Edge Network event types in Adobe Analytics
description: How Adobe Analytics interprets events received from the Edge Network.
feature: Implementation Basics
role: Admin, Developer
---
# Edge Network event types in Adobe Analytics

Adobe Analytics treats hits differently depending on what functions you call in AppMeasurement. For example, [`s.t`](/help/implement/vars/functions/t-method.md) and [`s.tl`](/help/implement/vars/functions/tl-method.md) include or omit certain dimensions and increment page views differently. Adobe Experience Platform only contains the `sendEvent` command. Specific properties within the `xdm` payload determine how that data is interpreted in Adobe Analytics.

The Edge Network uses the following logic to determine Adobe Analytics page views and link events:

| XDM payload contains... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL` and no `xdm.web.webInteraction.type` | considers payload a **page view** |
| `xdm.eventType = web.webPageDetails.pageViews` | considers payload a **page view** |
| `xdm.web.webInteraction.type` and (`xdm.web.webInteraction.name` or `xdm.web.webInteraction.url`) | considers payload a **link event** |
| `xdm.web.webInteraction.type` and (`xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.url`) | considers payload a **link event** <br/>Also sets `xdm.web.webPageDetails.name` and `xdm.web.webPageDetails.URL` to `null` |
| no `xdm.web.webInteraction.type` and (no `xdm.webPageDetails.name` and no `xdm.web.webPageDetails.URL`) | drops the payload and ignores the data |

In addition to differentiating page views and link clicks, the following logic is in place that determines if certain events are categorized as A4T or are discarded.

| XDM payload contains... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` or <br/>`xdm.eventType = decisioning.propositionDisplay` or <br/>`xdm.eventType = personalization.request` or <br/>`xdm.eventType = decisioning.propositionFetch` and `xdm._experience.decisioning` | considers payload an **A4T** call. |
| `xdm.eventType = display` or <br/>`xdm.eventType = decisioning.propositionDisplay` or <br/>`xdm.eventType = personalization.request` or <br/>`xdm.eventType = decisioning.propositionFetch` and no `xdm._experience.decisioning` | drops the payload and ignores the data |
| `xdm.eventType = click` or `xdm.eventType = decisioning.propositionInteract` and `xdm._experience.decisioning` and no `web.webInteraction.type` | considers payload an **A4T** call. |
| `xdm.eventType = click` or `xdm.eventType = decisioning.propositionInteract` and no `xdm._experience.decisioning` and no `web.webInteraction.type` | drops the payload and ignores the data. |

See the [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) for more information.
