---
title: Use AppMeasurement with iframes
description: Access Adobe Analytics variables inside an iframe or a parent page while in an iframe.
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
---
# Use AppMeasurement with iframes

You can reference AppMeasurement variables from both child and parent iframes. It is necessary to define all variables in the same location where the AppMeasurement library exists. The following examples explain how to set basic AppMeasurement variables and methods inside and outside an iframe.

If you use tags in Adobe Experience Platform, make sure that the tracker object is globally accessible. See [Adobe Analytics extension overview](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

>[!CAUTION]
>
>Avoid including AppMeasurement libraries on both a parent page and iframe. Doing so introduces risks to sending multiple image requests, inflating reports and increasing billable server calls.

## Access AppMeasurement that resides in an iframe

You can access AppMeasurement variables through the iframe object. These examples set [pageName](../vars/page-vars/pagename.md) and call the [t() method](../vars/functions/t-method.md) using two different ways to reference the iframe object.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Access AppMeasurement from inside an iframe

You can access AppMeasurement variables on a parent page from within an iframe. This example sets [pageName](../vars/page-vars/pagename.md) and calls the [t() method](../vars/functions/t-method.md) using the [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) property.

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Use `postMessage` and event listeners

Alternatively, you can use `postMessage` and event listeners to set variables. This method doesn't require a direct reference to an iframe. 

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## Limitations

* As with other JavaScript code, iframes can only communicate when domains and protocol match. These examples do not work if the iframe content resides on a different domain than the parent.
* If AppMeasurement resides in an iframe, the [`referrer`](../vars/page-vars/referrer.md) variable is set to the parent URL, not the actual referring URL. You can manually set the `referrer` variable to resolve this issue.
* The [Adobe Experience Cloud debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) does not recognize image requests triggered within iframes.
* Activity Map does not display the heatmap over links clicked within iframes. The entire iframe is highlighted instead.
