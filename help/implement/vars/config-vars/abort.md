---
title: abort
description: The abort variable is a boolean that prevents a hit from being sent to Adobe data collection servers.
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
autotag-review: '2026-05-22T07:53:09.657Z'
TQID: 'https://experienceleague.adobe.com/3RASISgJtY29aSGrGzO7070ZyH-B5cl3Cgv3aN7xjEU'
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
# abort

The `abort` variable is a boolean that can prevent the next tracking call from being sent to Adobe. Similar functionality exists in the Web SDK allowing you to return `false` before an XDM event is sent.

## Cancel sending an event using the Web SDK extension

Use the [!UICONTROL On before event send callback] code editor and return `false`.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection], click the **[!UICONTROL Edit on before event send callback code]** button.
1. In the code editor, put the following code under any conditions that you want to abort sending data to Edge:

```js
return false;
```

## Cancel sending an event manually implementing the Web SDK

Use the `onBeforeEventSend` callback and return `false`. See [Modifying events globally](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) in the Web SDK documentation for more information.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Using the abort variable in the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.abort in AppMeasurement and the Analytics extension custom code editor

The `s.abort` variable is a boolean. Its default value is `false`.

* If set to `true`, the next tracking call ([`t()`](../functions/t-method.md) or [`tl()`](../functions/tl-method.md)) does not send any data to Adobe.
* If set to `false` or not defined, this variable does nothing.

```js
s.abort = true;
```

>[!NOTE]
>
>The `abort` variable resets to `false` after every tracking call. If you want to abort subsequent tracking calls on the same page, set `abort` to `true` again.

The `abort` variable can be set in the [`doPlugins()`](../functions/doplugins.md) function, which is the last function to run before an image request is sent to Adobe. This example operates similarly to the `onBeforeEventSend` callback using the Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

You can centralize the logic you use to identify activity that you do not want to track, such as some custom links or external links in display ads.
