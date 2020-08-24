---
title: Use AppMeasurement with iFrames
description: Access Adobe Analytics variables inside an iFrame or a parent page while in an iFrame.
---

# Use AppMeasurement with iFrames

You can reference AppMeasurement variables from both child and parent iFrames. It is necessary to define all variables in the same location where the AppMeasurement library exists. The following examples explain how to set basic AppMeasurement variables and methods inside and outside an iFrame.

If you use Adobe Experience Platform Launch, make sure that the tracker object is globally accessible. See [Adobe Analytics extension overview](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) in the Launch user guide.

>![CAUTION]
>
>Avoid including AppMeasurement libraries on both a parent page and iFrame. Doing so introduces risks to sending multiple image requests, inflating reports and increasing billable server calls.

## Access AppMeasurement that resides in an iFrame

You can access AppMeasurement variables through the iFrame object. These examples set [pageName](../vars/page-vars/pagename.md) and call the [t() method](../vars/functions/t-method.md) using two different ways to reference the iFrame object.

```js
// Reference AppMeasurement code that resides within an iFrame and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iFrame";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iFrame on the page
window.frames[0].contentWindow.s.pageName = "Page name within iFrame";
window.frames[0].contentWindow.s.t();
```

## Access AppMeasurement from inside an iFrame

You can access AppMeasurement variables on a parent page from within an iFrame. This example sets [pageName](../vars/page-vars/pagename.md) and calls the [t() method](../vars/functions/t-method.md) using the [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) property.

```js
// Reference AppMeasurement code on a parent page from within an iFrame and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Limitations

* As with other JavaScript code, iFrames can only communicate when domains and protocol match. These examples do not work if the iFrame content resides on a different domain than the parent.
* If AppMeasurement resides in an iFrame, the [`referrer`](../vars/page-vars/referrer.md) variable is set to the parent URL, not the actual referring URL. You can manually set the `referrer` variable to resolve this issue.
* The [Adobe Experience Cloud debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) does not recognize image requests triggered within iFrames.
* Activity Map does not display the heatmap over links clicked within iFrames. The entire iFrame is highlighted instead.
