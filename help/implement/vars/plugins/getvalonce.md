---
title: getValOnce
description: Prevent an Analytics variable from being set to the same value twice in a row.
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
---
# Adobe plug-in: getValOnce

{{plug-in}}

The `getValOnce` plug-in prevents a variable from being set equal to the same value more than once. Adobe recommends using this plug-in when you would like to deduplicate occurrences where a visitor refreshes a page or otherwise visit a given page multiple times. This plug-in is unnecessary if you are not worried about the 'Occurrences' metric in Analysis Workspace.

## Install the plug-in using the Web SDK extension

Adobe offers an extension that allows you to use most commonly-used plug-ins with the Web SDK.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click **[!UICONTROL Tags]** on the left, then click the desired tag property.
1. Click **[!UICONTROL Extensions]** on the left, then click the **[!UICONTROL Catalog]** tab
1. Locate and install the **[!UICONTROL Common Web SDK Plugins]** extension.
1. Click **[!UICONTROL Data Elements]** on the left, then click the desired data element.
1. Set the desired data element name with the following configuration:
    * Extension: Common Web SDK Plugins
    * Data Element: `getValOnce`
1. Set the desired parameters on the right.
1. Save and publish the changes to the data element.

## Install the plug-in manually implementing the Web SDK

This plug-in is not yet supported for use within a manual implementation of the Web SDK.

## Install the plug-in using the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins with Adobe Analytics.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getValOnce
1. Save and publish the changes to the rule.

## Install the plug-in using custom code editor

If you do not want to use the Common Analytics Plugins plug-in extension, you can use the custom code editor.

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
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getValOnce` function uses the following arguments:

* **`vtc`** (required, string): The variable to check and see if it was just previously set to an identical value
* **`cn`** (optional, string): The name of the cookie that holds the value to check. Defaults to `"s_gvo"`
* **`et`** (optional, integer): The expiration of the cookie in days (or minutes, depending on the `ep` argument). Defaults to `0`, which expires at the end of the browser session
* **`ep`** (optional, string): Only set this argument if the `et` argument is also set. Set this argument to `"m"` if you want the `et` argument to expire in minutes instead of days. Defaults to `"d"`, which sets the `et` argument in days.

If the `vtc` argument and cookie value match, this function returns an empty string. If the `vtc` argument and cookie value do not match, the function returns the `vtc` argument as a string.

## Examples

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## Version History

### 3.1 (September 22, 2022)

* Fixed bug for expiration

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.01

* Fixed an issue with writing cookies.

### 2.0

* Point release (recompiled, smaller code size).

### 1.1

* Added the option to choose minutes or days for the expiration via the `t` parameter.
* Corrected the scope of the `k` variable used to restrict it to the plug-in only. This change prevents possible interference with other code on the page.
