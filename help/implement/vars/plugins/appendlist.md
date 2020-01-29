---
description: The apl (appendToList) plugin allows you to "safely" add new values to list-delimited variables (e.g. events, linkTrackVars, listVars, etc.).
keywords: Analytics Implementation
subtopic: Plug-ins
title: appendList
topic: Developer and implementation
uuid: e923c86c-eaa6-4e17-a3a4-0e08af886674
---

# apl plugin

## Plugin Description

The apl (appendToList) plugin allows you to "safely" add new values to list-delimited variables (e.g. events, linkTrackVars, list variables, etc.).

### When should I use this plugin?

You should use the apl plugin if you want to add a new value to an already-existing, list-delimited variable.  

* If the value you want to add already exists in the list-delimited variable, then the code will not add another instance of the value to the end of the variable. 
* If the value you want to add doesn't already exist in the variable, then the code will add the value to the end of the variable.
* If the list-delimited variable that you want to add the new value to hasn't been set yet (i.e. the variable is null/undefined/blank), then the code will simply set the variable equal to the new value 

Using the apl plugin will prevent potential duplicate values from being added to a list.  For example, assume the s.events variable is set as follows:
```js
s.events = "event1,event2";
```
If you use the apl plugin to try and add event1 to s.events, the logic would not add it since s.events already contains "event1".

### When shouldn't I use this plugin?

If you don't care whether a new value you want to add already exists in a list-delimited variable, then you have no need for this plugin and can use a simple concatenation operator instead. 

For example...
```js
s.events = s.events + ",event1";
```
...will do a perfectly fine job of adding event1 to the end of s.events regardless of whether event1 already exists in s.events.

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) and the inList v2.0 plugin (included in the Code to Deploy section below) to run the apl plugin

## How to Implement

* Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (requires AppMeasurement and inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```
**NOTE:** Adding the comments/version numbers of the code to the AppMeasurement file will help Adobe Support with troubleshooting any potential implementation issues.
* Run the apl plugin as needed within the doPlugins function (see example calls below)

## Arguments to Pass In

* **lv** ("sort-of" required, string): A JavaScript variable that contains a delimited list of items to add a new value to
* **vta** (required, string): A comma delimited list of the new value(s) to add to the lv argument's value.
* **d1** (optional, string): The delimiter used to separate out the individual values already contained in the lv argument.  Defaults to a comma (i.e. ",") when not set
* **d2** (optional, string): The delimiter that the plugin will use to join the values in the final list to be returned.  Defaults to the same value as d1 (i.e. a comma or otherwise) when not set
* **cc** (optional, boolean): A flag that says whether a case-sensitive check will be used to determine whether the vta argument value already exists in the lv argument value, defaults to false
  * If the cc argument equals true, then a case-sensitive check will be made between the new value(s) you want to add (i.e. the vta argument) and each value contained in the lv argument
  * If the cc argument is not set (or is not set equal to true), then a case-insensitive check will be made between the new value(s) you want to add (i.e. the vta argument) and each value contained in the lv argument

## Returns

The apl plugin returns the value of the lv argument plus those values specified in the vta argument that weren't previously contained in the lv argument
 
## Cookies

The apl plugin does not set any cookies

## Example Calls

### Example #1
If…
```js
s.events = "event22,event24";
```
…and the following code runs…
```js
s.events = s.apl(s.events, "event23");
```
… the final value of s.events will be:
```js
s.events = "event22,event24,event23";
```

### Example #2
If…
```js
s.events = "event22,event23";
```
…and the following code runs…
```js
s.events = s.apl(s.events, "event23");
```
… the final value of s.events will still be:
```js
s.events = "event22,event23";
```
In this example, the apl call made no changes to s.events since s.events already contained "event23"

### Example #3
If…
```js
s.events = ""; //blank value
```
…and the following code runs…
```js
s.events = s.apl(s.events, "event23");
```
… the final value of s.events will be…
```js
s.events = "event23";
```

### Example #4
If…
```js
s.prop4 = "hello|people";
```
…and the following code runs…
```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```
… the final value of s.prop4 will still be…
```js
s.prop4 = "hello|people";
```
…but the final value of s.eVar5 will be
```js
s.eVar5 = "hello|people|today";
```
Keep in mind that the plugin only returns a value; it does not necessarily "reset" the variable passed in through the lv argument.

### Example #5
If…
```js
s.prop4 = "hello|people";
```
…and the following code runs…
```js
s.prop4 = s.apl(s.prop4, "today");
```
… the final value of s.prop4 will be…
```js
s.prop4 = "hello|people,today";
```
Be sure to keep the delimiter consistent between what's in the lv argument's value and what's in the d1/d2 arguments

### Example #6
If…
```js
s.events = "event22,event23";
```
…and the following code runs…
```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```
… the final value of s.events will be:
```js
s.events = "event22,event23,EVentT23";
```
Although this example isn't practical, it demonstrates the need to use caution when using the case sensitive flag. 

### Example #7
If…
```js
s.events = "event22,event23";
```
…and the following code runs…
```js
s.events = s.apl(s.events, "event23,event24,event25");
```
… the final value of s.events will be:
```js
s.events = "event22,event23,event24,event25");
```
The plugin will not add "event23" to s.events because it already exists in s.events.  However, it will add both event24 and event25 to s.events because neither were previously contained in s.events.

### Example #8
If…
```js
s.linkTrackVars = "events,eVar1";
```
…and the following code runs…
```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```
… the final value of s.linkTrackVars will be:
```js
s.linkTrackVars = "events,eVar1,campaign";
```
The last three arguments (i.e. ",", ",", false) at the end of this apl call are not necessary but are also not "hurting anything" by being set since they match the default argument values.

### Example #9
If…
```js
s.events = "event22,event24";
```
…and the following code runs…
```js
s.apl(s.events, "event23");
```
… the final value of s.events will still be:
```js
s.events = "event22,event24";
```
Running the plugin all by itself (without assigning the return value to a variable) does not actually "reset" the variable passed in through the lv argument.

### Example #10
If…
```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```
…and the following code runs…
```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```
… the final value of s.list2 will be:
```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```
Since the two delimiter arguments are different, the value passed in will be delimited by the first delimiter argument (“|”) and then joined together by the second delimiter argument (“-“)

## Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this…
```js
s.apl=function(lv,vta,d1,d2,cc)
```
…to this:
```js
[objectname].apl=function(lv,vta,d1,d2,cc)
```
Be sure to also change the inList plugin from this…
```js
s.inList=function(lv,vtc,d,cc)
```
…to this:
```js
[objectname].inList=function(lv,vtc,d,cc)
```

## Version History

### 3.2 (2019-09-25)
* Fixed compatibility issues with apl calls that used older versions of the plugin
* Removed console warnings to reduce size - use documentation for troubleshooting
* Added inList 2.1

### 3.1 (2018-04-22)
* d2 argument now defaults to the value of the d1 argument when not set

### 3.0 (2018-04-16)
* Complete reanalysis/rewrite of plugin
* Added advanced error checking, updated documentation with required vs. optional arguments
* The value to add (vta) argument now accepts multiple values at one time
* Added the d2 argument to format the return value
* Changed the cc argument to a boolean

### 2.5 (2016-02-18)
* Now uses the inList plugin utility for its comparison processing

### 2.0 (2016-01-26)
* d (Delimiter) argument now optional (defaults to a comma)
* u (Case-sensitivity flag) argument now optional (defaults to case-insensitive) 
* Regardless of the u (Case-sensivity flag) argument setting, the apl plugin will no longer append a value to a list if the value already exists in the list (see the "Why shouldn't I use this plugin?" section above)