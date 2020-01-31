---
title: p_fo (Page First Only)
description: Add logic to your code to ensure that certain routines fire only once per page
---

# Adobe Experience Cloud Plugin – p_fo (Page First Only)

## Purpose of This Plugin

### What does this plugin do?
The p_fo (pageFirstOnly) plugin is a utility that checks for the existence of a specific JavaScript object.  If the object doesn't exist, then the plugin creates the object and returns the value of true.  This would be the first and only time the plugin would create this object on the current page (hence the name, pageFirstOnly)

If the JavaScript object already exists on the page, then the function will return the value of false

### Why should I use this plugin?
The doPlugins function, which is a key part of any Adobe Analytics/AppMeasurement deployment, has the potential to run multiple times while a visitor interacts with a single page even though certain portions of the doPlugins code might not have been meant to run so often.   Inadvertently running doPlugins multiple times per page might produce inaccurate data before Adobe Analytics is meant to send a server call.

p_fo allows you to add a conditional statement that will run code (in doPlugins or anywhere else) only if a specific JavaScript object hasn't been created yet on the page.  If the JavaScript object hasn't yet been created, the plugin will create the object automatically, which in turn (by its mere existence) will prevent the code that would have just run from running again.

### Why shouldn't I use this plugin?
If you don't care how often a certain piece of JavaScript code runs on a page, then you have no need for the p_fo plugin.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run this plugin

## How to Deploy

You may use one of the following three methods to deploy the p_fo plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
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
	* Action Type: Initialize p_fo
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the p_fo plugin (via JavaScript), be sure to pass in the following arguments:

* **on** (required, string): The name of the JavaScript object that the plugin will create if the object doesn't yet exist on the page.

## Returns
* If the object specified in the on argument doesn't exist on the page, then the plugin will create the object and return the value of true
* If the object specified in the on argument does exist on the page, then the plugin will return the value of false

## Cookies
The p_fo plugin does not create or use any cookies

## Example Calls

### Example #1
The following code will check for the existence of the "myobject" object within the page.  If the "myobject" object doesn't exist, then the code will create the "myobject" object and return the value of true.  As a result, the code within the conditional statement (i.e. Console.log('hello');) will run.

On the other hand, if the "myobject" object already exists when the p_fo call takes place, then the p_fo function will return the value of false and, thus, the conditional statement will be considered false.  In this case, the code within the conditional statement will not run.

```javascript
if(s.p_fo("myobject"))
{
	console.log("hello");
}
```
**NOTE:** Everytime a new page object/DOM loads (or the current page reloads), the object specified in the on argument will no longer exist and thus the p_fo plugin will again return true the first time it runs after the page finishes loading.

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.p_fo=function(on)
```
...to this:
```javascript
[objectname].p_fo=function(on)
```

## Version History

### 2.0
* Point release (recompiled, smaller code size)
* Changed return value type from Integer to Boolean
### 1.0
* Initial Release



