---
title: inList
description: Check if a value is contained in another character-delimited value.
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
---
# Adobe plug-in: inList

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `inList` plug-in allows you to check if a value already exists within either a delimited string or a JavaScript array object. Several other plug-ins depend on the `inList` plug-in to work. This plug-in provides a distinct advantage over the JavaScript method `indexOf()` where you it does not match partial strings. For example, if you used this plug-in to check for `"event2"`, it won't match with a string containing `"event25"`. This plug-in is not necessary if you don't need to check for values in delimited strings or arrays, or if you want to use your own `indexOf()` logic.

## Install the plug-in using tags in Adobe Experience Platform

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize inList
1. Save and publish the changes to the rule.

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `inList` method uses the following arguments:

* **`lv`** (required, string or array): A delimited list of values or a JavaScript array object to search
* **`vtc`** (required, string): The value to search for
* **`d`** (optional, string): The delimiter used to separate individual values in the `lv` argument. Defaults to a comma (`,`) when not set.
* **`cc`** (optional, boolean): If set to `true`, a case-sensitive check is made. If set to `false` or omitted, then a case-insensitive check is made. Defaults to `false`.

Calling this method returns `true` if it finds a match, and `false` if it does not find a match.

## Example Calls

### Example #1

If...

```js
s.events="event22,event24";
```

...and the following code runs...

```js
if(s.inList(s.events,"event22"))
```

...the conditional if statement will be true

### Example #2

If...

```js
s.events="event22,event24";
```

...and the following code runs...

```js
if(s.inList(s.events,"event2"))
```

...the conditional if statement will be false because the inList call did not make an exact match between event2 and either of the delimited-values in s.events

### Example #3

If...

```js
s.events="event22,event24";
```

...and the following code runs...

```js
if(!s.inList(s.events,"event23"))
```

...the conditional if statement will be true because the inList call did not make an exact match between event23 and either of the delimited-values in s.events (notice the "NOT" operator at the beginning of the inList variable call).

### Example #4

If...

```js
s.events = "event22,event23";
```

...and the following code runs...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...the conditional if statement will be false.  Although this example isn't practical, it demonstrates the need to use caution when using the case sensitive flag.

### Example #5

If...

```js
s.linkTrackVars = "events,eVar1";
```

...and the following code runs...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...the conditional if statement will be false.  The value of the d argument passed into the call (i.e. "|") assumes that the individual values in s.linkTrackVars are delimited by a pipe character, whereas in reality, the values are delimited by a comma.  In this case, the plug-in will try to make a match between the whole value of s.linkTrackVars (i.e. "events,eVar1") and the value to look for (i.e. "eVar1").

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### v2.1 (September 26, 2019)

* Added the option for the `cc` argument to not be a boolean. For example, `1` is a valid case check value.

### v2.0 (April 17, 2018)

* Point release (recompiled, smaller code size).

### v1.01 (September 27, 2017)

* Optimized code to reduce size

### v1.0 (2009)

* Initial release.
