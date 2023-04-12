---
title: getNewRepeat
description: Track activity of new vs. repeat visitors.
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
---
# Adobe plug-in: getNewRepeat

{{plug-in}}

The `getNewRepeat` plug-in allows you to determine whether a visitor to the site is a new visitor or a repeat visitor within a desired number of days. Adobe recommends using this plug-in if you want to identify visitors as "new" using a custom number of days. This plug-in is unnecessary if the New/Repeat visitor dimensions in Analysis Workspace meet your organization's needs.

## Install the plug-in using the Web SDK extension

Adobe offers an extension that allows you to use most commonly-used plug-ins with the Web SDK.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click **[!UICONTROL Tags]** on the left, then click the desired tag property.
1. Click **[!UICONTROL Extensions]** on the left, then click the **[!UICONTROL Catalog]** tab
1. Locate and install the **[!UICONTROL Common Web SDK Plugins]** extension.
1. Click **[!UICONTROL Data Elements]** on the left, then click the desired data element.
1. Set the desired data element name with the following configuration:
    * Extension: Common Web SDK Plugins
    * Data Element: `getNewRepeat`
1. Set the `daysBeforeReset` parameter on the right.
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
    * Action Type: Initialize getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getNewRepeat` function uses the following arguments:

* **`d`** (integer, optional): The minimum number of days required between visits that resets visitors back to `"New"`. If this argument is not set, it defaults to 30 days.

This function returns the value of `"New"` if the cookie set by the plug-in doesn't exist or has expired. It returns the value of `"Repeat"` if the cookie set by the plug-in exists and the amount of time since the current hit and the time set in the cookie is greater than 30 minutes. This function returns the same value for an entire visit.

This plug-in uses a cookie named `"s_nr[LENGTH]"` where `[LENGTH]` is equal to the `d` argument. The cookie contains a Unix timestamp representing the current time and the current status of the visitor (`"New"` or `"Repeat"`).

## Examples

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.1 (September 30, 2019)

* Rearrangement of JavaScript logic to reduce plug-in size

### 2.0 (April 16, 2018)

* Recompiled with smaller code size
* Removed the ability to name the cookie to store the visit info. The plug-in now dynamically names the cookie based on the value passed into the `d` argument.
