---
title: cleanStr
description: Remove/Replace All Unncessary characters from a String variable
---

# Adobe Plugin: cleanStr

## Plugin Purpose

### What does this plugin do?

The cleanStr plugin removes/replace all unnecessary characters from a string (or string variable), including the following characters:
* HTML tag characters
* Extra whitespaces (including double spaces)
* Left/right single quotes (‘’) (replaced with straight single quotes)
* Tabs
* Newlines/Carriage Returns

### Why should I use this plugin?

You should use the cleanStr plugin if you want to remove any unnecessary characters from your Adobe Analytics variables (or any JavaScript variables, for that matter)

### Why shouldn't I use this plugin?

If all the data you collect in your variables contain no unnecessary characters, then you won't need to use the cleanStr plugin

## Prerequisites

None

## How to Deploy

You may use one of the following three methods to deploy the cleanStr plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file

Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 (No Prerequisites Required) */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
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
	* Action Type: Initialize cleanStr
* Save and publish the changes to the rule

## How to Run the Plugin

When calling the cleanStr plugin (via JavaScript), be sure to pass in the following arguments:

* **str** (required, string): A string (variable or otherwise) containing any HTML encoding, extra whitespace, tabs, etc. that you want to remove from its value

## Returns

The cleanStr plugin returns the value of the str argument but with all the unnecessary characters taken out

## Cookies

The cleanStr plugin does not create or use any cookies

## Example Calls

### Example #1

Assume the following (where the dots represent spaces and the arrows represent tab characters
```javascript
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```
When you run the following code...
```javascript
s.eVar1 = cleanStr(s.eVar1)
```
...eVar1 will be set equal to "this is a messystring" (with all extra spaces and all tab characters removed)

### Example #2

If...
```javascript
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```
...and the following code runs...
```javascript
cleanStr(s.eVar1)
```
...the final value of s.eVar1 will still be:
```javascript
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```
Running the plugin all by itself (without assigning the return value to a variable) does not actually "reset" the variable passed in through the str argument.

## s Object Replacement
The cleanStr plugin does not require AppMeasurement or any other plugins and thus does not need to be attached to the s object (or other AppMeasurement object)

## Version History

### 1.0 (2018-04-15)

* Point Release (recompiled, smaller code size) and first official release