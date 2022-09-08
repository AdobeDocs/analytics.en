---
title: getQueryParam
description: Extract the value of a URL's query string parameter.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
---
# Adobe plug-in: getQueryParam

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getQueryParam` plug-in allows you to extract the value of any query string parameter contained in a URL. It is useful for extracting campaign codes, both internal and external, from landing page URLs. It is also valuable when extracting search terms or other query string parameters.

This plug-in provides robust features in parsing complex URLs, including hashes and URLs containing multiple query string parameters. If you only have simple query string parameter needs, Adobe recommends using the URL parameter features using the Web SDK or the Adobe Analytics extension or the [`Util.getQueryParam()`](../functions/util-getqueryparam.md) method included in AppMeasurement.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

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
    * Action Type: Initialize getQueryParam
1. Save and publish the changes to the rule.-->

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getQueryParam` function uses the following arguments:

* **`qsp`** (required): A comma delimited list of query string parameters to look for within the URL. It is not case-sensitive.
* **`de`** (optional): The delimiter to use if multiple query string parameters match. Defaults to an empty string.
* **`url`** (optional): A custom URL, string, or variable to extract the query string parameter values from. Defaults to `window.location`.

Calling this function returns a value depending on the above arguments and the URL:

* If a matching query string parameter is not found, the function returns an empty string.
* If a matching query string parameter is found, the function returns the query string parameter value.
* If a matching query string parameter is found but the value is empty, the function returns `true`.
* If multiple matching query string parameters are found, the function returns a string with each parameter value delimited by the string in the `de` argument.

## Examples

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## Version History

### 4.0.1 (March 26, 2021)

* Updated issue where undefined was being returned instead of "" if the query param was not present in the query string.

### 4.0 (March 19, 2021)

* Added version number as context data.
* Removed dependencies on pt plugin.

### 3.3 (September 24, 2019)

* Bypassed unnecessary logic to reduce code size

### 3.2 (May 15, 2018)

* Moved `findParameterValue` and `getParameterValue` functions into the `getQueryParam` function

### 3.1 (May 10, 2018)

* Fixed an issue with capturing query string parameters with no value

### 3.0 (April 16, 2018)

* Point release (recompiled, smaller code size).
* Renamed helper functions to `findParameterValue` and `getParameterValue` for readability purposes.
* Removed the need to add an argument to find parameters contained in the URL hash

### 2.5 (January 8, 2016)

* Compatible with both H-code and AppMeasurement (requires `s.pt` with AppMeasurement).

### 2.4

* Added the `h` parameter, allowing the code to find query string parameters found after the hash (`#`) character

### 2.3

* Fixed a regression issue where the plug-in worked only when the hash was present after the tracking code

### 2.2

* Now removes hash characters (and everything afterwards) from the return value

### 2.1

* Compatible with H.10 code
