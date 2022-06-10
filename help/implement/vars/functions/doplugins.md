---
title: doPlugins
description: Configure logic just before a hit is compiled and sent to Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
---
# doPlugins

The `doPlugins` variable acts as a 'last call' to set values in your implementation. If [`usePlugins`](../config-vars/useplugins.md) is enabled, it automatically runs just before any type of image request is compiled and sent to Adobe, including:

* All page view ([`t()`](t-method.md)) calls
* All link tracking ([`tl()`](tl-method.md)) calls, including automatic download links and exit links

Use the `doPlugins` variable to call plug-in code and set final variable values just before an image request is compiled and sent to Adobe.

## Use On Before Event Send callback code using the Web SDK extension

Instead of `doPlugins`, the Web SDK uses `onBeforeEventSend` with similar functionality.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection], click the **[!UICONTROL Edit on before event send callback code]** button.
1. Place the desired code in the editor.

## Use `onBeforeEventSend` manually implementing the Web SDK

Instead of `doPlugins`, the Web SDK uses `onBeforeEventSend` with similar functionality. See [Modifying events globally](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) in the Web SDK documentation for more information.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Plug-ins using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.doPlugins in AppMeasurement and custom code

Set the `s.doPlugins` variable to a function containing desired code. The function automatically runs when you make a tracking call.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Set a function to the `doPlugins` variable only once in your implementation. If you set the `doPlugins` variable more than once, only the most recent code is used.

## Examples

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>Previous versions of AppMeasurement had slightly different `doPlugins()` code. Adobe recommends using the above format as a best practice.
