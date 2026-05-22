---
title: registerPostTrackCallback
description: Create callback functions after sending a hit to Adobe.
feature: Appmeasurement Implementation
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/v-FVX1yPqGLFBhyOzW2rHbr56kRoho0vSzAhS4whSOc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# registerPostTrackCallback

The `registerPostTrackCallback` variable allows your organization to hook a JavaScript function immediately after a hit is successfully sent to Adobe. If a tracking call fails, this function does not run. You can use this variable to send data collected by AppMeasurement to a partner or in-house infrastructure, or clean up variable values in single-page applications.

>[!WARNING]
>
>Do not make any tracking calls like [`t()`](t-method.md) or [`tl()`](tl-method.md) inside the `registerPostTrackCallback` variable. Setting tracking calls in this variable cause an infinite loop of image requests!

Each time you call the `registerPostTrackCallback` variable, you hook that function to run immediately after an image request is successfully sent. Avoid registering the same function multiple times in the same page load.

>[!NOTE]
>
>The timing and order of functions fired between [`registerPreTrackCallback`](registerpretrackcallback.md) and `registerPostTrackCallback` are not guaranteed. Avoid dependencies between these two functions.

## Post-track Callback using the Web SDK extension

Coming soon!

## Post-track Callback manually implementing the Web SDK

You can use a JavaScript Promise when sending an event to register a function after data is successfully sent to Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

See [Handling responses from events](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#handling-responses-from-events) in the Web SDK documentation for more information.

## Register Post-track Callback using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.registerPostTrackCallback in AppMeasurement and the Analytics extension custom code editor

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

## Use case

Registering the [`clearVars()`](clearvars.md) function in the post track callback can be beneficial for single-page applications. Every time you successfully send a hit to Adobe, the `clearVars()` function runs. Your implementation can then define variables again without worrying about incorrectly persisting values.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
