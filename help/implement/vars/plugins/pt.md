---
title: pt
description: Add logic to your code to ensure that certain routines fire only once per page
---

# Adobe Experience Cloud Plugin – pt

## Purpose of This Plugin

### What does this plugin do?
The pt (pageFirstOnly) plugin is a utility that checks for the existence of a specific JavaScript object.  If the object doesn't exist, then the plugin creates the The pt plugin executes a function against a list of Adobe Analytics variables.

For example, the following function will run the clearVars function three times, once using eVar1 as the argument, once using eVar4 as the argument, and once using eVar29 as the argument.  The end result clears out the values of eVar1, eVar4 and eVar29
```javascript
s.pt("eVar1,eVar4,eVar29", ",", "clearVars");
```

### Why should I use this plugin?
In and of itself, there might not be a need to use this plugin.  However, several other Adobe Consulting plugins, including getQueryParam, require this plugin as the plugin allows them to work with multiple parameters and variables at the same time.

### Why shouldn't I use this plugin?
Do not use this plugin if you have no need to run a specific function on more than one Analytics variable at a time

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run this plugin

## How to Deploy

You may use one of the following three methods to deploy the pt plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: pt v2.01 (Requires AppMeasurement) */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
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
	* Action Type: Initialize pt
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the pt plugin (via JavaScript), be sure to pass in the following arguments:

* **l** (required, string): A list of Adobe Analytics variables (or other JavaScript variables) that the function contained in the "cf" argument can execute against.
* **de** (optional, string): The delimiter that separates the list of variables in the "l" argument; defaults to a comma (",") character.
* **cf** (required, string): The name of the callback function (contained in the AppMeasurement Object) to be called against each of the variables contained in the "l" argument.
* **fa** (optional, string): If the function in the "cf" argument calls for additional arguments when it runs, include them here; defaults to undefined

## Returns
The pt plugin will return a value if the callback function ("cf" argument) returns a value

## Cookies
The pt plugin by itself does not create any cookies.  However, the callback function specified in the cf argument might create cookies depending on its functionality.

## Example Calls

### Example #1
The following code is part of the getQueryParam plugin.  It runs the getParameterValue helper function against each of the key-value pairs that are contained in the URL's querystring (fullQueryString).  In other to extract each key-value pair, the fullQueryString must be delimited and split out by an ampersand "&" character. The parameterKey refers to the query string parameter that the plugin is specifically trying to extract from the query string

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```
The above line is a shortcut for running code that resembles the following:
```javascript
var returnValue = "",
	parameters = fullQueryString.split("&"),
	parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
	returnValue = s.getParameterValue(parameters[i], parameterKey);
	if(returnValue !== "") break;
}
```

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.pt=function(l,de,cf,fa)
```
...to this:
```javascript
[objectname].pt=function(l,de,cf,fa)
```

## Version History

### 2.01 (2019-09-24)
* Minor code changes to reduce overall size
### 2.0 (2018-04-17)
* Point Release (recompiled, smaller code size)
* Added Support for both the H-code and AppMeasurement versions of the Adobe Analytics javascript library.
### 1.0 (23 September 2013)
* Initial version



