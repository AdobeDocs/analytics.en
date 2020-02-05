---
title: getNewRepeat
description: Track activity of new vs. repeat visitors.
---

# Adobe plug-in: getNewRepeat

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getNewRepeat` plug-in allows you to determine whether a visitor to the site is a new visitor or a repeat visitor within a desired number of days. Adobe recommends using this plug-in if you want to identify visitors as "new" using a custom number of days. This plug-in is unnecessary if the New/Repeat visitor dimensions in Analysis Workspace meet your organization's needs.

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
    * Action Type: Initialize getNewRepeat
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

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getNewRepeat` method uses the following arguments:

* **`d`** (integer, optional): The minimum number of days required between visits that resets visitors back to `"New"`. If this argument is not set, it defaults to 30 days.

This method returns the value of `"New"` if the cookie set by the plug-in doesn't exist or has expired. It returns the value of `"Repeat"` if the cookie set by the plug-in exists and the amount of time since the current hit and the time set in the cookie is greater than 30 minutes. This method returns the same value for an entire visit.

This plug-in uses a cookie named `"s_nr[LENGTH]"` where `[LENGTH]` is equal to the `d` argument. The cookie contains a Unix timestamp representing the current time and the current status of the visitor (`"New"` or `"Repeat"`).

## Example Calls

### Example #1

The following code will set s.eVar1 equal to the value of "New" for new visitors and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat();
```

### Example #2

If the visitor comes back to the site anytime from 31 minutes to 30 days since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "Repeat" and will continue to set s.eVar1 equal to the value of "Repeat" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat();
```

### Example #3

If the visitor hasn't been to the site for at least 30 days since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "New" and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat();
```

### Example #4

If the visitor comes back to the site anytime 31 minutes to 365 days (i.e. 1 year) since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "Repeat" and will continue to set s.eVar1 equal to the value of "Repeat" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat(365);
```

### Example #5

If the visitor hasn't been to the site for at least 365 days (i.e. 1 year) since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "New" and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat(365);
```

## Version History

### 2.1 (September 30, 2019)

* Rearrangement of JavaScript logic to reduce plug-in size

### 2.0 (April 16, 2018)

* Recompiled with smaller code size
* Removed the ability to name the cookie to store the visit info. The plug-in now dynamically names the cookie based on the value passed into the `d` argument.
