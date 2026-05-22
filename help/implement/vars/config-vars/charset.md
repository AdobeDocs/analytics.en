---
title: charSet
description: The charSet variable determines what encoding Adobe uses to parse your image request.
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bPK-uLu-IgKnJWGpAUnS7cmRm808jhetzm-Cyd2R39o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# charSet

The `charSet` variable is used by Adobe to convert incoming data into UTF-8 for storage and reporting by Analytics. Most sites do not need to set this variable.

Set this variable only if you see garbled values ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) in reports. You can set this variable on a page-by-page basis if your site uses different encodings on different pages.

## Character Set in the Web SDK

The Web SDK currently supports only UTF-8, and does not provide options to change encoding.

## Character Set in the Adobe Analytics extension

Character Set is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension in Adobe Experience Platform Data Collection.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL General] accordion, which reveals the [!UICONTROL Character Set] field.

You can use either a preset character set or a custom character set. Avoid changing the value from `UTF-8` unless you see garbled values in reports.

## s.charSet in AppMeasurement and the Analytics extension custom code editor

The `charSet` variable is a string. If you have garbled values in Adobe Analytics, set this variable to the same value as the `<meta charset="">` HTML tag on your site.

```js
s.charSet = "UTF-8";
```
