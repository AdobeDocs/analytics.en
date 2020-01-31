---
title: getVisitDuration
description: Track how much time a visitor has been on the site so far
---

# Adobe Experience Cloud Plugin – getVisitDuration

## Purpose of This Plugin

### What does this plugin do?
The getVisitDuration plugin tracks the amount of time (in minutes) that the visitor has been on the site up to that point.

### Why should I use this plugin?
You should use the getVisitDuration plugin if you want to track how long (in minutes) a visitor might have taken to perform a certain activity (e.g. purchase, lead generation, etc.) after landing on the site

### Why shouldn't I use this plugin?
You won't need to use the getVisitDuration plugin if you don’t need/want to track how many minutes it took a visitor to perform a certain activity.  Also, this plugin does not track the amount of time between events; this merely tracks the amount of time since the visitor landed on the site.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getVisitDuration plugin

## How to Deploy

You may use one of the following three methods to deploy the getVisitDuration plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitDuration v2.0 (Requires AppMeasurement) */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
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
	* Action Type: Initialize getVisitDuration
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the getVisitDuration plugin (via JavaScript), you will not need to pass in any arguments.

## Returns
The getVisitDuration plugin returns one of the following values depending on the situation
* "first hit of visit"
* “less than a minute”
* “1 minute”
* “[x] minutes” (where [x] is the number of minutes passed since the visitor landed on the site)

## Cookies
The getVisitDuration plugin creates a first-party cookie called “s_dur”, which is equal to the number of milliseconds passed since the visitor landed on the site.  The cookie expires after 30 minutes of inactivity (i.e. end of the visit)

## Example Calls

### Example #1
The following code...
```javascript
s.eVar10 = s.getVisitDuration();
```
...will always set eVar10 equal to the number of minutes passed since the visitor landed on the site

### Example #2
The following code...
```javascript
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```
...uses the inList plugin to check whether the events variable contains the purchase event.  If so, then eVar10 will be set equal to the number of minutes between the visitor's start of the visit and the time of purchase.

### Example #3
The following code...
```javascript
s.prop10 = s.getVisitDuration();
```
...will always set prop10 equal to the number of minutes passed since the visitor landed on the site.  This will be useful if prop10 has pathing enabled.  Adding the "exits" metric to the prop10 report will show a granular, "scatterplot" report of how long a visit took in minutes before a visitor left the site.

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.getVisitDuration=function()
```
...to this:
```javascript
[objectname].getVisitDuration=function()
```
## Version History

### 2.0 (2018-05-02) (previous changes undocumented)
* Point Release (complete reanalysis/rewrite of plugin)

