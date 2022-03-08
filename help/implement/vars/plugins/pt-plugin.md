---
title: pt
description: Executes a function on a list of variables.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
---
# Adobe plug-in: pt

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `pt` plug-in executes a function or method on a list of Analytics variables. For example, you can selectively run the [`clearVars`](../functions/clearvars.md) function on several variables without manually calling the function each time. Several other plug-ins depend on this code to run correctly. This plug-in is not necessary if you have no need to run a specific function on more than one Analytics variable at a time, or if you're not using any dependent plug-ins.

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
    * Action Type: Initialize pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `pt` function uses the following arguments:

* **`l`** (required, string): A list of variables that the function contained in the `cf` argument can execute against.
* **`de`** (optional, string): The delimiter that separates the list of variables in the `l` argument. Defaults to a comma (`,`).
* **`cf`** (required, string): The name of the callback function contained in the AppMeasurement object to be called against each of the variables contained in the `l` argument.
* **`fa`** (optional, string): If the function in the `cf` argument calls for additional arguments when it runs, include them here. Defaults to `undefined`.

Calling this function returns a value if the callback function (in the `cf` argument) returns a value.

## Example Calls

### Example #1

The following code is part of the getQueryParam plug-in.  It runs the getParameterValue helper function against each of the key-value pairs that are contained in the URL's querystring (fullQueryString).  In other to extract each key-value pair, the fullQueryString must be delimited and split out by an ampersand "&" character. The parameterKey refers to the query string parameter that the plug-in is specifically trying to extract from the query string

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

The above line is a shortcut for running code that resembles the following:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.01 (September 24, 2019)

* Minor code changes to reduce overall size

### 2.0 (April 17, 2018)

* Point release (recompiled, smaller code size).
* Added support for both H-code and AppMeasurement.

### 1.0 (23 September 2013)

* Initial release.
