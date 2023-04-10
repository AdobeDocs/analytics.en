---
title: p_fo (Page First Only)
description: Ensure that certain routines fire only once per page.
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
---
# Adobe plug-in: p_fo (Page First Only)

{{plug-in}}

The `p_fo` plug-in is a utility that checks for the existence of a specific JavaScript object. If the object doesn't exist, then the plug-in creates the object and returns `true`. If the JavaScript object already exists on the page, then it returns `false`. This plug-in is useful to run code exactly once on a page. Several other plug-ins rely on this code to work. This plug-in is unnecessary if you're not worried about how many times code runs on a page, or if you don't use any dependent plug-ins.

## Install the plug-in using the Web SDK or Web SDK extension

This plug-in is not yet supported for use within the Web SDK.

## Install the plug-in using the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize p_fo
1. Save and publish the changes to the rule.

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `p_fo` function uses the following arguments:

* **on** (required, string): The name of the JavaScript object that the plug-in creates if the object doesn't yet exist on the page.

If the object doesn't yet exist, this function returns `true` and creates the object. If the object already exists, this function returns `false`.

## Example Calls

### Example #1

The following code will check for the existence of the "myobject" object within the page.  If the "myobject" object doesn't exist, then the code will create the "myobject" object and return the value of true.  As a result, the code within the conditional statement (i.e. Console.log('hello');) will run.

On the other hand, if the "myobject" object already exists when the p_fo call takes place, then the p_fo function will return the value of false and, thus, the conditional statement will be considered false.  In this case, the code within the conditional statement will not run.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTE:** Every time a new page object/DOM loads (or the current page reloads), the object specified in the on argument will no longer exist and thus the p_fo plug-in will again return true the first time it runs after the page finishes loading.

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.0

* Point release (recompiled, smaller code size).
* Changed return value type from integer to boolean

### 1.0

* Initial release.
