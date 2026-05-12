---
title: Use AppMeasurement with iframes
description: Access Adobe Analytics variables inside an iframe or a parent page while in an iframe.
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/og9yeHUn5BJVm8-22V2l1frcpluXdlI-f0LnyjFacnk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
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
* The [Adobe CX Enterprise debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) does not recognize image requests triggered within iframes.
* Activity Map does not display the heatmap over links clicked within iframes. The entire iframe is highlighted instead.
