---
title: getPreviousValue
description: Get the value of a variable from the previous web page.
---

# getPreviousValue

The `getPreviousValue` plug-in obtains a variable value from a previous hit. It stores variable values in cookies so they are preserved between hits. This plug-in is valuable if you want to use previous values as direct dimensions, instead of using breakdowns, segmentation, or attribution to determine previous values.

You define the cookie names this plug-in uses. They expire after exactly 30 minutes and refresh on each page load.

## Install the getPreviousValue plug-in using Adobe Experience Platform Launch

You can install the `s.getPreviousValue()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `s.getPreviousValue()` function in the custom code editor of rules to assign variable values.

## Install the getPreviousValue plug-in using AppMeasurement

You can install the `s.getPreviousValue()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere after the tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)).
3. Save the JS file and upload the new version to your web server.

Once installed, you can use the `s.getPreviousValue()` method to assign variable values.

## Plug-in code

> [!NOTE] This plug-in requires the `split` plug-in. Make sure you include dependent plug-ins to avoid JavaScript errors.

```js
// getPreviousValue v1.1 (requires split plug-in)
s.getPreviousValue = function(v,c,el) {var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t):s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t):s.c_w(c,'no value',t);return r}};
```

## Use the getPreviousValue plug-in with AppMeasurement and Launch custom code editor

The `s.getPreviousValue()` method returns a string containing a value stored in a cookie. It has three arguments:

* **Variable name** (required): The source variable you want to retrieve values from.
* **Cookie name** (required): A string that represents the cookie name used to store and retrieve values. You can use any cookie name you want, however Adobe recommends including the prefix `gpv_` to easily identify the purpose of this cookie.
* **Trigger event** (optional): A string that represents the event(s) that must be set on the page view to trigger the retrieval of the previous value. If omitted, this plug-in always attempts to get the previous value.

> [!IMPORTANT] Define the source variable before referencing this plug-in. If you set the source variable after calling this plug-in, values are not correctly stored in the cookie. Adobe recommends using this plug-in within the `doPlugins` function so source variable values are guaranteed to be set.

If the cookie is not yet set (for example, during the first hit of the visit), The string `"no value"` is returned.

```js
// Use eVar1 to get the pageName from a previous hit
s.eVar1 = s.getPreviousValue(s.pageName,"gpv_pn");

// Use eVar1 to get eVar2 from a previous hit, but only if event1 exists
s.events = "event1";
s.eVar1 = s.getPreviousValue(s.eVar2,"gpv_v2","event1");
```
