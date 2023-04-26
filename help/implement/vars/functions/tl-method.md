---
title: tl
description: Send a link tracking call to Adobe.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
---
# tl

The `tl()` method is an important core component to Adobe Analytics. It takes all Analytics variables defined on the page, compiles them into an image request, and sends that data to Adobe data collection servers. It works similarly to the [`t()`](t-method.md) method, however this method does not increment page views. It is useful for tracking links and other elements that wouldn't be considered a full page load.

If [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) or [`trackExternalLinks`](../config-vars/trackexternallinks.md) are enabled, AppMeasurement automatically calls the `tl()` method to send download link and exit link tracking data. If your organization prefers to have more control over the links to track and their behavior, you can call the `tl()` method manually. Custom links can only be manually tracked.

## Link tracking using the Web SDK

The Web SDK does not differentiate between page view calls and link tracking calls; both use the `sendEvent` command. If you want Adobe Analytics to count a given XDM event as a link tracking call, make sure that your XDM data includes or is mapped to `web.webInteraction.name`, `web.webInteraction.URL`, and `web.webInteraction.type`.

* Link name maps to `web.webInteraction.name`.
* Link URL maps to `web.webInteraction.URL`.
* Link type maps to `web.webInteraction.type`. Valid values include `other` (Custom links), `download` (Download links), and `exit` (Exit links).

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

## Link tracking using the Adobe Analytics extension

The Adobe Analytics extension has a dedicated location to set a link tracking call.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
1. Under [!UICONTROL Actions], click the desired action or click the **'+'** icon to add an action.
1. Set the [!UICONTROL Extension] drop-down list to **[!UICONTROL Adobe Analytics]**, and the [!UICONTROL Action Type] to **[!UICONTROL Send Beacon]**.
1. Click the `s.tl()` radio button.

You cannot set any optional arguments in the Analytics extension.

## s.tl() method in AppMeasurement and the Analytics extension custom code editor

Call the `s.tl()` method when you want to send a tracking call to Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Link object (required)

The link object argument determines if the browser waits up to 500ms before navigating away from the page. If an image request is sent sooner than 500ms, the page immediately navigates to the clicked link.

>[!NOTE]
>
>AppMeasurement automatically enables the [`useBeacon`](../config-vars/usebeacon.md) variable for exit links, making this argument no longer needed in modern browsers. This argument was used more commonly in previous versions of AppMeasurement.

* `this`: Wait up to 500ms to give AppMeasurement time to send an image request. Default value.
* `true`: Do not wait.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Link type (required)

The link type argument is a single-character string that determines the type of link tracking call. There are three valid values.

* `o`: The link is a [Custom link](/help/components/dimensions/custom-link.md).
* `d`: The link is a [Download link](/help/components/dimensions/download-link.md).
* `e`: The link is an [Exit link](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Link name (recommended)

The link name argument is a string that determines the link tracking dimension item. When using the [Custom link](/help/components/dimensions/custom-link.md), [Download link](/help/components/dimensions/download-link.md), or [Exit link](/help/components/dimensions/exit-link.md) dimensions in reporting, this string contains the dimension item. If this argument is not set, the [linkURL](../config-vars/linkurl.md) variable is used.

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Variable overrides (optional)

Lets you change variable values for a single call. See [variable overrides](../../js/overrides.md) for more information.

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Examples and use cases

Send a basic link tracking call directly inside an HTML link:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Use JavaScript to make a basic link tracking call using method arguments:

```JavaScript
s.tl(true,"o","Example link");
```

### Make link tracking calls within a custom function

You can consolidate link tracking code into a self-contained JavaScript function defined on the page or in a linked JavaScript file. Calls can then be made in the onClick function of each link. Set the following in a JavaScript file:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

You can then call the function whenever you want to track a given link:

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### Avoid tracking duplicate links

If `trackDownloadLinks` or `trackExternalLinks` are enabled, AppMeasurement automatically makes a link tracking call if the correct filters match. If you also manually call `s.tl()` for these link clicks, you can send duplicate data to Adobe. Duplicate data inflates report numbers and makes them less accurate.

For example, the following function would send two link tracking calls for same link click (manual and automatic download links):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

You can help prevent duplicate link tracking calls by using the following modified function. It first checks to see if a link object exists, and only sends a manual link tracking call if the link object is an empty string.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
