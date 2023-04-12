---
title: getVisitNum
description: Track a visitor's current visit number.
feature: Variables
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
---
# Adobe plug-in: getVisitNum

{{plug-in}}

The `getVisitNum` plug-in returns the visit number for all visitors that come to the site within the desired number of days. Analysis Workspace offers a 'Visit Number' dimension that provides similar functionality. Adobe recommends using this plug-in if you want more control over how visit number is incremented. This plug-in is unnecessary if the built-in 'Visit Number' dimension in Analysis Workspace is sufficient for your reporting needs.

## Install the plug-in using the Web SDK extension

Adobe offers an extension that allows you to use most commonly-used plug-ins with the Web SDK.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click **[!UICONTROL Tags]** on the left, then click the desired tag property.
1. Click **[!UICONTROL Extensions]** on the left, then click the **[!UICONTROL Catalog]** tab
1. Locate and install the **[!UICONTROL Common Web SDK Plugins]** extension.
1. Click **[!UICONTROL Data Elements]** on the left, then click the desired data element.
1. Set the desired data element name with the following configuration:
    * Extension: Common Web SDK Plugins
    * Data Element: `getVisitNum`
1. Set the desired parameters on the right.
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
    * Action Type: Initialize getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getVisitNum` function uses the following arguments:

* **`rp`** (optional, integer OR string): The number of days before the visit number counter resets.  Defaults to `365` when not set.
  * When this argument is `"w"`, the counter resets at the end of the week (this Saturday at 11:59 PM)
  * When this argument is `"m"`, the counter resets at the end of the month (the last day of this month)
  * When this argument is `"y"`, the counter resets at the end of the year (December 31st)
* **`erp`** (optional, boolean): When the `rp` argument is a number, this argument determines if the visit number expiration should be extended. If set to `true`, subsequent hits to your site resets the visit number counter. If set to `false`, subsequent hits to your site do not extend when the visit number counter resets. Defaults to `true`. This argument is not valid when the `rp` argument is a string.

The visit number increment whenever the visitor returns to your site after 30 minutes of inactivity. Calling this function returns an integer that represents the visitor's current visit number.

This plug-in sets a first-party cookie called `"s_vnc[LENGTH]"` where `[LENGTH]` is the value passed into the `rp` argument. For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. The value of the cookie is a combination of a Unix timestamp that represents when the visit counter resets, such as end of the week, end of the month, or after 365 days of inactivity. It also contains the current visit number. This plug-in sets another cookie named `"s_ivc"` that is set to `true` and expires after 30 minutes of inactivity.

## Examples

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## Version History

### 4.2 (March 19, 2021)

* Added version number as context data.

### 4.11 (September 30, 2019)

* Fixed an issue where the `erp` argument was explicitly set to `false`.

### 4.1 (May 21, 2018)

* Updated the `endOfDatePeriod` plug-in to v1.1.

### 4.0 (April 17, 2018)

* Point release (recompiled, smaller code size).
* Removed cookie arguments as the plug-in now dynamically generates cookies based on the `rp` argument)

### 3.0 (June 5, 2016)

* Complete overhaul
* Combined all previous solutions available in various versions of the `getVisitNum` plug-in.
