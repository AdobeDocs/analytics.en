---
title: linkTrackVars
description: Specify which variables to include in link tracking image requests.
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
---
# linkTrackVars

Some implementations don't want to include all variables in all link tracking image requests. Use the `linkTrackVars` and [`linkTrackEvents`](linktrackevents.md) variables to selectively include dimensions and metrics in [`tl()`](../functions/tl-method.md) calls.

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Variables in link tracking calls using tags in Adobe Experience Platform

Data Collection automatically populates this variable on the backend based on variables set in the interface, so it is always set in implementations using tags in Adobe Experience Platform.

>[!IMPORTANT]
>
>If you set variables using the custom code editor, you must include the variable in `linkTrackVars` using custom code as well.

## s.linkTrackVars in AppMeasurement and custom code editor

The `s.linkTrackVars` variable is a string containing a comma-delimited list of variables that you want to include in link tracking image requests (`tl()` method). Both of the following criteria must be met to include dimensions in link tracking hits:

* Set the desired variable value. For example, `s.eVar1 = "Example value";`.
* Set the desired variable in the `linkTrackVars` variable. For example, `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

The default value for this variable is an empty string. However, Adobe provided AppMeasurement code in the Code Manager where this variable is set to `"None"`. Valid values are any page-level variable that populates a dimension.

* If this variable is not defined or set to an empty string, *all* variables are included in link tracking image requests.
* If this variable is set to `"None"`, *no* variables are included in link tracking image requests.

>[!TIP]
>
>Avoid using the Analytics object identifier (`s.`) when specifying variables in this variable. For example, `s.linkTrackVars = "eVar1";` is correct, while `s.linkTrackVars = "s.eVar1";` is incorrect.

## Example

The following link tracking function includes only `eVar1` (not `eVar2`) in the image request sent to Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
