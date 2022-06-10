---
title: abort
description: The abort variable is a boolean that prevents a hit from being sent to Adobe data collection servers.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
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
>The `abort` variable resets to `false` after every tracking call. If you need to abort subsequent tracking calls on the same page, set `abort` to `true` again.

For example, the `abort` variable can be set in the [`doPlugins()`](../functions/doplugins.md) function, which is the last function to run before an image request is sent to Adobe. This example operates similarly to the `onBeforeEventSend` callback using the Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

You can centralize the logic you use to identify activity that you do not want to track, such as some custom links or external links in display ads.
