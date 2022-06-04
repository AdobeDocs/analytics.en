---
title: registerPostTrackCallback
description: Create callback functions after sending a hit to Adobe.
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
---
# registerPostTrackCallback

The `registerPostTrackCallback` variable allows your organization to hook a JavaScript function immediately after a hit is successfully sent to Adobe. If a tracking call fails, this function does not run. You can use this variable to send data collected by AppMeasurement to a partner or in-house infrastructure, or clean up variable values in single-page applications.

>[!WARNING]
>
>Do not call any tracking calls like [`t()`](t-method.md) or [`tl()`](tl-method.md) inside the `registerPostTrackCallback` variable. Tracking functions in this variable cause an infinite loop of image requests!

Each time you call the `registerPostTrackCallback` variable, you hook that function to run immediately after an image request is successfully sent. Avoid registering the same function multiple times in the same page load.

>[!NOTE]
>
>The timing and order of functions fired between [`registerPreTrackCallback`](registerpretrackcallback.md) and `registerPostTrackCallback` are not guaranteed. Avoid dependencies between these two functions.

## Register Post Track Callback using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.registerPostTrackCallback in AppMeasurement and custom code editor

The `s.registerPostTrackCallback` is a function that takes a function as its only argument. The nested function runs immediately after an image request is successfully sent.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

If you want to use the image request URL in your code, reference the `requestUrl` string argument within the nested function. You can parse the `requestUrl` variable for your desired use; adjusting this variable does not impact data collection.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Additional arguments can be included in the `s.registerPostTrackCallback` function, which can be used in the nested function:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Use case example

Registering the [`clearVars()`](clearvars.md) function in the post track callback can be beneficial for single-page applications. Every time you successfully send a hit to Adobe, the `clearVars()` function runs. Your implementation can then define variables again without worrying about incorrectly persisting values.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
