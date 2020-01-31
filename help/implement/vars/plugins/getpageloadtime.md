---
title: getPageLoadTime
description: Track the amount of time needed for a page to load
---

# Adobe Plugin: getPageLoadTime

## Plugin Purpose

### What does this plugin do?

The getPageLoadTime plugin uses the JavaScript performance object to allow you to measure the amount of time a page takes to completely load.

### Why should I use this plugin?

You should use the getPageLoadTime plugin if you want to measure how long your web pages take to load.

### Why shouldn't I use this plugin?

You won't need to use the getPageLoadTime plugin if you don't need/want to track how long your pages take to load.

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) and the p_fo Plugin, along with the performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (included in the Code to Deploy section below), to run the getPageLoadTime plugin

## How to Deploy

You may use one of the following three methods to deploy the getPageLoadTime plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file

Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageLoadTime v1.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
s.getPageLoadTime=function(){var a=this;if("undefined"!==typeof performance&&a.p_fo("performance")){var b=performance; b.clearResourceTimings();""!==a.c_r("s_plt")&&(0<b.timing.loadEventEnd&&clearInterval(a.pi),a._pltLoadTime=a.c_r("s_plt"),a._pltPreviousPage=a.c_r("s_pltp"),a.c_w("s_plt",""),a.c_w("s_pltp",""));0===b.timing.loadEventEnd?a.pi=setInterval(function(){a.performanceWriteFull()},250):0<b.timing.loadEventEnd&&(a.ptc?a.ptc===b.timing.loadEventEnd&&1===b.getEntries().length&&(a.pwp=setInterval(function(){a.performanceWritePart()},500)):a.performanceWriteFull())}};
s.performanceWriteFull=function(){var s=this,a=performance.timing;0<a.loadEventEnd&&(clearInterval(s.pi),""===s.c_r("s_plt")&& (s.c_w("s_plt",s.performanceCheck(a.loadEventEnd,a.navigationStart)),s.c_w("s_pltp",s.pageName)));s.ptc=a.loadEventEnd};
s.performanceWritePart=function(){var s=this,a=performance;0<a.getEntries().length&&(s.ppfe===a.getEntries().length? clearInterval(s.pwp):s.ppfe=a.getEntries().length);""===s.c_r("s_plt")&&(s.c_w("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),s.c_w("s_pltp",s.pageName))};
s.performanceCheck=function(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
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
	* Action Type: Initialize getPageLoadTime
* Save and publish the changes to the rule

## How to Run the Plugin

When calling the getPageLoadTime plugin (via JavaScript), you will not need to pass in any arguments.

## Returns
The getPageLoadTime plugin returns nothing but will set the following variables in the AppMeasurement object as a new page loads:
* s._pltPreviousPage = the previous page, to be correlated with the load time of the previous page
* s._pltLoadTime = the time, in seconds, that the previous page took to load.

## Cookies
The getPageLoadTime plugin creates two first-party cookies:
* s_plt = the time, in seconds, that the previous page took to load
* s_pltp = the value of the s.pageName variable as recorded in the previous Adobe Analytics image request.
Both cookies expire when the visitor closes the browser.

## Example Calls

### Example #1
Running the following code...
```javascript
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
	s.prop10 = s._pltLoadTime;
	s.prop11 = s._pltPreviousPage
	s.eVar10 = prop11;
	s.events = "event100=" + s._pltLoadTime;
}
```
...will do the following:
* Run the getPageLoadTime plugin when s.pageName is set
* Set s.prop10 equal to the load time of the previous page
* Set s.prop11 and s.eVar10 equal to the name of the previous page (as recorded in s.pageName)
* Set event100, which would be a custom numeric event, equal to the load time of the previous page.   Using a custom event in this case would allow you to get the total amount of time for all page loads of the previous page (from all visitors/visits) and thus use a calculated metric to get the average page load time for each page

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.getPageLoadTime=function(lv,cn,d1)
```
...to this:
```javascript
[objectname].getPageLoadTime=function(lv,cn,d1)
```
Also be sure to change this...
```javascript
s.performanceWriteFull=function()
```
...to this:
```javascript
[objectname].performanceWriteFull=function()
```
And change this...
```javascript
s.performanceWritePart=function()
```
...to this:
```javascript
[objectname].performanceWritePart=function()
```
And change this...
```javascript
s.performanceCheck=function()
```
...to this:
```javascript
[objectname].performanceCheck=function()
```
And (finally) change this...
```javascript
s.p_fo=function(on)
```
...to this:
```javascript
[objectname].p_fo=function(on)
```

## Version History

### 1.0 (2018-05-22)
* First Official Release