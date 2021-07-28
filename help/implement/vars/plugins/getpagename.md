---
title: getPageName
description: Create an easy-to-read pageName from the current website path.
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
---
# Adobe plug-in: getPageName

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getPageName` plug-in creates an easy to read, friendly formatted version of the current URL. Adobe recommends using this plug-in if you want a [`pageName`](../page-vars/pagename.md) value that is easy to set and understand in reporting. This plug-in is unnecessary if you already have a naming structure for the `pageName` variable, such as through a data layer. It is best used when you don't have another solution to set the `pageName` variable.

## Install the plug-in using tags in Adobe Experience Platform

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getPageName
1. Save and publish the changes to the rule.

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getPageName` method uses the following arguments:

* **`si`** (optional, string): An ID inserted into the beginning of the string representing the ID of the site. This value can either be a numeric ID or a friendly name. When not set, it defaults to the current domain.
* **`qv`** (optional, string): A comma-delimited list of query string parameters that, if found in the URL, are added to the string
* **`hv`** (optional, string): A comma-delimited list of parameters found in the URL hash that, if found in the URL, are added to the string
* **`de`** (optional, string): The delimiter to split up individual parts of the string. Defaults to a pipe (`|`).

The method returns a string containing a friendly-formatted version of the URL. This string is typically assigned to the `pageName` variable, but can be used in other variables as well.

## Example Calls

### Example #1

If the current URL were...

```js
https://mail.google.com/mail/u/0/#inbox
```

...and the following code runs...

```js
s.pageName = getPageName()
```

...the final value of s.pageName will be:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Example #2

If the current URL were...

```js
https://mail.google.com/mail/u/0/#inbox
```

...and the following code runs...

```js
s.pageName = getPageName("gmail")
```

...the final value of s.pageName will be:

```js
s.pageName = "gmail|mail|u|0";
```

### Example #3

If the current URL were...

```js
https://www.google.com/
```

...and the following code runs...

```js
s.pageName = getPageName()
```

...the final value of s.pageName will be:

```js
s.pageName = "www.google.com|home"
```

**Note**: When the code runs on a URL that does not contain a path, it will always add the value of "home" to the end of the return value

### Example #4

If the current URL were...

```js
https://www.google.com/
```

...and the following code runs...

```js
s.pageName = getPageName("google","","","|")
```

...the final value of s.pageName will be:

```js
s.pageName = "google|home"
```

### Example #5

If the current URL were...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...and the following code runs...

```js
s.pageName = getPageName()
```

...the final value of s.pageName will be:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

However, if the following code runs instead...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...the final value of s.pageName will be:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Upgrading from Previous Versions

Version 4.0+ of the getPageName plug-in is not dependent on the existence of the Adobe Analytics' AppMeasurement object (i.e. the "s" object) to run.  If you choose to upgrade to this version, be sure to change the code that calls the plug-in by removing any instances of the "s" object from the call.
For example, change this:

```js
s.pageName = s.getPageName();
```

...to this:

```js
s.pageName = getPageName();
```

## Version History

### 4.2 (March 19, 2021)

* Added version number as context data.

### 4.1 (September 17, 2019)

* Changed default delimiter value to a pipe character (from a colon + space).

### 4.0 (May 22, 2018)

* Complete reanalysis/rewrite of plug-in
