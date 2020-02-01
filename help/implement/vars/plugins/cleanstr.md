---
title: cleanStr
description: Remove or replace All unnecessary characters from a string.
---

# Adobe plug-in: cleanStr

## Plugin Purpose

### What does this plug-in do?

The cleanStr plug-in removes/replace all unnecessary characters from a string (or string variable), including the following characters:
* HTML tag characters
* Extra whitespaces (including double spaces)
* Left/right single quotes (‘’) (replaced with straight single quotes)
* Tabs
* Newlines/Carriage Returns

### Why should I use this plug-in?

You should use the cleanStr plug-in if you want to remove any unnecessary characters from your Adobe Analytics variables (or any JavaScript variables, for that matter)

### Why shouldn't I use this plug-in?

If all the data you collect in your variables contain no unnecessary characters, then you won't need to use the cleanStr plug-in

## Prerequisites

None

## How to Deploy

You may use one of the following three methods to deploy the cleanStr plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: cleanStr v1.0 (No Prerequisites Required) */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the cleanStr plug-in (via JavaScript), be sure to pass in the following arguments:

* **str** (required, string): A string (variable or otherwise) containing any HTML encoding, extra whitespace, tabs, etc. that you want to remove from its value

## Returns

The cleanStr plug-in returns the value of the str argument but with all the unnecessary characters taken out

## Cookies

The cleanStr plug-in does not create or use any cookies

## Example Calls

### Example #1

Assume the following (where the dots represent spaces and the arrows represent tab characters

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```
When you run the following code...

```js
s.eVar1 = cleanStr(s.eVar1)
```
...eVar1 will be set equal to "this is a messystring" (with all extra spaces and all tab characters removed)

### Example #2

If...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```
...and the following code runs...

```js
cleanStr(s.eVar1)
```
...the final value of s.eVar1 will still be:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```
Running the plug-in all by itself (without assigning the return value to a variable) does not actually "reset" the variable passed in through the str argument.

## s Object Replacement
The cleanStr plug-in does not require AppMeasurement or any other plug-ins and thus does not need to be attached to the s object (or other AppMeasurement object)

## Version History

### 1.0 (2018-04-15)

* Point Release (recompiled, smaller code size) and first official release