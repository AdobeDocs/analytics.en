---
title: Implement Adobe Analytics with Adobe Experience Platform Edge
description: Overview of using XDM data from Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
---
# Implement Adobe Analytics with the Adobe Experience Platform Edge Network

The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. The Edge Network forwards the appropriate information to the desired products. This concept allows you to consolidate implementation efforts, especially spanning multiple data solutions. Adobe Analytics is one of the products that you can send data to using the Edge Network.

## How Adobe Analytics handles Edge Network data

Since data sent to the Edge Network and AppMeasurement data operate differently, the Edge Network payload determines how Adobe Analytics handles the hit. See [Edge Network event types in Adobe Analytics](hit-types.md) for more information.

Data sent to the Adobe Experience Platform Edge Network can follow three formats: **XDM object**, **Data object**, and **Context data**. When a datastream forwards data to Adobe Analytics, they are translated into a format that Adobe Analytics can handle.

## `xdm` object

Conform to schemas that you create based on [XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) (Experience Data Model). XDM gives you flexibility in what fields are defined as part of events. If you want to use a pre-defined schema specific to Adobe Analytics, you can add the [Adobe Analytics ExperienceEvent schema field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) to your schema. Once added, you can populate this schema using the `xdm` object in the Web SDK to send data to a report suite. When data arrives at the Edge Network, it translates the XDM object into a format that Adobe Analytics understands.

See [XDM object variable mapping to Adobe Analytics](xdm-var-mapping.md) for a full reference of XDM fields and how they map to Analytics variables.

>[!TIP]
>
>If you plan to move to [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing) in the future, Adobe advises against using the Adobe Analytics schema field group. Instead, Adobe recommends [creating your own schema](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) and use datastream mapping to populate the desired Analytics variables. This strategy does not lock you in to a schema of props and eVars when you're ready to make the move to Customer Journey Analytics.

## `data` object

As an alternative to using the `xdm` object, you can use the `data` object instead. The data object is geared towards implementations that currently use AppMeasurement, making the upgrade to the Web SDK much easier. The Edge Network detects the presence of fields specific to Adobe Analytics without the need to conform to a schema.

See [Data object variable mapping to Adobe Analytics](data-var-mapping.md) for a full reference of data object fields and how they map to Analytics variables.

## Context data variables

Send data to the Edge Network in any format that you'd like. Any fields that don't automatically map to `xdm` or `data` object fields are included as [Context data variables](/help/implement/vars/page-vars/contextdata.md) when forwarded to Adobe Analytics. You must then use [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) to map the desired fields to their respective Analytics variables.

For example, if you had a custom XDM schema that looked like the following:

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

Then these fields would be the context data keys available to you in the Processing rules interface:

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```
