---
title: getTimeSinceLastVisit
description: Measure the amount of time elapsed between two visits.
---

# Adobe plug-in: getTimeSinceLastVisit

## Purpose of This Plugin

### What does this plug-in do?
The getTimeSinceLastVisit plug-in allows you to track how long a visitor has taken to return to your site after his/her last visit.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) as well as the formatTime and inList plug-ins (included below) to run the getTimeSinceLastVisit plug-in

## How to Deploy

You may use one of the following three methods to deploy the getTimeSinceLastVisit plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires AppMeasurement and formatTime/inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires AppMeasurement and inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getTimeSinceLastVisit plug-in (via JavaScript), you will not need to pass in any arguments.

## Returns
The getTimeSinceLastVisit plug-in returns the amount of time since the visitor last came to the site
* Any time between 30 minutes and an hour since the last visit will be set equal to the closest 1/2-minute benchmark (e.g. 30.5 minutes, 53 minutes, etc.)
* Any time between an hour and a day will be rounded to the closest quarter-hour benchmark (e.g. 2.25 hours, 7.5 hours, etc.)
* Anything greater than a day will be rounded to the closest day benchmark (e.g. 1 day, 3 days, 9 days, 372 days, etc.)
* "New Visitor" for new visitors or for visitors that haven't been to the site for over two years.
**NOTE:** The getTimeSinceLastVisit plug-in will return a value on only the first hit of the visit

## Cookies
The getTimeSinceLastVisit plug-in creates a first-party cookie called "s_tslv" that is set equal to a unix timestamp representing the current time.  The cookie expires after two years of inactivity.

## Example Calls

### Example #1
If a brand-new visitor comes to the site and the following code runs on the first page of the visit ...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```
...the value of s.prop1 will be set equal to “New Visitor”.

If the same code runs on the same domain after 35 minutes of inactivity, the value of s.prop1 will be set equal to “35 minutes”.

If the same code runs on the same domain after 4 days of further inactivity the value of s.prop1 will be set equal to “4 days”.

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plug-in code from this...

```js
s.getTimeSinceLastVisit = function(
```
...to this:

```js
[objectname].getTimeSinceLastVisit = function(
```

## Version History

### 1.0 (2018-04-16)
* Point Release (recompiled code, smaller size, etc.)
* Code Derived from "getDaysSinceLastVisit" (now deprecated and renamed)
* Now uses formatTime/inList plug-ins for return value

