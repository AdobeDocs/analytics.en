---
title: apl (appendToList)
description: Append values to variables that support multiple values.
feature: Variables
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
---
# Adobe plug-in: apl (appendToList)

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `apl` plug-in allows you to safely add new values to list-delimited variables, such as [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md), and others.

* If the value you want to add doesn't exist in the variable, then the code adds the value to the end of the string.
* If the value you want to add already exists in the variable, then this plug-in does not change the value. This features allows your implementation to avoid duplicate values.
* If the variable you want to add to is empty, then the plug-in sets the variable to the new value.

Adobe recommends using this plug-in if you want to add new values to existing variables that contain a string of delimited values. This plug-in is not necessary if you prefer to concatenate strings for variables containing delimited values.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize APL (Append To List)
1. Save and publish the changes to the rule.-->

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `apl` function uses the following arguments:

* **`lv`** (required, string): The variable that contains a delimited list of items to add a new value to
* **`vta`** (required, string): A comma delimited list of the new value(s) to add to the `lv` argument's value.
* **`d1`** (optional, string): The delimiter used to separate the individual values already contained in the `lv` argument.  Defaults to a comma (`,`) when not set.
* **`d2`** (optional, string): The output delimiter. Defaults to the same value as `d1` when not set.
* **`cc`** (optional, boolean): A flag that indicates if a case-sensitive check is used. If `true`, the duplication check is case-sensitive. If `false` or not set, the duplication check is not case-sensitive. Defaults to `false`.

The `apl` function returns the value of the `lv` argument plus any non-duplicate values in the `vta` argument.

## Examples

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## Version History

### 4.0 (March 19, 2021)

* Added version number as context data.

### 3.2 (September 25, 2019)

* Fixed compatibility issues with `apl` calls that used older versions of the plug-in
* Removed console warnings to reduce size
* Added `inList 2.1`

### 3.1 (April 22, 2018)

* `d2` argument now defaults to the value of the `d1` argument when not set

### 3.0 (April 16, 2018)

* Complete reanalysis/rewrite of plug-in
* Added advanced error checking
* The `vta` argument now accepts multiple values at one time
* Added the `d2` argument to format the return value
* Changed the `cc` argument to a boolean

### 2.5 (February 18, 2016)

* Now uses the `inList` function for comparison processing

### 2.0 (January 26, 2016)

* `d` (Delimiter) argument now optional (defaults to a comma)
* `u` (Case-sensitivity flag) argument now optional (defaults to case-insensitive)
* Regardless of the `u` (Case-sensitivity flag) argument, the plug-in no longer appends a value to a list if the value already exists in the list
