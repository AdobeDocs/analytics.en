---
title: getQueryParam
description: Extract the value of a URL's query string parameter.
---

# Adobe plug-in: getQueryParam

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getQueryParam` plug-in allows you to extract the value of any query string parameter contained in a URL. It is useful for extracting campaign codes, both internal and external, from landing page URLs. It is also valuable when extracting search terms or other query string parameters.

This plug-in provides robust features in parsing complex URLs, including hashes and URLs containing multiple query string parameters. If you only have simple query string parameter needs, Adobe recommends using the URL parameter features in Launch or the [`Util.getQueryParam()`](../functions/util-getqueryparam.md) method included in AppMeasurement.

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
    * Action Type: Initialize getQueryParam
1. Save and publish the changes to the rule.

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
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

The `getQueryParam` method uses the following arguments:

* **`qsp`** (required): A comma delimited list of query string parameters to look for within the URL. It is not case-sensitive.
* **`de`** (optional): The delimiter to use if multiple query string parameters match. Defaults to an empty string.
* **`url`** (optional): A custom URL, string, or variable to extract the query string parameter values from. Defaults to `window.location`.

Calling this method returns a value depending on the above arguments and the URL:

* If a matching query string parameter is not found, the method returns an empty string.
* If a matching query string parameter is found, the method returns the query string parameter value.
* If a matching query string parameter is found but the value is empty, the method returns `true`.
* If multiple matching query string parameters are found, the method returns a string with each parameter value delimited by the string in the `de` argument.

## Example Calls

### Example #1

If the current URL is the following:

```js
http://www.abc123.com/?cid=trackingcode1
```

The following code will set s.campaign equal to "trackingcode1":

```js
s.campaign=s.getQueryParam('cid');
```

### Example #2

If the current URL is the following:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

The following code will set s.campaign equal to "trackingcode1:123456":

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Example #3

If the current URL is the following:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

The following code will set s.campaign equal to "trackingcode1123456":

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Example #4

If the current URL is the following:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

The following code will set s.campaign equal to "123456":

```js
s.campaign=s.getQueryParam('ecid');
```

### Example #5

If the current URL is the following:

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

The following code will set s.campaign equal to "123456"

```js
s.campaign=s.getQueryParam('ecid');
```

**Note:** The plug-in replaces the URL to Check's hash character with a question mark if a question mark does not exist.  If the URL contains a question mark that comes before the hash character, the plug-in will replace the URL to Check's hash character with an ampersand;

### Example #6

If the current URL is the following...

```js
http://www.abc123.com/
```

...and if the variable s.testURL is set as follows:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

The following code will not set s.campaign at all:

```js
s.campaign=s.getQueryParam('cid');
```

However, the following code will set s.campaign equal to "trackingcode1":

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**Note:** the third parameter can be any string/variable that the code will use to try to find the query string parameters in

The following code will set s.eVar2 equal to "123456|trackingcode1|true|300":

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* The value of 123456 comes from the ecid parameter in the s.testURL variable
* The value of trackingcode1 comes from the cid parameter in the s.testURL variable
* The value of true comes from the existence (but non-value) of the location parameter after the hash character in the s.testURL variable

The value of 300 comes from the value of the pos parameter in the s.testURL variable

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
