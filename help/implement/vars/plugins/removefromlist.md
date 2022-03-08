---
title: rfl
description: Remove a specific value from a character-delimited string.
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
---
# Adobe plug-in: rfl (Remove From List)

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `rfl` plug-in allows you to "safely" remove values from delimited strings, such as [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md), and others. This plug-in is useful if you want to remove specific values from a delimited string without worrying about delimiters. Several other plug-ins depend on this code to run correctly. This plug-in is not necessary if you have no need to run a specific function on more than one Analytics variable at a time, or if you're not using any dependent plug-ins.

The plug-in uses the following logic:

* If the value you want to remove exists, the plug-in keeps everything in the variable except the value to remove.
* If the value you want to remove doesn't exist, the plug-in keeps the original string as-is.

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
    * Action Type: Initialize RFP (Remove From List)
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `rfl` function uses the following arguments:

* **`lv`** (required, string): A variable (or string) that containing a list of delimited values
* **`vr`** (required, string): The value you want removed from the `lv` argument. Adobe advises against removing multiple values during a single `rfl` call.
* **`d1`** (optional, string): The delimiter that the `lv` argument uses. Defaults to a comma (`,`).
* **`d2`** (optional, string): The delimiter that you want the return string to use. Defaults to the same value as the `d1` argument.
* **`df`** (optional, boolean): If `true`, forces only duplicate instances of the `vr` argument from the `lv` argument instead of all instances. Defaults to `false` when not set.

Calling this function returns a modified string containing the `lv` argument but without any instances (or duplicate instances) of the value specified in the `vr` argument.

## Example Calls

### Example #1

If...

```js
s.events = "event22,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event24");
```

...the final value of s.events will be:

```js
s.events = "event22,event25";
```

### Example #2

If...

```js
s.events = "event22,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event26");
```

...the final value of s.events will be:

```js
s.events = "event22,event24,event25";
```

In this example, the rfl call made no changes to s.events since s.events didn't contain "event26"

### Example #3

If...

```js
s.events = "event22,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events);
```

...the final value of s.events will be:

```js
s.events = "";
```

If either the `lv` argument or `vr` argument are blank in an `rfl` call, then the plug-in returns nothing.

### Example #4

If...

```js
s.prop4 = "hello|people|today";
```

...and the following code runs...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

...the final value of s.prop4 will still be...

```js
s.prop4 = "hello|people|today";
```

...but the final value of s.eVar5 will be:

```js
s.eVar5 = "hello|today";
```

Keep in mind that the plug-in only returns a value; it does not actually "reset" the variable passed in through the `lv` argument.

### Example #5

If...

```js
s.prop4 = "hello|people|today";
```

...and the following code runs...

```js
s.prop4 = rfl(s.prop4,"people");
```

...the final value of s.prop4 will still be...

```js
s.prop4 = "hello|people|today";
```

Be sure to set the `d1` argument in cases where the `lv` argument value contains a different delimiter than the default value (i.e. comma).

### Example #6

If...

```js
s.events = "event22,event23,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"EVenT23");
```

...the final value of s.events will be:

```js
s.events = "event22,event23,event25";
```

Although this example isn't practical, it demonstrates the need to pass in case-sensitive values.

### Example #7

If...

```js
s.events = "event22,event23:12345,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23");
```

...the final value of s.events will be:

```js
s.events = "event22,event25";
```

### Example #8

If...

```js
s.events = "event22,event23:12345,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23:12345");
```

...the final value of s.events will be:

```js
s.events = "event22,event23:12345,event25";
```

When you need to remove an event that uses serialization and/or numeric/currency syntax, you should specify only the event itself (i.e. without the serialization/numeric/currency values) in the `rfl` call.  

### Example #9

If...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23");
```

...the final value of s.events will be:

```js
s.events = "event22,event24,event25");
```

### Example #10

If...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23", "", "",true);
```

...the final value of s.events will be:

```js
s.events = "event22,event23,event24,event25");
```

### Example #11

If...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23", "", "|",true);
```

...the final value of s.events will be:

```js
s.events = "event22|event23|event24|event25");
```

### Example #12

If...

```js
s.events = "event22,event23,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23,event24");
```

...the final value of s.events will be:

```js
s.events = "event22,event23,event24,event25";
```

Setting multiple values in the `vr` argument is not supported. The `rfl` logic in the above example would first split out the values in the `lv` argument (i.e. s.events) then try to match each delimited value to the complete `vr` argument value (i.e. `"event23,event24"`).  

### Example #13

If...

```js
s.events = "event22,event23,event24,event25";
```

...and the following code runs...

```js
s.events = rfl(s.events,"event23");
s.events = rfl(s.events,"event24");
```

...the final value of s.events will be:

```js
s.events = "event22,event25");
```

Each value to be removed from the list should be contained within its own `rfl` call.

### Example #14

If...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...and the following code runs...

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...the final value of s.linkTrackVars will be:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

The last three arguments (i.e. ",",",",false) at the end of this `rfl` call are not necessary but are also not "hurting anything" by being there since they match the default settings.

### Example #15

If...

```js
s.events = "event22,event23,event24";
```

...and the following code runs...

```js
rfl(s.events,"event23");
```

...the final value of s.events will still be:

```js
s.events = "event22,event23,event24";
```

Again, keep in mind the plug-in only returns a value; it does not actually "reset" the variable passed in through the `lv` argument.

## Version History

### 2.1 (March 19, 2021)

* Added version number as context data.

### 2.01 (September 17, 2019)

* Minor bug fix for the default delimiter value

### 2.0 (April 16, 2018)

* Point release (recompiled, smaller code size).
* Removed the need for the `join` plug-in.

### 1.0 (July 18, 2016)

* Initial release.
