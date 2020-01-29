---
title: doPlugins
description: Configure logic just before a hit is compiled and sent to Adobe.
---

# doPlugins

The `doPlugins` variable acts as a 'last call' to set values in your implementation. If `usePlugins` is `true`, it automatically runs just before any type of image request is compiled and sent to Adobe, including:

* All page view (`t`) calls
* All link tracking (`tl`) calls, including automatic download links and exit links

Use the `doPlugins` variable to call plugin code and set final variable values just before an image request is compiled and sent to Adobe.

## Plugins in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.doPlugins in AppMeasurement and Launch custom code

Set the `s.doPlugins` variable to a function containing desired code. The function automatically runs when you make a tracking call.

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] Set a function to the `doPlugins` variable only once in your implementation. If you set the `doPlugins` variable more than once, only the most recent code is used.

## Examples

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plugin (requires plugin code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

> [!NOTE] Previous versions of AppMeasurement had slightly different `doPlugins()` code. Adobe recommends using the above format as a best practice.
