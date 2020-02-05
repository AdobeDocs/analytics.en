---
title: linkTrackVars
description: Specify which variables to include in link tracking image requests.
---

# linkTrackVars

Some implementations don't want to include all variables in all link tracking image requests. Use the `linkTrackVars` and `linkTrackEvents` variables to selectively include dimensions and metrics in `tl()` calls.

This variable is not used for page view calls (`t()` function).

## Variables in link tracking calls using Adobe Experience Platform Launch

Launch automatically populates this variable on the backend based on variables set in the interface, so it is always set in implementations using Launch.

> [!IMPORTANT] If you set variables in Launch using the custom code editor, you must include the variable in `linkTrackVars` using custom code as well.

## s.linkTrackVars in AppMeasurement and Launch custom code editor

The `s.linkTrackVars` variable is a string containing a comma-delimited list of variables that you want to include in link tracking image requests (`tl()` function). Both of the following criteria must be met to include dimensions in link tracking hits:

* Set the desired variable value. For example, `s.eVar1 = "Example value";`.
* Set the desired variable in the `linkTrackVars` variable. For example, `s.linkTrackEvents = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

The default value for this variable is an empty string. However, Adobe provided AppMeasurement code in the Code Manager where this variable is set to `"None"`. Valid values are any page-level variable that populates a dimension.

* If this variable is not defined or set to an empty string, *all* variables are included in link tracking image requests.
* If this variable is set to `"None"`, *no* variables are included in link tracking image requests.

> [!TIP] Avoid using the Analytics object identifier (`s.`) when specifying variables in this variable. For example, `s.linkTrackVars = "eVar1";` is correct, while `s.linkTrackVars = "s.eVar1";` is incorrect.

## Example

The following link tracking function includes only `eVar1` (not `eVar2`) in the image request sent to Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
