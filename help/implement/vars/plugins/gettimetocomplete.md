---
title: getTimeToComplete
description: Measure the amount of time taken to complete a task.
---

# Adobe plug-in: getTimeToComplete

## Purpose of This Plugin

### What does this plug-in do?
The getTimeToComplete plug-in will track the time a user takes to complete a process on a site. The "clock" begins when the "start" action is called and ends when the "stop" action is called.

### Why should I use this plug-in?
This plug-in is useful if there is a workflow on the site that takes some time to complete and the business would like to know how much time visitors are taking to complete it.

### Why shouldn't I use this plug-in?
This plug-in is not useful if the workflow on the site only takes a short period of time (less than 3 seconds) because the granularity is only down to the full second.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) as well as the formatTime and inList plug-ins (provided below) to run this plug-in

## How to Deploy

You may use one of the following three methods to deploy the getTimeToComplete plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install (and publish) the "Common Analytics Plugins" extension
1. For any Launch Rule that you want to use the plug-in in, add an [!UICONTROL action] with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided above into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires AppMeasurement; also the formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires AppMeasurement and inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getTimeToComplete plug-in (via JavaScript), be sure to pass in the following arguments:

* **sos** (optional, string): set equal to "start" in cases where you want to start a timer; otherwise set equal to "stop" in cases where you want to stop the timer; defaults to "start"
* **cn** (optional, string): the name of the cookie that will store the start time; defaults to "s_gttc"
* **exp** (optional, integer): the number of days that the timer will run (after being started) before it will expire; defaults to 0, when the timer will expire at the end of the session

## Returns
The getTimeToComplete plug-in returns the number of days, hours, minutes and/or seconds it took between the "start" and "stop" action.

## Cookies
The getTimeToComplete plug-in creates/reads from a first-party cookie with the name specified in the cn argument.  The value of the cookie is equal to a unix timestamp that represents the timer start time.  The cookie expires at the time specified in the exp argument.

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

### 3.1 (2019-09-30)
* Added logic that requires a value of either "start" or "stop" in the first argument.  All other values passed in will stop the plug-in from running
* Replaced inList 2.0 plug-in with inList 2.1
### 3.0 (2018-08-23)
* No change to the getTimeToComplete plug-in code but replaced the formatTime v1.0 plug-in code with the formatTime v1.1 plug-in code
### 3.0 (2018-04-17)
* Point Release (recompiled, smaller code size)
* Minor bug fixes
### 2.0 (2016-06-21) – previous versions undocumented
* Eliminated the dependency on the "s.p_fo" (page first only) plug-in.
* Added compatibility with H-code and AppMeasurement.
* Added console logging

