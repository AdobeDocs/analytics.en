---
title: abort
description: The abort variable is a boolean that prevents a hit from being sent to Adobe data collection servers.
---

# abort

The `abort` variable is a boolean that can prevent the next tracking call from being sent to Adobe.

## Using the abort variable in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## AppMeasurement syntax and custom code editor in Launch

The `abort` variable is a boolean. Its default value is `false`.

* If set to `true`, the next tracking call (`t()` or `tl()`) does not send any data to Adobe.
* If set to `false` or not defined, this variable does nothing.

```js
s.abort = true;
```

> [!NOTE] The `abort` variable resets to `false` after every tracking call. If you need to abort subsequent tracking calls on the same page, set `abort` to `true` again.

## Example

The `abort` variable can be set in the `doPlugins()` function, which is the last function to run before an image request is sent to Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

You can centralize the logic you use to identify activity that you do not want to track, such as some custom links or external links in display ads.
