---
title: visitorID
description: Use a custom visitor ID.
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
---
# visitorID

Adobe uses several different methods to identify visitors on your site. The `visitorID` variable overrides all other methods of visitor identification.

>[!IMPORTANT]
>
>Adobe advises against using this variable. Use the [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) instead.

## Visitor ID using tags in Adobe Experience Platform

[!UICONTROL Visitor ID] is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Visitor ID] field.

Assign this field to the data element containing your custom visitor ID. Do not set this field to a static value.

## s.visitorID in AppMeasurement and custom code editor

The `s.visitorID` variable is a string that contains a custom unique identifier for the visitor. Valid values include alpha-numeric characters up to 100 bytes. Avoid using dashes, spaces, underscores, or symbols in this variable.

>[!WARNING]
>
>If you set the `visitorID` variable partway through a visit, data results in two separate unique visitors.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>An invalid implementation of custom visitor ID's can lead to incorrect data and poor reporting performance. If this variable contains a default value (such as `"0"` or `"NULL"`), Adobe treats these hits as if they are the same visitor. This situation results in incorrect data, with low visitor counts and visitor-level segments not working as expected. Incorrectly implemented custom visitor ID's also introduce heavy load on processing servers, increasing [latency](/help/technotes/latency.md) and decreasing report performance.
