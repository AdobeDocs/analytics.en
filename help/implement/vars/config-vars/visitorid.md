---
title: visitorID
description: Use a custom visitor ID.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
---
# visitorID

Adobe uses several different methods to [identify visitors](../../id/overview.md) on your site. **The `visitorID` variable overrides all other methods of visitor identification.**

>[!IMPORTANT]
>
>Adobe advises against using this variable. Use the [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) instead.

## How Analytics uses `visitorID`

This variable is a manual visitor ID override that replaces all other forms of visitor identification. To be counted as a single visitor, every hit for a person must use the same `visitorID` value.

* Hits that omit `visitorID` fall back to another visitor identification method and are treated as a separate visitor.
* Hits that use more than one `visitorID` value are treated as separate visitors.
* Adobe does not stitch hits that use different visitor IDs together.

See [Visitor identification in Adobe Analytics](../../id/overview.md) for details on identification precedence and why mixing identifiers can inflate visitor counts.

>[!WARNING]
>
>Set `visitorID` only if you can guarantee that it is set on every hit for that person and that the value never changes. Setting it on only some hits, introducing it partway through a visit (such as on authentication), or changing it between hits splits a single visitor's activity into multiple visitors.

>[!CAUTION]
>
>Invalid custom visitor ID values can lead to incorrect data and poor reporting performance. If this variable contains a default or placeholder value (such as `"0"` or `"NULL"`), Adobe treats these hits as if they are the same visitor. This situation results in incorrect data, with artificially low visitor counts and visitor-level segments not working as expected. Incorrectly implemented custom visitor IDs can also introduce heavy load on processing servers, increasing [latency](/help/technotes/latency.md) and decreasing report performance.

## Visitor ID using the Adobe Analytics extension

[!UICONTROL Visitor ID] is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Select the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then select the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Visitor ID] field.

Assign this field to the data element containing your custom visitor ID. **Do not set this field to a single static value for all visitors.** Use a data element that resolves per visitor and remains constant across all hits.

## s.visitorID in AppMeasurement and the Analytics extension custom code editor

The `s.visitorID` variable is a string that contains a custom unique identifier for the visitor. Valid values include alphanumeric characters up to 100 bytes. Avoid using dashes, spaces, underscores, or symbols in this variable.

```js
s.visitorID = "abc123";
```

## Visitor ID using the Web SDK

The Adobe Experience Platform Edge Network allows you to provide multiple identifiers using XDM's [Identity Map](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap). Each identity in an Identity Map has a different namespace. You can specify which namespace should be used for visitor ID as part of [datastream configuration](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics). Once this field is configured, when you send an event with a value specified for this namespace, it is automatically used as the visitor ID in Analytics.
