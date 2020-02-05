---
title: visitorID
description: Use a custom visitor ID.
---

# visitorID

Adobe uses several different methods to identify visitors on your site. The `visitorID` variable overrides all other methods of visitor identification.

> [!IMPORTANT] Adobe advises against using this variable. Use the [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) instead.

## Visitor ID in Adobe Experience Platform Launch

[!UICONTROL Visitor ID] is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Visitor ID] field.

Assign this field to the data element containing your custom visitor ID. Do not set this field to a static value.

## s.visitorID in AppMeasurement and Launch custom code editor

The `s.visitorID` variable is a string that contains a custom unique identifier for the visitor. Valid values include alpha-numeric characters up to 100 bytes. Avoid using dashes, spaces, underscores, or symbols in this variable.

> [!WARNING] If you set the `visitorID` variable partway through a visit, data results in two separate unique visitors.

```js
s.visitorID = "abc123";
```
