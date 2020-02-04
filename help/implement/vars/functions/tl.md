---
title: tl
description: Send a link tracking call to Adobe.
---

# tl

The `tl` method is an important core component to Adobe Analytics. It takes all Analytics variables defined on the page, compiles them into an image request, and sends that data to Adobe data collection servers. It works similarly to the `t` method, however this method does not increment page views. It is useful for tracking links and other elements that wouldn't be considered a full page load.

If `trackDownloadLinks` or `trackExternalLinks` are enabled, AppMeasurement automatically calls the `tl` method to send download link and exit link tracking data. If your organization prefers to have more control over the links to track and their behavior, you can call the `tl` method manually. Custom links can only be manually tracked.

## Link tracking call in Adobe Experience Platform Launch

Launch has a dedicated location set a link tracking call.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the '+' icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button.

You cannot set any optional arguments in Launch.

## s.tl() method in AppMeasurement and Launch custom code editor

Call the `s.tl()` method when you want to send a tracking call to Adobe.

```js
s.tl();
```

Optionally, this method accepts several arguments:

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Link object

The link object argument determines if the browser waits up to 500ms before navigating away from the page. If an image request is sent sooner than 500ms, the page immediately navigates to the clicked link.

> [!NOTE] AppMeasurement automatically enables the `useBeacon` variable for exit links, making this argument no longer needed in modern browsers. This argument was used more commonly in previous versions of AppMeasurement.

* `this`: Wait up to 500ms to give AppMeasurement time to send an image request. Default value.
* `true`: Do not wait.

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### Link type

The link type argument is a single-letter string that determines the type of link tracking call. It is the same as setting the `linkType` variable.

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### Link name

The link name argument is a string that determines the link tracking dimension value. It is the same as setting the `linkName` variable.

```js
s.tl(true,"d","Example download link");
```

### Variable overrides

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

Use JavaScript to make a basic link tracking call:

```JavaScript
s.tl(true,"o","Example Link");
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
