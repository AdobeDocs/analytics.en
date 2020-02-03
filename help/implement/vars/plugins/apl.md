---
title: apl (appendToList)
description: Append values to variables that support multiple values.
---

# Adobe plug-in: apl (appendToList)

The `apl` plug-in allows you to safely add new values to list-delimited variables, such as `events`, `linkTrackVars`, list vars, and others.

* If the value you want to add doesn't exist in the variable, then the code adds the value to the end of the string.
* If the value you want to add already exists in the variable, then this plug-in does not change the value. This features allows your implementation to avoid duplicate values.
* If the variable you want to add to is empty, then the plug-in sets the variable to the new value.

Adobe recommends using this plug-in if you want to add new values to existing variables that contain a string of delimited values. This plug-in is not necessary if you prefer to concatenate strings for variables containing delimited values.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install (and publish) the 'Common Analytics Plugins' extension
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `apl` method uses the following arguments:

* **`lv`** (required, string): The variable that contains a delimited list of items to add a new value to
* **`vta`** (required, string): A comma delimited list of the new value(s) to add to the `lv` argument's value.
* **`d1`** (optional, string): The delimiter used to separate the individual values already contained in the `lv` argument.  Defaults to a comma (`,`) when not set.
* **`d2`** (optional, string): The output delimiter. Defaults to the same value as `d1` when not set.
* **`cc`** (optional, boolean): A flag that indicates if a case-sensitive check is used. If `true`, the duplication check is case-sensitive. If `false` or not set, the duplication check is not case-sensitive. Defaults to `false`.

The `apl` method returns the value of the `lv` argument plus any non-duplicate values in the `vta` argument.

## Example Calls

### Example #1

If...

```js
s.events = "event22,event24";
```

...and the following code runs...

```js
s.events = s.apl(s.events, "event23");
```

... the final value of s.events will be:

```js
s.events = "event22,event24,event23";
```

### Example #2

If...

```js
s.events = "event22,event23";
```

...and the following code runs...

```js
s.events = s.apl(s.events, "event23");
```

... the final value of s.events will still be:

```js
s.events = "event22,event23";
```

In this example, the apl call made no changes to s.events since s.events already contained "event23"

### Example #3

If...

```js
s.events = ""; //blank value
```

...and the following code runs...

```js
s.events = s.apl(s.events, "event23");
```

... the final value of s.events will be...

```js
s.events = "event23";
```

### Example #4

If...

```js
s.prop4 = "hello|people";
```

...and the following code runs...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... the final value of s.prop4 will still be...

```js
s.prop4 = "hello|people";
```

...but the final value of s.eVar5 will be

```js
s.eVar5 = "hello|people|today";
```

Keep in mind that the plug-in only returns a value; it does not necessarily "reset" the variable passed in through the lv argument.

### Example #5

If...

```js
s.prop4 = "hello|people";
```

...and the following code runs...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... the final value of s.prop4 will be...

```js
s.prop4 = "hello|people,today";
```

Be sure to keep the delimiter consistent between what's in the lv argument's value and what's in the d1/d2 arguments

### Example #6

If...

```js
s.events = "event22,event23";
```

...and the following code runs...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... the final value of s.events will be:

```js
s.events = "event22,event23,EVentT23";
```

Although this example isn't practical, it demonstrates the need to use caution when using the case sensitive flag.

### Example #7

If...

```js
s.events = "event22,event23";
```

...and the following code runs...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... the final value of s.events will be:

```js
s.events = "event22,event23,event24,event25");
```

The plug-in will not add "event23" to s.events because it already exists in s.events.  However, it will add both event24 and event25 to s.events because neither were previously contained in s.events.

### Example #8

If...

```js
s.linkTrackVars = "events,eVar1";
```

...and the following code runs...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... the final value of s.linkTrackVars will be:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

The last three arguments (i.e. ",", ",", false) at the end of this apl call are not necessary but are also not "hurting anything" by being set since they match the default argument values.

### Example #9

If...

```js
s.events = "event22,event24";
```

...and the following code runs...

```js
s.apl(s.events, "event23");
```

... the final value of s.events will still be:

```js
s.events = "event22,event24";
```

Running the plug-in all by itself (without assigning the return value to a variable) does not actually "reset" the variable passed in through the lv argument.

### Example #10

If...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...and the following code runs...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... the final value of s.list2 will be:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Since the two delimiter arguments are different, the value passed in will be delimited by the first delimiter argument (“|”) and then joined together by the second delimiter argument (“-“)

## Version History

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

* Now uses the `inList` method for comparison processing

### 2.0 (January 26, 2016)

* `d` (Delimiter) argument now optional (defaults to a comma)
* `u` (Case-sensitivity flag) argument now optional (defaults to case-insensitive)
* Regardless of the `u` (Case-sensitivity flag) argument, the plug-in no longer appends a value to a list if the value already exists in the list