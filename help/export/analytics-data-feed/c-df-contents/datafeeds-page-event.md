---
description: Lookup table to determine the type of a hit based on page event.
keywords: page;event;page_event;post_page_event
title: Page event lookup
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
---
# Page event lookup

Lookup table to determine the type of a hit based on the `page_event` value. As mentioned in the [Data column reference](datafeeds-reference.md), the `page_event` and `post_page_event` columns are tinyint unsigned.

* See [`t()`](/help/implement/vars/functions/t-method.md) to understand implementing page view calls for AppMeasurement and the Web SDK.
* See [`tl()`](/help/implement/vars/functions/tl-method.md) to understand implementing link tracking calls for AppMeasurement and the Web SDK.
* See [Implement Adobe Analytics with the Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) to understand how Adobe Analytics translates XDM payloads to page event types.

| `page_event` value | `post_page_event` value | Description |
| --- | --- | --- |
| `0` | `0` | All standard page view calls. It is the default value for most hits. |
| `10` | `100` | Custom links. Set link type to `o` (AppMeasurement) or `xdm.web.webInteraction.type` to `other` (Web SDK or Mobile SDK). |
| `11` | `101` | Download links. Set link type to `d` (AppMeasurement) or `xdm.web.webInteraction.type` to `download` (Web SDK or Mobile SDK). |
| `12` | `102` | Exit links. Set link type to `e` (AppMeasurement) or `xdm.web.webInteraction.type` to `exit` (Web SDK or Mobile SDK). |
| `31` | `76` | Media start |
| `32` | `77` | Media updates (with no other variable processing) |
| `33` | `78` | Media updates (with other variable processing) |
| `40` | `80` | Survey |
| `50` | `50` | Streaming media start |
| `51` | `51` | Streaming media close |
| `52` | `52` | Streaming media scrubbing |
| `53` | `53` | Streaming media keep alive |
| `54` | `54` | Streaming media ad start |
| `55` | `55` | Streaming media ad close |
| `56` | `56` | Streaming media ad scrubbing |
| `60` | `60` | Primetime media start |
| `61` | `61` | Primetime media close |
| `62` | `62` | Primetime media scrubbing |
| `63` | `63` | Primetime media keep alive |
| `64` | `64` | Primetime media ad start |
| `65` | `65` | Primetime media ad close |
| `66` | `66` | Primetime media ad scrubbing |
| `70` | `70` | Includes Target activity data |
