---
title: getAndPersistValue
description: Store a value that can be retrieved later at any time.
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
---
# Adobe plug-in: getAndPersistValue

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getAndPersistValue` plug-in allows you to store a value in a cookie that can be retrieved later during a visit. It serves a similar role to the [!UICONTROL Storage duration] feature using tags in Adobe Experience Platform. Adobe recommends using this plug-in if you want to automatically persist an Analytics variable to the same value in subsequent hits after the variable was set. This plug-in is not necessary if the [!UICONTROL Storage duration] feature in Adobe Experience Platform is sufficient. It is also not necessary to use this plug-in if you do not need to set and persist variables to the same value in subsequent hits. The built-in persistence of eVars does not require the use of this plug-in, as these variables persist server-side by Adobe.

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
    * Action Type: Initialize getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getAndPersist` method uses the following arguments:

* **`vtp`** (required): The value to persist from page to page
* **`cn`** (optional): The name of the cookie to store the value. If this argument is not set, The cookie is named `"s_gapv"`
* **`ex`** (optional): The number of days before the cookie expires. If this argument is `0` or is not set, the cookie expires at the end of the visit (30 minutes of inactivity).

If the variable in the `vtp` argument is set, then the plug-in sets the cookie then returns the cookie value. If the variable in the `vtp` argument is not set, then the plug-in only returns the cookie value.

## Examples

### Example #1

The following code will set eVar21 equal to the value of "hello".  The code will then set the ev21gapv cookie, which will expire in 28 days, equal to the value of eVar21 (i.e. "hello").  The code will then (re)set eVar21 equal to the value of the ev21gapv cookie.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #2

Assume that eVar21 has not been set on the current page yet but was set equal to "hello" on a previous page within the last 28 days.   The following code will only set eVar21 equal to the value of the ev21gapv cookie (i.e. "hello").  It does not reset the ev21gapv cookie since eVar21 was not set on the current page before the function was called.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #3

Assume that eVar21 has not been set on the current page yet but was set equal to "hello" on a previous page within the last 28 days.  The following code will set only prop35 equal to the value of the ev21gapv cookie (i.e. "hello").  It will not set eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #4

The following code will set eVar21 equal to the value of "howdy".  The code will then set (or reset) the ev21gapv cookie, which will expire in 28 days, equal to the value of eVar21 (i.e. "howdy").  The code will then set prop35 equal to the value of the ev21gapv cookie (i.e. "howdy").

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #5

Assume that s.eVar21 has not been set on any pages within the last 28 days.  The following code will set s.eVar21 equal to nothing since the ev21gapv cookie would have expired 28 days after it was last set.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #6

The following code will set eVar30 equal to "shopping".  It will then set the s_gapv cookie, which will expire at the end of the browser session, equal to the value of s.eVar30 (i.e. "shopping").  It will then set s.eVar30 equal to the value of the s_gapv cookie (i.e. the getAndPersistValue call returns the value of the s_gapv cookie, which in this case is "shopping").

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

If s.eVar30 is not set to an explicit value on any additional pages seen during the session but is set (in doPlugins) via the following code...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 will be set equal to "shopping" (i.e. the persisted value of the s_gapv cookie)

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.0 (April 16, 2018)

* Point release (smaller code size)
* Passing 0 into the `ex` argument now forces expiration after 30 minutes of inactivity rather than expiration at the end of the browser session.

### 1.0 (January 18, 2016)

* Initial release.
