---
title: useBeacon
description: useBeacon lets you force AppMeasurement to use the browsers sendBeacon API
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
---
# useBeacon

Most modern browsers include the native method `navigator.sendBeacon()`. It asynchronously sends a small amount of data over HTTP to a web server. AppMeasurement can use the `navigator.sendBeacon()` method if the `useBeacon` variable is enabled. It is useful for exit links and other situations where you want to send information before the page unloads.

If `useBeacon` is enabled, the next hit sent to Adobe uses the browser's `navigator.sendBeacon()` method instead of a standard `GET` image request. This variable applies to both [`s.t()`](../functions/t-method.md) and [`s.tl()`](../functions/tl-method.md) image requests. It requires AppMeasurement 2.17.0 or higher.

>[!TIP]
>
>AppMeasurement automatically enables `useBeacon` for exit link image requests.

The `useBeacon` variable is ignored when the visitor uses a browser that does not support `navigator.sendBeacon()`. Use of this variable requires AppMeasurement 2.16.0 or higher.

## Use the sendBeacon API using the Web SDK extension

The **[!UICONTROL Document will unload]** checkbox within an Action Configuration determines if data sent to Adobe uses the sendBeacon API.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Rules] tab, then click the desired rule.
1. Under [!UICONTROL Actions], click the desired Action or click the **'+'** icon to add a new action.
1. Set the Extension dropdown to **[!UICONTROL Adobe Experience Platform Web SDK]** and the [!UICONTROL Action Type] to **[!UICONTROL Send event]**
1. Click the checkbox **[!UICONTROL Document will unload]** on the right.

If this box is checked, data is sent to Adobe using the sendBeacon API. It is unchecked by default.

## Use the sendBeacon API manually implementing the Web SDK

Set `documentUnloading` to `true` when sending an event. If not set, its default value is `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

See [Using the sendBeacon API](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) in the Web SDK documentation for more information.

## Use Beacon using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.useBeacon in AppMeasurement and the Analytics extension custom code editor

The `s.useBeacon` variable is a boolean that determines if AppMeasurement uses the browser's `navigator.sendBeacon()` method. Its default value is `false`. Set this variable to `true` before calling a tracking function if you want to use the asynchronous nature of `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>After a tracking call runs, this variable is reset to `false`. If your implementation sends multiple image requests in the same page load (such as single-page applications), set this variable to `true` before each tracking call.
