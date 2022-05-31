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

## Register Pre Track Callback using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.registerPreTrackCallback in AppMeasurement and custom code editor

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
