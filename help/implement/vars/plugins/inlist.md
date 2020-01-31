---
title: inList
description: Check whether a value is contained in another character-delimited value
---

# Adobe Experience Cloud Plugin – inList

## Purpose of This Plugin

### What does this plugin do?
The inList plugin is a utility that allows you to check whether a value already exists within either a delimited list of values or a JavaScript array object.

### Why should I use this plugin?
You should use the inList plugin in conjunction with other plugins, such as the appendToList plugin, or if you want to simply check (within an if statement) whether a value already exists within a delimited list of values.

### Why shouldn't I use this plugin?
If you are looking for only a partial match between a specific value and a delimited list of values, then then you have no need for this plugin and can use a simple concatenation operator instead.
For example, if ...
```javascript
s.events="event1,event25,event3";
```
...and you want to find out if 'event2' is contained within s.events (without an exact match), then the following if statement...
```javascript
if(s.events.indexOf("event2") >- 1)
```
...will suffice, as it will return a positive number and thus indicate the fact that event2 is contained within s.events (as a "partial match" with event25)

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the inList plugin

## How to Deploy

You may use one of the following three methods to deploy the inList plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
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
	* Action Type: Initialize inList
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the inList plugin (via JavaScript), be sure to pass in the following arguments:

* **lv** (required, string or array): A delimited list of values or a JavaScript array object that might contain the lookup value specified in the vtc argument
* **vtc** (required, string): the value to check for within the values specified in the lv argument
* **d** (optional, string): The delimiter used to separate out the individual values contained in the lv argument.  Defaults to a comma (i.e. ",") when not set
* **cc** (optional, boolean): A flag that determines whether a case-sensitive check will be used to determine whether the vtc argument value already exists in the lv argument value
	* If cc equals true, then a case-sensitive check will be made for the value (vtc argument) you want to look for within the lv argument
	* If cc is not set (or is equal to false), then a case-insensitive check will be made for the value you want to look for within the lv argument

## Returns
The inList plugin returns "true" (boolean) if it finds a match between the vtc argument's value and any of the values contained within the lv argument.  Otherwise, the plugin returns "false" (boolean)

## Cookies
The inList plugin does not set or use any cookies.

## Example Calls

### Example #1
If...
```javascript
s.events="event22,event24";
```
...and the following code runs...
```javascript
if(s.inList(s.events,"event22"))
```
...the conditional if statement will be true
### Example #2
If...
```javascript
s.events="event22,event24";
```
...and the following code runs...
```javascript
if(s.inList(s.events,"event2"))
```
...the conditional if statement will be false because the inList call did not make an exact match between event2 and either of the delimited-values in s.events

### Example #3
If...
```javascript
s.events="event22,event24";
```
...and the following code runs...
```javascript
if(!s.inList(s.events,"event23"))
```
...the conditional if statement will be true because the inList call did not make an exact match between event23 and either of the delimited-values in s.events (notice the "NOT" operator at the beginning of the inList variable call).

### Example #4
If...
```javascript
s.events = "event22,event23";
```
...and the following code runs...
```javascript
if(s.inList(s.events,"EVenT23","",1))
```
...the conditional if statement will be false.  Although this example isn't practical, it demonstrates the need to use caution when using the case sensitive flag.

### Example #5
If...
```javascript
s.linkTrackVars = "events,eVar1";
```
...and the following code runs...
```javascript
if(s.inList(s.linkTrackVars,"eVar1","|"))
```
...the conditional if statement will be false.  The value of the d argument passed into the call (i.e. "|") assumes that the individual values in s.linkTrackVars are delimited by a pipe character, whereas in reality, the values are delimited by a comma.  In this case, the plugin will try to make a match between the whole value of s.linkTrackVars (i.e. "events,eVar1") and the value to look for (i.e. "eVar1").

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.inList=function(lv,vtc,d,cc)
```
...to this:
```javascript
[objectname].inList=function(lv,vtc,d,cc)
```

## Version History

### v2.1 (2019-09-26)
* Added the option for the cc argument to not be a boolean (e.g. "1" is a valid case check value)
### v2.0 (2018-04-17)
* Point Release (recompiled, smaller code size)
### v1.01 (2017-09-27)
* JavaScript code optimizations to reduce size (no functionality changes)
### v1.0 (2009)
* Initial Release


