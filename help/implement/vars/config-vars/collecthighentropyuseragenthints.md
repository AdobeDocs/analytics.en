---
title: collectHighEntropyUserAgentHints
description: Use the collectHighEntropyUserAgentHints variable to determine whether Adobe will request high entropy hints from Chromium browsers (e.g. Google Chrome and Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Variables
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
