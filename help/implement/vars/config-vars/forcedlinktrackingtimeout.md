---
title: forcedLinkTrackingTimeout
description: Use this variable with optional arguments in the s.tl() function.
---

# forcedLinkTrackingTimeout

When using the optional `doneAction` argument in the `tl()` tracking function, this variable is required. If you do not intend to use the optional `doneAction` argument, this variable does not do anything. See [The tl() function](../functions/tl.md) for more information.

This value sets the maximum number of milliseconds to wait before performing the `doneAction` passed into the `tl()` function. If the track link call completes before this timeout, the `doneAction` executes immediately at that time.

## Forced Link Tracking Timeout in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.forcedLinkTrackingTimeout in AppMeasurement and Launch custom code editor

The `s.forcedLinkTrackingTimeout` is an integer, representing the number of milliseconds AppMeasurement waits before executing the `doneAction` argument in the `tl()` function. Its default value is `250`.

```js
// Lengthen the timeout to 500ms before executing the doneAction argument
s.forcedLinkTrackingTimeout = 500;
```
