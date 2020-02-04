---
title: getQueryParam
description: Extract the value of a URL's query string parameter.
---

# Adobe plug-in: getQueryParam

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help gain more value out of your use of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getQueryParam` plug-in allows you to extract the value of any query string parameter contained in a URL. It is useful for extracting campaign codes, both internal and external, from landing page URLs. It is also valuable when extracting search terms or other query string parameters.

This plug-in provides robust features in parsing complex URLs, including hashes and URLs containing multiple query string parameters. If you only have simple query string parameter needs, Adobe recommends using the URL parameter features in Launch or the `Util.getQueryParam` method included in AppMeasurement.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. For any Launch Rule where you want to use the plug-in, add an action with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule

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
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
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
