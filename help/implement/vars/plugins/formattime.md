---
title: formatTime
description: Convert a number of seconds into its equivalent in minutes, hours, etc.
---

# Adobe plug-in: formatTime

## Plugin Purpose

### What does this plug-in do?

The formatTime plug-in allows you to take a specified number of seconds and present them in a bucketed format, rounded to a benchmark value that you specify

### Why should I use this plug-in?

You should use the formatTime plug-in if you want to capture a value in seconds and convert it into a more rounded format (i.e. minutes, hours, days, etc.)

### Why shouldn't I use this plug-in?

You won't need to use the formatTime plug-in if you don't need to capture any second-based values or convert those values into a time-rounded format

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) and the inList Plugin (included in the Code to Deploy section below) to run the formatTime plug-in

## How to Deploy

You may use one of the following three methods to deploy the formatTime plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires AppMeasurement and inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the formatTime plug-in (via JavaScript), be sure to pass in the following arguments:

* **ns** (required, integer): The number of seconds to convert/format
* **tf** (optional, string): The type of format to return the seconds in; defaults to seconds
	* Set equal to "d" if you want the time to be formatted into days (rounded to the closest 1/4 day benchmark by default)
	* Set equal to "h" if you want the time to be formatted into hours (rounded to the closest 1/4 hour benchmark by default)
	* Set equal to "m" if you want the time to be formatted into minutes (rounded to the closest 1/2-minute benchmark by default)
	* Set equal to "s" if you want the time to be formatted into seconds (rounded to the closest 5 second benchmark by default)
* **bml** (optional, number): The value of this argument will specify the length of the rounding benchmarks per the value of the tf argument; defaults to the values specified in the tf arguments above

## Returns

The formatTime plug-in will return the number of seconds formatted using the unit you specify in the tf argument.
When the "tf" argument is not set:
* Anything less than a minute will be rounded to the closest 5 second benchmark (e.g. 10 seconds, 15 seconds, etc.)
* Anything between a minute and an hour will be rounded to the closest 1/2-minute benchmark (e.g. 30.5 minutes, 31 minutes, etc.)
* Anything between an hour and a day will be rounded to the closest quarter-hour benchmark (e.g. 2.25 hours, 3.5 hours, etc.)
* Anything greater than a day will be rounded to the closest day benchmark (e.g. 1 days, 3 days, 9 days, etc.)
Otherwise the number of seconds will be automatically formatted per the settings in the "tf" and "bml" arguments

## Cookies

The formatTime plug-in does not create or use any cookies

## Example Calls

### Example #1

The following code...

```js
s.eVar1 = s.formatTime(38242);
```
...will set s.eVar1 equal to "10.5 hours"
The argument passed in – 38242 seconds – is equal to 10 hours, 37 minutes, and 22 seconds.  Since the tf argument is not set in this call and the number of seconds passed in is between an hour and a day, the plug-in will return the number of second converted to the closest quarter-hour benchmark.

### Example #2

The following code...

```js
s.eVar1 = s.formatTime(38250);
```
...will set s.eVar1 equal to "10.75 hours"
The argument passed in – 38250 seconds – is equal to 10 hours, 37 minutes, and 30 seconds.  Rounding the number of seconds passed in to the closest quarter-hour benchmark in this case will set the final value to 10.75 hours

### Example #3
The following code...

```js
s.eVar1 = s.formatTime(38242, "m");
```
...will set s.eVar1 equal to "637.5 minutes"
In this case, the "m" argument forces the plug-in to convert the seconds to the closest ½-minute benchmark

### Example #4
The following code...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```
...will set s.eVar1 equal to "640 minutes"
The tf argument value ("m") forces the plug-in to convert the seconds into minutes, but the bml argument value (20) also forces the plug-in to round the minute conversion to the closest 20-minute benchmark.
### Example #5
The following code...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```
...will set s.eVar1 equal to "126 seconds", which is the closest 2-second benchmark to 125 seconds
### Example #6
The following code...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```
...will set s.eVar1 equal to "3 minutes", which is the closest 3-minute benchmark to 125 seconds
### Example #7
The following code...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```
...will set s.eVar1 equal to "2.4 minutes", which is the closest 2/5ths-minute benchmark (e.g. .4 = 2/5)  to 145 seconds

## Version History

### 1.1 (2018-05-21)

* Added the bml (benchmarkLength parameter) to allow for more flexibility in the rounding

### 1.0 (2018-04-15)

* Initial Release