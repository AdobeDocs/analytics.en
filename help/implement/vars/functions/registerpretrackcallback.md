---
title: registerPreTrackCallback
description: Create callback functions before sending a hit to Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
---
# registerPreTrackCallback

The `registerPreTrackCallback` variable allows your organization to hook a JavaScript function after an image request URL is compiled but before it is sent. You can use this variable to send data collected by AppMeasurement to a partner or in-house infrastructure.

>[!WARNING]
>
>Do not call any tracking calls like [`t()`](t-method.md) or [`tl()`](tl-method.md) inside the [`registerPostTrackCallback`](registerposttrackcallback.md) variable. Tracking functions in this variable cause an infinite loop of image requests!

Each time you call the `registerPreTrackCallback` variable, you hook that function to run every time an image request URL is compiled. Avoid registering the same function multiple times in the same page load.

>[!NOTE]
>
>The timing and order of functions fired between `registerPreTrackCallback` and `registerPostTrackCallback` are not guaranteed. Avoid dependencies between these two functions.

## Pre-track callback using the Web SDK extension

The Web SDK does not have the ability to hook a function after data is compiled but before it is sent to Adobe. However, you can use `onBeforeEventSend` to register a function to execute just before data is sent.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection], click the **[!UICONTROL Edit on before event send callback code]** button.
1. Place the desired code in the editor.

## Pre-track callback manually implementing the Web SDK

The Web SDK does not have the ability to hook a function after data is compiled but before it is sent to Adobe. However, you can use `onBeforeEventSend` to register a function to execute just before data is sent, similar to `doPlugins`. See [Modifying events globally](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) in the Web SDK documentation for more information.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Pre-track callback using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.registerPreTrackCallback in AppMeasurement and the Analytics extension custom code editor

The `s.registerPreTrackCallback` is a function that takes a function as its only argument. The nested function runs just before an image request is sent.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

If you want to use the image request URL in your code, reference the `requestUrl` string argument within the nested function. You can parse the `requestUrl` variable for your desired use; adjusting this variable does not impact data collection.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

You can include additional arguments in the `s.registerPreTrackCallback` function, which can be used in the nested function:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>Setting page variables or altering the `requestUrl` string within this function do **not** impact the image request sent shortly after this function call. Use the [`doPlugins()`](doplugins.md) variable instead.
