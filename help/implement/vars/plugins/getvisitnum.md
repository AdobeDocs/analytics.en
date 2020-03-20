---
title: getVisitNum
description: Track a visitor's current visit number.
---

# Adobe plug-in: getVisitNum

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getVisitNum` plug-in returns the visit number for all visitors that come to the site within the desired number of days. Analysis Workspace offers a 'Visit Number' dimension that provides similar functionality. Adobe recommends using this plug-in if you want more control over how visit number is incremented. This plug-in is unnecessary if the built-in 'Visit Number' dimension in Analysis Workspace is sufficient for your reporting needs.

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
    * Action Type: Initialize getVisitNum
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

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getVisitNum` method uses the following arguments:

* **`rp`** (optional, integer OR string): The number of days before the visit number counter resets.  Defaults to `365` when not set.
  * When this argument is `"w"`, the counter resets at the end of the week (this Saturday at 11:59 PM)
  * When this argument is `"m"`, the counter resets at the end of the month (the last day of this month)
  * When this argument is `"y"`, the counter resets at the end of the year (December 31st)
* **`erp`** (optional, boolean): When the `rp` argument is a number, this argument determines if the visit number expiration should be extended. If set to `true`, subsequent hits to your site resets the visit number counter. If set to `false`, subsequent hits to your site do not extend when the visit number counter resets. Defaults to `true`. This argument is not valid when the `rp` argument is a string.

The visit number increment whenever the visitor returns to your site after 30 minutes of inactivity. Calling this method returns an integer that represents the visitor's current visit number.

This plug-in sets a first-party cookie called `"s_vnc[LENGTH]"` where `[LENGTH]` is the value passed into the `rp` argument. For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. The value of the cookie is a combination of a Unix timestamp that represents when the visit counter resets, such as end of the week, end of the month, or after 365 days of inactivity. It also contains the current visit number. This plug-in sets another cookie named `"s_ivc"` that is set to `true` and expires after 30 minutes of inactivity.

## Example Calls

### Example #1

For a visitor that hasn't been to the site within the last 365 days, the following code will set s.prop1 equal to the value of 1:

```js
s.prop1=s.getVisitNum();
```

### Example #2

For a visitor that returns to the site within 364 days after his/her first visit, the following code will set s.prop1 equal to 2:

```js
s.prop1=s.getVisitNum(365);
```

If this visitor returns to the site within 364 days after his/her second visit, the following code will set s.prop1 equal to 3:

```js
s.prop1=s.getVisitNum(365);
```

### Example #3

For a visitor that returns to the site within 179 days after his/her first visit, the following code will set s.prop1 equal to 2:

```js
s.prop1=s.getVisitNum(180,false);
```

However, if this visitor returns to the site 1 or more days after his/her second visit, the following code will set s.prop1 equal to 1:

```js
s.prop1=s.getVisitNum(180,false);
```

When the second argument in the call is equal to false, the routine that determines when the visit number should be "reset" to 1 will do so "x" number of days – in this example, 365 days – after the visitor's first visit to the site.

When the second argument is equal to true (or not set at all), the plug-in will reset the visit number to 1 only after "x" number of days – again, in this example, 365 days – of visitor inactivity.

### Example #4

For all visitors that come to the site for the first time during the current week – beginning on Sunday - the following code will set s.prop1 equal to 1:

```js
s.prop1=s.getVisitNum("w");
```

### Example #5

For all visitors that come to the site for the first time during the current month – beginning on the first day of each month - the following code will set s.prop1 equal to 1:

```js
s.prop1=s.getVisitNum("m");
```

Keep in mind that the getVisitNum plug-in does not consider retail-based calendars (i.e. 4-5-4, 4-4-5, etc.)

### Example #6

For all visitors that come to the site for the first time during the current year – beginning on January 1 - the following code will set s.prop1 equal to 1:

```js
s.prop1=s.getVisitNum("y");
```

### Example #7

If you wish to track a visitor's visit number for the week, a visitor's visit number for the month, and a visitor's visit number for the year – all within different Analytics variables – you should use code that resembles the following:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

In this case, the plug-in will create three different cookies – one for each of the different time periods – to keep track of the individual visit number per time period.

## Version History

### 4.11 (September 30, 2019)

* Fixed an issue where the `erp` argument was explicitly set to `false`.

### 4.1 (May 21, 2018)

* Updated the `endOfDatePeriod` plug-in to v1.1.

### 4.0 (April 17, 2018)

* Point release (recompiled, smaller code size).
* Removed cookie arguments as the plug-in now dynamically generates cookies based on the `rp` argument)

### 3.0 (June 5, 2016)

* Complete overhaul
* Combined all previous solutions available in various versions of the `getVisitNum` plug-in.
