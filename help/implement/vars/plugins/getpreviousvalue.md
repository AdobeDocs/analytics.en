---
title: getPreviousValue
description: Get the last value passed into a variable.
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
---
# Adobe plug-in: getPreviousValue

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getPreviousValue` plug-in allows you to set a variable to a value set on a previous hit. This plug-in is not necessary if your implementation contains all desired values in the current hit.

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
    * Action Type: Initialize getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getPreviousValue` method uses the following arguments:

* **`v`** (string, required): The variable that has the value that you want to pass over to the next image request. A common variable used is `s.pageName` to retrieve the previous page value.
* **`c`** (string, optional): The name of the cookie that stores the value.  If this argument is not set, it defaults to `"s_gpv"`.

When you call this method, it returns the string value contained in the cookie. The plug-in then resets the cookie expiration, and assigns it the variable value from the `v` argument. The cookie expires after 30 minutes of inactivity.

## Example Calls

### Example #1

The following code...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* First sets s.prop7 equal to the value passed into s.pageName in the previous image request (i.e. the value stored in the "gpv_Page" cookie)
* The code will then reset the "gpv_Page" cookie, making it equal to the current value of s.pageName
* If s.pageName is not set at the time this code runs, then the code will reset the expiration for the cookie's current value

### Example #2

The following code sets s.prop7 equal to the last value passed into s.pageName, but only if event1 is also contained within s.events, as determined via the inList plug-in, at the time the call takes place.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Example #3

The following code sets s.prop7 equal to the last value passed into s.pageName but only if s.pageName is currently set on the page at the same time.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Example #4

The following code sets s.eVar10 equal to the value passed into s.eVar1 in the previous image request.   The previous eVar1 value would have been contained in the "s_gpv" cookie.  The code will then set the "s_gpv" cookie equal to the current value of s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Unlikely Quirks

If the variable associated with the v argument is set to a new value and the getPreviousValue plug-in runs BUT an Analytics server call is NOT sent at the same time, the new v argument value will still be considered the "previous value" the next time the plug-in runs.
For example, assume the following code runs on the first page of the visit:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

This code would produce a server call where the pageName argument is equal to "home" and the p7 (prop7) argument is not set.  However, the call to s.getPreviousValue would store the value of s.pageName (i.e. "home") in the cookie specified in the call (i.e. the "gpv_Page" cookie).
Now, assume that immediately afterwards, on the same page, the following code runs (for whatever reason):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Since the s.t() function does not run in this code block, another image request will not be created.  However, when the s.getPreviousValue() function code runs this time, s.prop7 will be set equal to the previous value of s.pageName (i.e. "home") and then will store the new value of s.pageName (i.e. "happy value") in the "gpv_Page" cookie.
Assume the visitor navigates to a different page and the following code runs on this page:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

When the s.t() call function runs, it will create an image request where s.pageName="page 2" and s.prop7 is equal to "happy value", which was the value of s.pageName when the last call to getPreviousValue took place.   The s.prop7 value of "home" was never contained in any real image request even though "home" was the first value passed into s.pageName.

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### v2.0 (October 7, 2019)

* Point release (complete logic rewrite).
