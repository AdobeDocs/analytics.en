---
title: collectHighEntropyUserAgentHints
description: Use the collectHighEntropyUserAgentHints variable to determine whether Adobe will request high entropy hints from Chromium browsers (e.g. Google Chrome and Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/SfKPGVjuEsMzJUVJYSEh9M8eawg0RqLNceSlqrTu3Ps'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
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
# collectHighEntropyUserAgentHints

High-entropy client hints are used by Adobe Analytics to improve device and browser identification. This option is available starting with version 2.23.0 of AppMeasurement.js. Read more about client hints in [this overview and FAQ](/help/technotes/client-hints.md) as well as [Google's blog](https://web.dev/user-agent-client-hints/).

## Collect high-entropy hints using the Web SDK

High-entropy client hints are part of the context categories in Web SDK. See [Configure the Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) for more details.

## Collect high-entropy hints using the Adobe Analytics Extension

**[!UICONTROL Collect high-entropy user-agent hints]** is a check box under the General accordion when configuring the Adobe Analytics extension. 

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/@adobepm/data-collection) using your AdobeID credentials.
1. Click the desired [!UICONTROL tag property].
1. Go to the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
1. Expand the [!UICONTROL General] accordion, which reveals the [!UICONTROL Collect high entropy user-agent hints] check box. It is unchecked by default.

## collectHighEntropyUserAgentHints in AppMeasurement

The `s.collectHighEntropyUserAgentHints` variable determines if AppMeasurement requests high-entropy hints from Chromium browsers (for example, Google Chrome or Microsoft Edge). These hints are used by Adobe Analytics to improve device and browser identification.

If set to `true`, all high entropy hints will be requested from the browser.

```js
s.collectHighEntropyUserAgentHints = true;
```
