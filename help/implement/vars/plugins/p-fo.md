---
title: p_fo (Page First Only)
description: Ensure that certain routines fire only once per page.
---

# Adobe plug-in: p_fo (Page First Only)

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `p_fo` plug-in is a utility that checks for the existence of a specific JavaScript object. If the object doesn't exist, then the plug-in creates the object and returns `true`. If the JavaScript object already exists on the page, then it returns `false`. This plug-in is useful to run code exactly once on a page. Several other plug-ins rely on this code to work. This plug-in is unnecessary if you're not worried about how many times code runs on a page, or if you don't use any dependent plug-ins.

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
    * Action Type: Initialize p_fo
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

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `p_fo` method uses the following arguments:

* **on** (required, string): The name of the JavaScript object that the plug-in creates if the object doesn't yet exist on the page.

If the object doesn't yet exist, this method returns `true` and creates the object. If the object already exists, this method returns `false`.

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
