---
title: getTimeToComplete
description: Measure the amount of time taken to complete a task on a website
---

# Adobe Experience Cloud Plugin – getTimeToComplete

## Purpose of This Plugin

### What does this plugin do?
The getTimeToComplete plug-in will track the time a user takes to complete a process on a site. The "clock" begins when the "start" action is called and ends when the "stop" action is called.

### Why should I use this plugin?
This plugin is useful if there is a workflow on the site that takes some time to complete and the business would like to know how much time visitors are taking to complete it.

### Why shouldn't I use this plugin?
This plugin is not useful if the workflow on the site only takes a short period of time (less than 3 seconds) because the granularity is only down to the full second.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) as well as the formatTime and inList plugins (provided below) to run this plugin

## How to Deploy

You may use one of the following three methods to deploy the getTimeToComplete plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires AppMeasurement; also the formatTime and inList plugins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires AppMeasurement and inList plugin) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```
**NOTE:** Adding the comments/version numbers of the code to the AppMeasurement file will help Adobe with troubleshooting any potential implementation issues.

### Method #2. Edit the Adobe Analytics Extension as contained within Adobe Experience Platform Launch

* Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
* Click on the desired property.
* Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
* Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
* Open the custom code editor and paste the plug-in code provided above into the edit window.
* Save and publish the changes to the Analytics extension.

### Method #3. Leverage the Common Analytics Plugin extension contained within Adobe Experience Platform Launch

* Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
* Click the desired property.
* Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
* Install (and publish) the "Common Analytics Plugins" extension
* For any Launch Rule that you want to use the plugin in, add an [!UICONTROL action] with the following configuration:
	* Extension: Common Analytics Plugins
	* Action Type: Initialize getTimeToComplete
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the getTimeToComplete plugin (via JavaScript), be sure to pass in the following arguments:

* **sos** (optional, string): set equal to "start" in cases where you want to start a timer; otherwise set equal to "stop" in cases where you want to stop the timer; defaults to "start"
* **cn** (optional, string): the name of the cookie that will store the start time; defaults to "s_gttc"
* **exp** (optional, integer): the number of days that the timer will run (after being started) before it will expire; defaults to 0, when the timer will expire at the end of the session

## Returns
The getTimeToComplete plugin returns the number of days, hours, minutes and/or seconds it took between the "start" and "stop" action.

## Cookies
The getTimeToComplete plugin creates/reads from a first-party cookie with the name specified in the cn argument.  The value of the cookie is equal to a unix timestamp that represents the timer start time.  The cookie expires at the time specified in the exp argument.

## Example Calls

### Example #1
Use these calls to determine the time between when a visitor starts the checkout process and when they make a purchase.

Start the timer when the visitor starts the checkout:
```javascript
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```
Stop the timer when the visitor makes the purchase and set prop1 to the time difference between stop and start:
```javascript
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
```javascript
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```
In the second example, event1 is meant to capture the beginning of a registration process that could take up to 7 days to complete, for whatever reason, and event2 is meant to capture the completion of the registration.  s.prop2 will capture the amount of time needed to complete the registration process

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.getTimeToComplete=function(sos,cn,exp)
```
...to this:
```javascript
[objectname].getTimeToComplete=function(sos,cn,exp)
```
## Version History

### 3.1 (2019-09-30)
* Added logic that requires a value of either "start" or "stop" in the first argument.  All other values passed in will stop the plugin from running
* Replaced inList 2.0 plugin with inList 2.1
### 3.0 (2018-08-23)
* No change to the getTimeToComplete plugin code but replaced the formatTime v1.0 plugin code with the formatTime v1.1 plugin code
### 3.0 (2018-04-17)
* Point Release (recompiled, smaller code size)
* Minor bug fixes
### 2.0 (2016-06-21) – previous versions undocumented
* Eliminated the dependency on the "s.p_fo" (page first only) plugin.
* Added compatibility with H-code and AppMeasurement.
* Added console logging

