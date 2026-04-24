---
title: Edge Network event types in Adobe Analytics
description: How Adobe Analytics interprets events received from the Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
TQID: https://experienceleague.adobe.com/Bf-OnlQu7TFYb1V4uKCVVoQkaPP4MuhyVWSdgjlZ6e8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
---
# Edge Network event types in Adobe Analytics

Adobe Analytics treats hits differently depending on what functions you call in AppMeasurement. For example, [`s.t`](/help/implement/vars/functions/t-method.md) and [`s.tl`](/help/implement/vars/functions/tl-method.md) include or omit certain dimensions and increment [page views](/help/components/metrics/page-views.md) differently. Adobe Experience Platform only contains the [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/overview) command. Specific properties within the [`xdm`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/xdm) or [`data`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/data) payload determine how that data is interpreted in Adobe Analytics.

The Edge Network uses the following logic to determine Adobe Analytics [page views](/help/components/metrics/page-views.md) and [link events](/help/components/metrics/page-events.md):

## Page views and link events using the `xdm` object

| XDM payload contains... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL` and no `xdm.web.webInteraction.type` | considers payload a **page view** |
| `xdm.eventType = web.webpagedetails.pageViews` | considers payload a **page view** |
| `xdm.web.webInteraction.type` and (`xdm.web.webPageDetails.name` or `xdm.web.webPageDetails.URL`) | considers payload a **link event** <br/>Also sets `xdm.web.webPageDetails.name` and `xdm.web.webPageDetails.URL` to `null` |
| `xdm.web.webInteraction.type` and (`xdm.web.webInteraction.name` or `xdm.web.webInteraction.URL`) | considers payload a **link event** <br/>Also sets `xdm.web.webPageDetails.name` and `xdm.web.webPageDetails.URL` to `null` if present |
| no `xdm.web.webInteraction.type` and no `xdm.web.webPageDetails.name` and no `xdm.web.webPageDetails.URL` | drops the payload and ignores the data |

>[!TIP]
>
>XDM field names in the payload are case-sensitive (for example, `webPageDetails.URL`). The `xdm.eventType` field is a string value with its own set of accepted values, and the casing in those values might not match XDM field names. For accepted values, see the `eventType` field in the [XDM ExperienceEvent class](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Minimal page view using `xdm` fields

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Minimal page view using `xdm.eventType`

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++Minimal link event using recommended fields

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## Page views and link events using the `data` object

| Data object payload contains... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` or `data.__adobe.analytics.pageURL` and no `data.__adobe.analytics.linkType` | considers payload a **page view** |
| `data.__adobe.analytics.linkType` and (`data.__adobe.analytics.linkName` or `data.__adobe.analytics.linkURL`) | considers payload a **link event** <br/>Also sets `data.__adobe.analytics.pageName` and `data.__adobe.analytics.pageURL` to `null` |
| no `data.__adobe.analytics.linkType` and no `data.__adobe.analytics.pageName` and no `data.__adobe.analytics.pageURL` | drops the payload and ignores the data |

+++Minimal page view using `data` fields

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Minimal link event using `data` fields

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>If you include both an `xdm` object and a `data` object in the same payload, Adobe Analytics checks both objects for respective fields.

## A4T and decisioning-related events

In addition to differentiating page views and link events, the following logic determines if certain decisioning events are categorized as A4T or are discarded.

| XDM payload contains... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` and `xdm._experience.decisioning` | considers payload an **A4T** call. |
| `xdm.eventType = decisioning.propositionDisplay` and no `xdm._experience.decisioning` | drops the payload and ignores the data |
| `xdm.eventType = decisioning.propositionInteract` and `xdm._experience.decisioning` and no `xdm.web.webInteraction.type` | considers payload an **A4T** call. |
| `xdm.eventType = decisioning.propositionInteract` and no `xdm._experience.decisioning` and no `xdm.web.webInteraction.type` | drops the payload and ignores the data. |
| `xdm.eventType = decisioning.propositionFetch` | drops the payload and ignores the data |

>[!TIP]
>
>The following `eventType` values are deprecated. Note that these values affect logic in the same way as their current counterparts:
>
>* The event type `display` is deprecated. Use `decisioning.propositionDisplay` instead.
>* The event type `click` is deprecated. Use `decisioning.propositionInteract` instead.
>* The event type `personalization.request` is deprecated. Use `decisioning.propositionFetch` instead.

+++Minimal A4T display

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++Minimal A4T interaction

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

See the [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) for more information.
