---
title: rfl
description: Remove a specific value from a separate character-delimited value
---

# Adobe Experience Cloud Plugin – rfl (Remove From List)

## Purpose of This Plugin

### What does this plugin do?
The rfl plugin is a JavaScript function that allows you to "safely" remove values from list-delimited variables (e.g. s.events, s.linkTrackVars, listVars, etc.).

### Why should I use this plugin?
You should use the rfl plugin if you want to remove a specific value from a variable that already contains multiple delimited values.  This plugin utility is especially useful for removing specific events (contained in s.events) that use serialization and/or integer/currency-based syntax.
* If the value you want to remove exists in the variable that you want to remove the value from, then the plugin will keep everything in the variable except the value to remove.  
* If the value you want to remove doesn't exist in the variable, then the code will simply keep the original variable value as is.

You can use the plugin if you want to also change the delimiter that a variable uses to separate out the individual values contained within it. 

### Why shouldn't I use this plugin?
If you have no need to remove a specific value from a variable containing a delimited list of values, then you have no need for this plugin.   

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the rfl plugin.

## How to Deploy

You may use one of the following three methods to deploy the rfl plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation. 

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 (Requires AppMeasurement) */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
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
	* Action Type: Initialize rfl
* Save and publish the changes to the rule
	
## How to Run the Plugin
When calling the rfl plugin (via JavaScript), be sure to pass in the following arguments:

* **lv** (required, string): A variable (or string) that is equal to a list of delimited values 
* **vr** (required, string): A single value that will be removed from the lv argument's delimited list.  Trying to remove multiple values during a single rfl call is not recommended (see examples #12/#13 below)
* **d1** (optional, string): The delimiter that separates out the individual values contained in the lv argument.  Defaults to a comma (i.e. ",") when not set
* **d2** (optional, string): The delimiter that will separate the remaining (i.e. final) list of values after the value contained in the vr argument has been removed from the lv argument's value.   Defaults to the same value as the d1 argument
* **df** (optional, boolean): A "flag" that, when set equal to true, will force the plugin to remove only duplicate instances of the vr argument value from the lv argument rather than all instances.  Defaults to false when not set

## Returns
The rfl plugin returns the value of the lv argument but without any instances (or duplicate instances) of the value specified in the vr argument

## Cookies
The rfl plugin by itself does not create or use any cookies.  

## Example Calls

### Example #1
If...
```javascript
s.events = "event22,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event24");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event25";
```

### Example #2
If...
```javascript
s.events = "event22,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event26");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event24,event25";
```
In this example, the rfl call made no changes to s.events since s.events didn't contain "event26"


### Example #3
If...
```javascript
s.events = "event22,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events);
```
...the final value of s.events will be:
```javascript
s.events = "";
```
If either the lv argument or vr argument are blank in an s.rfl call, then the plugin will return nothing

### Example #4
If...
```javascript
s.prop4 = "hello|people|today";
```
...and the following code runs...
```javascript
s.eVar5 = s.rfl(s.prop4,"people","|");
```
...the final value of s.prop4 will still be...
```javascript
s.prop4 = "hello|people|today";
```
...but the final value of s.eVar5 will be:
```javascript
s.eVar5 = "hello|today";
```
Keep in mind that the plugin only returns a value; it does not actually "reset" the variable passed in through the lv argument.


### Example #5
If...
```javascript
s.prop4 = "hello|people|today";
```
...and the following code runs...
```javascript
s.prop4 = s.rfl(s.prop4,"people");
```
...the final value of s.prop4 will still be...
```javascript
s.prop4 = "hello|people|today";
```
Be sure to set the d1 argument in cases where the lv argument value contains a different delimiter than the default value (i.e. comma).

### Example #6
If...
```javascript
s.events = "event22,event23,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"EVenT23");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event23,event25";
```
Although this example isn't practical, it demonstrates the need to pass in case-sensitive values.


### Example #7
If...
```javascript
s.events = "event22,event23:12345,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event25";
```

### Example #8
If...
```javascript
s.events = "event22,event23:12345,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23:12345");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event23:12345,event25";
```
When you need to remove an event that uses serialization and/or numeric/currency syntax, you should specify only the event itself (i.e. without the serialization/numeric/currency values) in the s.rfl call.  


### Example #9
If...
```javascript
s.events = "event22,event23,event23,event23,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event24,event25");
```

### Example #10
If...
```javascript
s.events = "event22,event23,event23,event23,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23", "", "",true);
```
...the final value of s.events will be:
```javascript
s.events = "event22,event23,event24,event25");
```

### Example #11
If...
```javascript
s.events = "event22,event23,event23,event23,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23", "", "|",true);
```
...the final value of s.events will be:
```javascript
s.events = "event22|event23|event24|event25");
```

### Example #12
If...
```javascript
s.events = "event22,event23,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23,event24");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event23,event24,event25";
```
Setting multiple values in the vr argument is not supported. The rfl logic in the above example would first split out the values in the lv argument (i.e. s.events) then try to match each delimited value to the complete vr argument value (i.e. "event23,event24").  

### Example #13
If...
```javascript
s.events = "event22,event23,event24,event25";
```
...and the following code runs...
```javascript
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```
...the final value of s.events will be:
```javascript
s.events = "event22,event25");
```
Each value to be removed from the list should be contained within its own s.rfl call.


### Example #14
If...
```javascript
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```
...and the following code runs...
```javascript
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```
...the final value of s.linkTrackVars will be:
```javascript
s.linkTrackVars = "events,eVar1,eVar3";
```
The last three arguments (i.e. ",",",",false) at the end of this s.rfl call are not necessary but are also not "hurting anything" by being there since they match the default settings.

### Example #15
If...
```javascript
s.events = "event22,event23,event24";
```
...and the following code runs...
```javascript
s.rfl(s.events,"event23");
```
...the final value of s.events will still be:
```javascript
s.events = "event22,event23,event24";
```
Again, keep in mind the plugin only returns a value; it does not actually "reset" the variable passed in through the lv argument.


## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.rfl=function(l,v,d1,d2,df)
```
...to this:
```javascript
[objectname].rfl=function(l,v,d1,d2,df)
```

## Version History

### 2.01 (2019-09-17)
* Minor bug fix for the default delimiter value
### 2.0 (2018-04-16)
* Point release (recompiled, smaller code size)
* Removed the need for the join plugin
### 1.0 (2016-07-18)
* Initial release




 





