---
title: getVisitDuration
description: Track how much time a visitor has been on the site so far.
---

# Adobe plug-in: getVisitDuration

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help gain more value out of your use of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getVisitDuration` plug-in tracks the amount of time in minutes that the visitor has been on the site up to that point. Adobe recommends using this plug-in if you want to track cumulative time on the site up to that point, or to track the time it takes to perform an activity. This plug-in does not track the amount of time between events; if this functionality is desired, use the `getTimeBetweenEvents` plug-in.

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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getVisitDuration` method does not use any arguments. It returns one of the following values:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (where `[x]` is the number of minutes passed since the visitor landed on the site)

This plug-in creates a first-party cookie called `"s_dur"`, which is the number of milliseconds elapsed since the visitor landed on the site. The cookie expires after 30 minutes of inactivity.

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
