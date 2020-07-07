---
title: getValOnce
description: Prevent an Analytics variable from being set to the same value twice in a row.
---

# Adobe plug-in: getValOnce

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getValOnce` plug-in prevents a variable from being set equal to the same value more than once. Adobe recommends using this plug-in when you would like to deduplicate occurrences where a visitor refreshes a page or otherwise visit a given page multiple times. This plug-in is unnecessary if you are not worried about the 'Occurrences' metric in Analysis Workspace.

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
    * Action Type: Initialize getValOnce
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
/* Adobe Consulting Plugin: getValOnce v2.01 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:e);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getValOnce` method uses the following arguments:

* **`vtc`** (required, string): The variable to check and see if it was just previously set to an identical value
* **`cn`** (optional, string): The name of the cookie that holds the value to check. Defaults to `"s_gvo"`
* **`et`** (optional, integer): The expiration of the cookie in days (or minutes, depending on the `ep` argument). Defaults to `0`, which expires at the end of the browser session
* **`ep`** (optional, string): Only set this argument if the `et` argument is also set. Set this argument to `"m"` if you want the `et` argument to expire in minutes instead of days. Defaults to `"d"`, which sets the `et` argument in days.

If the `vtc` argument and cookie value match, this method returns an empty string. If the `vtc` argument and cookie value do not match, the method returns the `vtc` argument as a string.

## Example Calls

### Example #1

Use this call to prevent the same value being passed in to s.campaign more than once in a row for next 30 days:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

In the above call, the plug-in will first compare the value already contained in the s_campaign cookie with the value coming from the current s.campaign variable.   If a match is not made, the plug-in will set the s_campaign cookie equal to the new value coming from s.campaign and then return the new value.   This comparison will happen for the next thirty days

### Example #2

Use this call to prevent the same value being set throughout the session:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

This code prevents the same value from being passed into s.eVar2 more than once in a row throughout a user’s session.  It also ignores the “m” value in the epargument (at the end of the call) since the expiration time is set equal to 0.   The code also stores the comparison value in the s_ev2 cookie.

## Version History

### 2.01

* Fixed an issue with writing cookies.

### 2.0

* Point release (recompiled, smaller code size).

### 1.1

* Added the option to choose minutes or days for the expiration via the `t` parameter.
* Corrected the scope of the `k` variable used to restrict it to the plug-in only. This change prevents possible interference with other code on the page.
