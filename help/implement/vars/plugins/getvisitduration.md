---
title: getVisitDuration
description: Track how much time a visitor has been on the site so far.
---

# Adobe plug-in: getVisitDuration

## Purpose of This Plugin

### What does this plug-in do?
The getVisitDuration plug-in tracks the amount of time (in minutes) that the visitor has been on the site up to that point.

### Why should I use this plug-in?
You should use the getVisitDuration plug-in if you want to track how long (in minutes) a visitor might have taken to perform a certain activity (e.g. purchase, lead generation, etc.) after landing on the site

### Why shouldn't I use this plug-in?
You won't need to use the getVisitDuration plug-in if you don’t need/want to track how many minutes it took a visitor to perform a certain activity.  Also, this plug-in does not track the amount of time between events; this merely tracks the amount of time since the visitor landed on the site.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getVisitDuration plug-in

## How to Deploy

You may use one of the following three methods to deploy the getVisitDuration plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getVisitDuration v2.0 (Requires AppMeasurement) */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getVisitDuration plug-in (via JavaScript), you will not need to pass in any arguments.

## Returns
The getVisitDuration plug-in returns one of the following values depending on the situation
* "first hit of visit"
* “less than a minute”
* “1 minute”
* “[x] minutes” (where [x] is the number of minutes passed since the visitor landed on the site)

## Cookies
The getVisitDuration plug-in creates a first-party cookie called “s_dur”, which is equal to the number of milliseconds passed since the visitor landed on the site.  The cookie expires after 30 minutes of inactivity (i.e. end of the visit)

## Example Calls

### Example #1
The following code...

```js
s.eVar10 = s.getVisitDuration();
```
...will always set eVar10 equal to the number of minutes passed since the visitor landed on the site

### Example #2
The following code...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```
...uses the inList plug-in to check whether the events variable contains the purchase event.  If so, then eVar10 will be set equal to the number of minutes between the visitor's start of the visit and the time of purchase.

### Example #3
The following code...

```js
s.prop10 = s.getVisitDuration();
```
...will always set prop10 equal to the number of minutes passed since the visitor landed on the site.  This will be useful if prop10 has pathing enabled.  Adding the "exits" metric to the prop10 report will show a granular, "scatterplot" report of how long a visit took in minutes before a visitor left the site.

## Version History

### 2.0 (May 2, 2018)

* Point release (complete reanalysis/rewrite of plug-in).
