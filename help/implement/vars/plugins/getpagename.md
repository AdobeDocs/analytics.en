---
title: getPageName
description: Create an easy-to-read pageName from the current website path.
---

# Adobe plug-in: getPageName

## Plugin Purpose

### What does this plug-in do?

The getPageName plug-in creates a value that can be inserted into the Adobe Analytics pageName variable and that is an easy-to-read, "friendly"-formatted version of the current URL

### Why should I use this plug-in?

You should use the getPageName plug-in if you don't set the Analytics pageName variable within your code and your website has a very easy-to-parse-through pathing structure

### Why shouldn't I use this plug-in?

You won't need to use the getPageName plug-in if you already set the Analytics pageName variable equal to values that are easy to understand by your digital marketers.  The getPageName plug-in should be used as a "last resort" solution if you aren't able to provide data about how each page of your site should be named (dynamically or otherwise)

## Prerequisites

None

## How to Deploy

You may use one of the following three methods to deploy the getPageName plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the getPageName plug-in (via JavaScript), be sure to pass in the following arguments:

* **si** (optional, string): An ID that will be inserted into the beginning of the pageName value and represents the ID of the site (e.g. friendly name, etc.); When not set, this will default to the current domain (e.g. "www.sitename.com")
* **qv** (optional, string): A comma delimited list of query string parameters that, if found in the URL, will be added to the pageName (along with their values)
* **hv** (optional, string): A comma delimited list of parameters found in the URL hash that, if found in the URL, will be added to the pageName (along with their values)
* **de** (optional, string): A delimiter that will split up the individual parts of the pageName (based off the domain(ID)/path/query string parameters).  Defaults to a pipe character (e.g. "|")

## Returns
The getPageName plug-in returns a "friendly"-formatted version of the URL, to be passed into the Analytics' pageName variable, based off the criteria you specify in the arguments above

## Cookies
The getPageName plug-in does not create or use any cookies

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
