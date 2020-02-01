---
title: getQueryParam
description: Extract the value of a URL's query string parameter.
---

# Adobe plug-in: getQueryParam

## Purpose of This Plugin

### What does this plug-in do?
The getQueryParam plug-in allows you to extract the value of any query string parameter contained in a URL

### Why should I use this plug-in?
The getQueryParam plug-in is an essential plug-in that is used for, but not limited to:

* Extracting campaign tracking codes – both internal and external – from landing page URLs
* Extracting search terms from other query string parameters
* Etc.

If you use AppMeasurement, which has its own built-in version of the plug-in (s.Util.getQueryParam), Adobe Consulting still recommends using this version of the plug-in as it contains enhanced functionality that is not currently present in the below-the-line version.

### Why shouldn't I use this plug-in?

If you have no need to extract any query string parameters from a URL, then you have no need to use the getQueryParam plug-in.  You may use also Adobe Experience Platform Launch or Adobe Analytics Processing Rules to extract query string parameters values.

## Prerequisites
To run the getQueryParam plug-in, you must have the following code/plugins:
* AppMeasurement (i.e. the base Adobe Analytics Code)
* pt v2.0 (plugin, included in code below)

## How to Deploy

You may use one of the following three methods to deploy the getQueryParam plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install (and publish) the "Common Analytics Plugins" extension
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

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires AppMeasurement and pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 (Requires AppMeasurement) */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getQueryParam plug-in (via JavaScript), be sure to pass in the following arguments:
* **qsp** (required): A comma delimited list of query string parameters to look for within the URL.  The search will be case-insensitive.
* **de** (optional): If the code finds multiple query string parameters in the URL (as specified in p), this parameter will be the delimiter used to separate out the individual query string parameter values as the code returns the result.  Defaults to nothing (i.e. a blank string)
* **url** (optional): A custom url/string/variable to extract the query string parameter values from.  Defaults to the value of s.pageURL (or window.location).

## Returns
* The getQueryParam plug-in will return the value of the query string parameter specified in qsp
* The plug-in will return nothing if the query string parameter specified in qsp does not exist in the URL
* The plug-in will return 'true' if the query string parameter specified in qsp exists in the URL but does not contain a value
* If the plug-in finds multiple query string parameters in the URL, then it will return each of the parameters' values concatenated together but delimited by the character(s) specified in de
* If the getQueryParam call does not contain the de parameter but the code finds multiple query string parameters in the URL, it will ultimately return each of the parameters' values concatenated together but without a delimiter to separate them.

## Cookies
The getQueryParam plug-in does not create or use any cookies

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
