---
title: linkTrackVars
description: Specify which variables to include in link tracking image requests.
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
TQID: https://experienceleague.adobe.com/B3So-VtGCz2klaFJT2a1zA3-AzSPaM9R-0jafXNsrVE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
---
# linkTrackVars

Some implementations don't want to include all variables in all link tracking image requests. Use the `linkTrackVars` and [`linkTrackEvents`](linktrackevents.md) variables to selectively include dimensions and metrics in [`tl()`](../functions/tl-method.md) calls.

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Determine which variables to include in an XDM event using the Web SDK

The Web SDK does not exclude certain fields for link tracking calls. However, you can use the `onBeforeEventSend` callback to clear or set desired fields before data is sent to Adobe. See [Modifying events globally](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) in the Web SDK documentation for more information.

## Variables in link tracking calls using the Adobe Analytics extension

This variable is automatically populated on the backend based on variables set in the interface, so it is always set in implementations using the Adobe Analytics extension.

>[!IMPORTANT]
>
>If you set variables using the custom code editor, you must include the variable(s) in `linkTrackVars` using custom code as well.

## s.linkTrackVars in AppMeasurement and the Analytics extension custom code editor

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
