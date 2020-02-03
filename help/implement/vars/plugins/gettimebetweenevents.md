---
title: getTimeBetweenEvents
description: Measure the amount of time between two events.
---

# Adobe plug-in: getTimeBetweenEvents

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help gain more value out of your use of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getTimeBetweenEvents` plug-in allows you to track the amount of time between any two Analytics events, including shopping cart and custom events. It is useful in tracking the amount of time it takes for a checkout process to complete, or any other process that you want to measure time. This plug-in is unnecessary if you don't have any conversion processes that you want to measure how long they take.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. For any Launch Rule where you want to use the plug-in, add an action with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getTimeBetweenEvents plug-in (via JavaScript), be sure to pass in the following arguments:
* **ste** (required, string): startTimerEvents, or a comma-separated list of Adobe Analytics events that will "start the timer"
* **rt** (required, boolean): restartTimer
	* set equal to true if you want to restart the timer every time s.events contains an event in the start-timer (ste) argument
	* set equal to false if you don't want to restart the timer every time s.events contains an event in the ste argument.  This means only the first instance of s.events containing a "start-timer" event will actually start the timer
* **stp** (required, string): stopTimerEvents, or a comma-separated list of Adobe Analytics events that will "stop the timer"
* **res** (required, boolean) resetTimer:
	* Set equal to true if you want to record the time since the timer started AND reset the timer (when s.events contains an event in the stop-timer, or stp argument)
	* set equal to false if you want to only record the time since the timer started but not stop the timer.  This means the timer will continue to run after the events variable has recorded a stop event.  NOTE: when the res argument is set equal to false, setting the rte argument (see below) is highly recommended (defaults to true)
* **cn** (optional, string): The cookieName where the time of the first event is stored; (defaults to "s_tbe")
* **etd** (optional, integer): expireTimerInDays, or the expiration time for the cn cookie in days - set to 0 for session (defaults to 1 day when not set)
* **fmt** (optional, string): the format of the time that the number of seconds will be returned in (defaults to nothing)
	* "s" for seconds
	* "m" for minutes
	* "h" for hours
	* "d" for days
	* When not set, the return value's format will be based off the following rules:
		* Anything less than a minute will be rounded to the closest 5 second benchmark (e.g. 10 seconds, 15 seconds, etc.)
		* Anything between a minute and an hour will be rounded to the closest 1/2-minute benchmark (e.g. 30.5 minutes, 31 minutes, etc.)
		* Anything between an hour and a day will be rounded to the closest quarter-hour benchmark (e.g. 2.25 hours, 3.5 hours, etc.)
		* Anything greater than a day will be rounded to the closest day benchmark (e.g. 1 days, 3 days, 9 days, etc.)
* **bml** (optional, number): benchmarkLength, or the length of the rounding benchmark according to the format of the fmt argument
	* For example, if the fmt argument is equal to "s" and the bml argument is equal to 2, the return value will be rounded to the closest 2-second benchmark
	* Or, if the fmt argument is equal to "m" and the bml argument is equal to .5, the return value will be rounded to the closest 1/2-minute benchmark
* **rte** (optional, string): removeTimerEvents, or a comma-separated list of Adobe Analytics events that will remove/delete the timer (defaults to nothing)

## Returns
The getTimeBetweenEvents plug-in returns the amount of time between any of the events specified in the "ste" argument and any of the events specified in the "stp" argument (per the rules explained above)

## Cookies
The getTimeBetweenEvents plug-in creates a first-party cookie with the name specified in the "cn" argument (defaults to "s_tbe") and is equal to a Unix timestamp representing the timer's start time.  The cookie will expire after the number of days specified in the "etd" argument (when set) or when the visitor closes his/her browser (when the "etd" argument is not set)

## Example Calls

### Example #1
The following code...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```
...is configured to behave as follows:
* The timer will start when s.events contains event1.
* The timer will restart every time s.events contains event1
* The timer will stop when s.events contains event2
* The timer will reset (i.e. go to 0 seconds) every time s.events contains event2
* The timer will reset also when either s.events contains event3 OR if the visitor closes his/her browser
* When an actual time between event1 and event2 is recorded, the plug-in will set eVar1 equal to the number of seconds between the two events being set, rounded to the closest 2-second benchmark (e.g. 0 seconds, 2 seconds, 4 seconds, 10 seconds, 184 seconds, etc.)
* If s.events contains event2 before a timer has started, eVar1 won't be set at all.

### Example #2
The following code...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```
...is configured to behave as follows:
* The timer will start when s.events contains event1.
* The timer will NOT restart every time s.events contains event1, rather the original timer will still keep running
* The timer will NOT stop when s.events contains event2, but the plug-in will record the time since the original event1 setting was recorded
* The timer will be stored in a cookie called "s_20"
* The timer will reset only when either s.events contains event3 OR if 20 days has passed since the timer started
* When a time between (the original) event1 and event2 is recorded, the plug-in will set eVar1 equal to the number of hours between the two events being set, rounded to the closest 1 1/2-hour benchmark (e.g. 0 hours, 1.5 hours, 3 hours, 7.5 hours, 478.5 hours, etc.)

### Example #3
The following code...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```
...will produce similar results to the first example above; however, the value of eVar1 will be returned in either seconds, minutes, hours, or days, depending on the final length of the timer.  Also, the timer will expire 1 day after it was first set instead of at the time the visitor closes his/her browser.

## Version History

### 2.1 (May 26, 2018)

* Accommodates changes made to the new version of the `formatTime` plug-in.

### 2.0 (April 6, 2018)

* Complete rewrite/reanalysis of plug-in.
