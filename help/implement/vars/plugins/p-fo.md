---
title: p_fo (Page First Only)
description: Ensure that certain routines fire only once per page.
---

# Adobe plug-in: p_fo (Page First Only)

## Purpose of This Plugin

### What does this plug-in do?
The p_fo (pageFirstOnly) plug-in is a utility that checks for the existence of a specific JavaScript object.  If the object doesn't exist, then the plug-in creates the object and returns the value of true.  This would be the first and only time the plug-in would create this object on the current page (hence the name, pageFirstOnly)

If the JavaScript object already exists on the page, then the function will return the value of false

### Why should I use this plug-in?
The doPlugins function, which is a key part of any Adobe Analytics/AppMeasurement deployment, has the potential to run multiple times while a visitor interacts with a single page even though certain portions of the doPlugins code might not have been meant to run so often.   Inadvertently running doPlugins multiple times per page might produce inaccurate data before Adobe Analytics is meant to send a server call.

p_fo allows you to add a conditional statement that will run code (in doPlugins or anywhere else) only if a specific JavaScript object hasn't been created yet on the page.  If the JavaScript object hasn't yet been created, the plug-in will create the object automatically, which in turn (by its mere existence) will prevent the code that would have just run from running again.

### Why shouldn't I use this plug-in?
If you don't care how often a certain piece of JavaScript code runs on a page, then you have no need for the p_fo plug-in.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run this plug-in

## How to Deploy

You may use one of the following three methods to deploy the p_fo plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.


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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the p_fo plug-in (via JavaScript), be sure to pass in the following arguments:

* **on** (required, string): The name of the JavaScript object that the plug-in will create if the object doesn't yet exist on the page.

## Returns
* If the object specified in the on argument doesn't exist on the page, then the plug-in will create the object and return the value of true
* If the object specified in the on argument does exist on the page, then the plug-in will return the value of false

## Cookies
The p_fo plug-in does not create or use any cookies

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
**NOTE:** Everytime a new page object/DOM loads (or the current page reloads), the object specified in the on argument will no longer exist and thus the p_fo plug-in will again return true the first time it runs after the page finishes loading.

## Version History

### 2.0

* Point release (recompiled, smaller code size).
* Changed return value type from integer to boolean

### 1.0

* Initial release.
