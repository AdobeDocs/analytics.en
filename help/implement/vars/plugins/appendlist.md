---
title: apl
description: Append values to variables that support multiple values.
---

# apl

The `apl` plug-in, also known as the `appendList` plug-in, adds values to an existing delimited string. This plug-in is valuable for Analytics variables that can hold multiple values in the same hit:

* You can add events to the `events` variable
* You can add values to a list variable without duplicating a value in the list
* You can add a product to the `products` variable based on page logic
* You can add values to the `linkTrackVars` or `linkTrackEvents` variables for use in link tracking

This plug-in has an option to check for existing values. It helps prevent duplicate values when inserting a value in the string.

## Install the apl plug-in using Adobe Experience Platform Launch

You can install the `s.apl()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `s.apl()` function in the custom code editor of rules to assign variable values.

## Install the apl plug-in using AppMeasurement

You can install the `s.apl()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere after the tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)).
3. Save the JS file and upload the new version to your web server.

Once installed, you can use the `s.apl()` function to assign variable values.

## Plug-in code

> [!NOTE] This plug-in requires that you also install the [`split`](split.md) plug-in.

```js
// Plugin Utility: apl v1.2 (requires split plug-in)
s.apl= function (l,v,d,u) {var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a.length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCase()));}}if(!m)l=l?l+d+v:v;return l;}
```

## Use the apl plug-in with AppMeasurement and Launch custom code editor

The `s.apl()` method returns a string. Use this function to assign variable values. It takes the following arguments:

* **Existing string**: The variable or string containing the existing data you want to add to. An empty string is valid.
* **New string**: The variable or string containing the new data you want to append.
* **Delimiter**: The string delimiter that you want to use.
* **Duplicate check**: An optional integer containing the duplicate check setting:
  * `0`: No duplicate check; value is always appended.
  * `1`: Duplicate check, case-insensitive; Do not append value if it already exists (uppercase or lowercase)
  * `2`: Duplicate check, case-sensitive; Do not append value if it already exists with exact matching case sensitivity.

## Examples

```js
// Append event2 to the events variable. Assigns the events variable to "event1,event2"
s.events = "event1";
s.events = s.apl(s.events,"event2",",");

// Progressively add items to a list variable with a semicolon delimiter. Assigns list1 the value of "Value 1,Value 2,Value 3"
var dt = ";";
s.list1 = s.apl(s.list1,"Value 1",dt);
s.list1 = s.apl(s.list1,"Value 2",dt);
s.list1 = s.apl(s.list1,"Value 3",dt);

// Iterate through an array and concatenate all values into a list variable with a pipe delimiter. Assigns list2 the value of "Milk|Eggs|Cheese"
var exampleArray = ["Milk","Eggs","Cheese"];
for (var i = 0; i < exampleArray.length; i++) {
  s.list2 = s.apl(s.list2,exampleArray[i],"|");
}

// The apl() function detects a duplicate, and therefore does not alter the string. Assigns the events variable to "event1,event2,event3"
s.events = "event1,event2,event3";
s.events = s.apl(s.events,"event2",",",1);
```
