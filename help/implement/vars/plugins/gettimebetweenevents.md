---
title: getTimeBetweenEvents
description: Measure the amount of time taken between two different events that coudl take place on a website
---

# Adobe Experience Cloud Plugin – getTimeBetweenEvents

## Purpose of This Plugin

### What does this plugin do?
The getTimeBetweenEvents plugin allows you to track the amount of time between two different Adobe Analytics events (custom or otherwise)

### Why should I use this plugin?
You should use the getTimeBetweenEvents plugin if you want to track, for example, the amount of time it takes for the checkout process to complete, or for any other process that might take a specific amount of time.

### Why shouldn't I use this plugin?

You won't need to use the getTimeBetweenEvents plugin if you don't need to measure the amount of time needed to complete a certain process that takes place on your website.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) as well as the formatTime and inList plugins (included in the Code to Deploy section below) to run the getTimeBetweenEvents plugin

## How to Deploy

You may use one of the following three methods to deploy the getTimeBetweenEvents plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires AppMeasurement; also formatTime and inList plugins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

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
	* Action Type: Initialize getTimeBetweenEvents
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the getTimeBetweenEvents plugin (via JavaScript), be sure to pass in the following arguments:
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
The getTimeBetweenEvents plugin returns the amount of time between any of the events specified in the "ste" argument and any of the events specified in the "stp" argument (per the rules explained above)

## Cookies
The getTimeBetweenEvents plugin creates a first-party cookie with the name specified in the "cn" argument (defaults to "s_tbe") and is equal to a Unix timestamp representing the timer's start time.  The cookie will expire after the number of days specified in the "etd" argument (when set) or when the visitor closes his/her browser (when the "etd" argument is not set)

## Example Calls

### Example #1
The following code...
```javascript
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```
...is configured to behave as follows:
* The timer will start when s.events contains event1.
* The timer will restart every time s.events contains event1
* The timer will stop when s.events contains event2
* The timer will reset (i.e. go to 0 seconds) every time s.events contains event2
* The timer will reset also when either s.events contains event3 OR if the visitor closes his/her browser
* When an actual time between event1 and event2 is recorded, the plugin will set eVar1 equal to the number of seconds between the two events being set, rounded to the closest 2-second benchmark (e.g. 0 seconds, 2 seconds, 4 seconds, 10 seconds, 184 seconds, etc.)
* If s.events contains event2 before a timer has started, eVar1 won't be set at all.

### Example #2
The following code...
```javascript
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```
...is configured to behave as follows:
* The timer will start when s.events contains event1.
* The timer will NOT restart every time s.events contains event1, rather the original timer will still keep running
* The timer will NOT stop when s.events contains event2, but the plugin will record the time since the original event1 setting was recorded
* The timer will be stored in a cookie called "s_20"
* The timer will reset only when either s.events contains event3 OR if 20 days has passed since the timer started
* When a time between (the original) event1 and event2 is recorded, the plugin will set eVar1 equal to the number of hours between the two events being set, rounded to the closest 1 1/2-hour benchmark (e.g. 0 hours, 1.5 hours, 3 hours, 7.5 hours, 478.5 hours, etc.)

### Example #3
The following code...
```javascript
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```
...will produce similar results to the first example above; however, the value of eVar1 will be returned in either seconds, minutes, hours, or days, depending on the final length of the timer.  Also, the timer will expire 1 day after it was first set instead of at the time the visitor closes his/her browser.

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte)
```
...to this:
```javascript
[objectname].getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte)
```
Also be sure to change this...
```javascript
s.formatTime=function(ns,tf,bml)
```
...to this:
```javascript
[objectname].formatTime=function(ns,tf,bml)
```
And change this...
```javascript
s.inList=function(lv,vtc,d,cc){
```
...to this:
```javascript
[objectname].inList=function(lv,vtc,d,cc){
```

## Version History

### 2.1 (2018-05-26)
* Accommodates changes made to the new version of the formatTime plugin
### 2.0 (2018-04-06) (Previous Changes Undocumented)
* Complete Rewrite/Reanalysis of Plugin
