---
title: charSet
description: The charSet variable determines what encoding Adobe uses to parse your image request.
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
---
# charSet

The charSet variable is used by Adobe to convert incoming data into UTF-8 for storage and reporting by Analytics. Most sites do not need to set this variable.

Set this variable only if you see garbled values ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) in reports. You can set this variable on a page-by-page basis if your site uses different encodings on different pages.

## Character Set in Adobe Experience Platform

Character Set is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
1. Expand the [!UICONTROL General] accordion, which reveals the [!UICONTROL Character Set] field.

You can use either a preset character set or a custom character set. Avoid changing the value from `UTF-8` unless you see garbled values in reports.

## s.charSet in AppMeasurement and custom code editor

The `charSet` variable is a string. If you have garbled values in Adobe Analytics, set this variable to the same value as the `<meta charset="">` HTML tag on your site.

```js
s.charSet = "UTF-8";
```
