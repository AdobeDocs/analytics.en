---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.useForcedLinkTracking

This flag is used to disable forced link tracking for some browsers. Forced link tracking is enabled by default for FireFox 20+ and WebKit browsers.

When `useForcedLinkTracking` is enabled, the AppMeasurement file overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. The AppMeasurement file executes the track link call and handles the navigation event manually, instead of using the default browser action.

In JavaScript H.25.4 (released February 2013), the following scope limitations were added to links tracked when `useForcedLinkTracking` is enabled. The automatic forced link tracking applies only to:

* `<A>` and `<AREA>` tags. 
* The tag must have an `HREF` attribute. 
* The `HREF` can't start with `#`, `about:`, or `javascript:`. 
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

Default Value = true

## Example 

`s.useForcedLinkTracking = false`

