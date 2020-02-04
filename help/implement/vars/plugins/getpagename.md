---
title: getPageName
description: Create an easy-to-read pageName from the current website path.
---

# Adobe plug-in: getPageName

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getPageName` plug-in creates an easy to read, friendly formatted version of the current URL. Adobe recommends using this plug-in if you want a `pageName` value that is easy to set and understand in reporting. This plug-in is unnecessary if you already have a naming structure for the `pageName` variable, such as through a data layer. It is best used when you don't have another solution to set the `pageName` variable.

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

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
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

### 4.1 (September 17, 2019)

* Changed default delimiter value to a pipe character (from a colon + space).

### 4.0 (May 22, 2018)

* Complete reanalysis/rewrite of plug-in
