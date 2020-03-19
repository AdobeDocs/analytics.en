---
title: cleanStr
description: Remove or replace All unnecessary characters from a string.
---

# Adobe plug-in: cleanStr

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `cleanStr` plug-in removes or replaces all unnecessary characters from a string, including HTML tag characters, extra whitespaces, tabs, and newline/carriage returns. It also replaces left/right single quotes (`‘` and `’`) with straight single quotes (`'`). Adobe recommends using this plug-in if you want to remove unnecessary characters from variable values and the 'Clean text' feature in Launch does not fulfill your implementation needs. This plug-in is not necessary if the collected data does not contain unnecessary characters, or if the 'Clean text' feature in Launch is sufficient.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize cleanStr
1. Save and publish the changes to the rule.

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `cleanStr` method uses the following arguments:

* **`str`** (required, string): The value that you want to clean HTML encoding, extra whitespace, tabs, or other unnecessary characters.

The method returns the value of the `str` argument with all unnecessary characters removed.

## Examples

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

## Version History

### 1.0 (April 15, 2018)

* Initial release.
