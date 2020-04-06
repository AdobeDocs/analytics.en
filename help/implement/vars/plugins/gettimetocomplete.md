---
title: getTimeToComplete
description: Measure the amount of time taken to complete a task.
---

# Adobe plug-in: getTimeToComplete

>[!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getTimeToComplete` plug-in tracks the time a user takes to complete a process on a site. The "clock" begins when the `start` action is called and ends when the `stop` action is called. Adobe recommends using this plug-in if there is a workflow on the site that takes some time to complete and you would like to know how much time visitors take to complete it. It is unnecessary to use this plug-in if the workflow on your site takes a short period of time (less than 3 seconds) because the granularity is only down to the full second.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getTimeToComplete
1. Save and publish the changes to the rule.

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getTimeToComplete` method uses the following arguments:

* **`sos`** (optional, string): Set to `"start"` when you want to start the timer. Set to `"stop"` when you want to stop the timer. Defaults to `"start"`.
* **`cn`** (optional, string): The name of the cookie to store the start time. Defaults to `"s_gttc"`.
* **`exp`** (optional, integer): The number of days that the cookie (and timer) expires. Defaults to `0`, which represents the end of the browser session.

Calling this method returns a string that contains the number of days, hours, minutes and/or seconds it took between the `"start"` and `"stop"` action.

## Example Calls

### Example #1

Use these calls to determine the time between when a visitor starts the checkout process and when they make a purchase.

Start the timer when the visitor starts the checkout:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Stop the timer when the visitor makes the purchase and set prop1 to the time difference between stop and start:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 will capture the amount of time needed to complete the purchase process

### Example #2

If you want to have several timers running at the same time (to measure different processes), you will need to manually set the cn cookie argument.  For example, if you want to measure the amount of time needed for a purchase to complete, you would set the following code...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...but if you also wanted to measure (at the same time) the amount of time needed for a registration form to be filled out, you would run the following code as well:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

In the second example, event1 is meant to capture the beginning of a registration process that could take up to 7 days to complete, for whatever reason, and event2 is meant to capture the completion of the registration.  s.prop2 will capture the amount of time needed to complete the registration process

## Version History

### 3.1 (September 30, 2019)

* Added logic that requires a value of either "start" or "stop" in the first argument.  All other values passed in stop the plug-in from running.
* Updated `inList 2.0` plug-in to `inList 2.1`.

### 3.0 (August 23, 2018)

* Updated the `formatTime v1.0` plug-in to `formatTime v1.1`.

### 3.0 (April 17, 2018)

* Point release (recompiled, smaller code size).
* Minor bug fixes.

### 2.0 June 21, 2016)

* Eliminated the dependency on the `p_fo` plug-in.
* Added compatibility with H-code and AppMeasurement.
* Added console logging.
