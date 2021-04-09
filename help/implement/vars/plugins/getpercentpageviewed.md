---
title: getPercentPageViewed
description: Retrieve the percentage of the page the visitor viewed.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
---
# Adobe plug-in: getPercentPageViewed

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getPercentPageViewed` plug-in measures a visitor's scroll activity to see how much of a page they view before moving on to another page. This plug-in is not necessary if your pages are small in height or do not want to measure scroll activity.

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
    * Action Type: Initialize getPercentPageViewed
1. Save and publish the changes to the rule.

## Install the plug-in using Launch custom code editor

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getPercentPageViewed` method uses the following arguments:

* **`pid`** (optional, string):  A page-based identifier you can correlate with the percentages provided by the plug-in's measurements.  Defaults to the `pageName` variable.
* **`ch`** (optional, boolean):  Set this to `false` (or `0`) if you don't want the plug-in to take into consideration any changes made to a page's size after its initial load. If omitted, this argument defaults to `true`. Adobe recommends omitting this argument in most cases.

Calling this method returns nothing; instead, it sets the following variables:

* `s._ppvPreviousPage`: The name of the previous page viewed. Final scrolling measurements for the current page aren't available until after a new page loads.
* `s._ppvHighestPercentViewed`: The highest percent of the previous page that the visitor viewed (height-wise). The furthest point that the visitor scrolled down to on the previous page.
* `s._ppvInitialPercentViewed`: The percent of the previous page that was visible when the previous page first loaded.
* `s._ppvHighestPixelsSeen`: The highest number of total pixels seen (height-wise) as the visitor scrolled down the previous page.
* `s._ppvFoldsSeen`: The highest number of "page folds" reached as the visitor scrolled down the previous page. This variable includes the "top-of-page" fold.
* `s._ppvFoldsAvailable`: The number of total "page folds" available to scroll down on the previous page.

Assign one or more of these variables to eVars to see dimension data in reports.

This plug-in creates a first-party cookie called `s_ppv` that contains the above values. It expires at the end of the browser session.

## Example Calls

### Example #1

The following code...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* Determines if s.pageName is set and if so, the code will run the getPercentPageViewed function
* When the getPercentPageViewed function runs, it will create the variables described in the "Returns" section above
* If the "Returns" variables have been successfully set:
  * The code will set s.prop1 equal to the value of s._ppvPreviousPage (i.e. the previous value of s.pageName, or the previous page)
  * The code will also set s.prop2 equal to the Highest Percent Viewed of the previous page and the Initial Percent Viewed of the previous page, along with the number of folds that the visitor reached and the number of folds that were available

**Note**:  If an entire page is visible when it first loads, both the Highest Percent Viewed and the Initial Percent Viewed dimensions would be equal to 100, and both the Folds Seen and Folds Available would be equal to 1.   When an entire page is NOT visible when it first loads but the visitor never ends up scrolling down the page before moving onto the next page, then both the Highest Percent Viewed and the Initial Percent Viewed dimensions would be equal to the same value.

### Example #2

Assume that s.prop5 has been set aside to capture a rolled-up "page type" rather than the entire page name.

The following code determines if s.prop5 has been set and, if so, will store its value as the "previous page" to correlate with the Highest Percent Viewed and the Initial Percent Viewed dimensions.  The value will still be stored in the s._ppvPreviousPage variable but can be treated as if it were the previous page type instead of the previous page name.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Version History

### 5.0 (March 19, 2021)

* Added version number as context data.

### v4.0 (October 7, 2019)

* Added `s._ppvFoldsSeen` and `s._ppvFoldsAvailable` solutions

### v3.01 (August 13, 2018)

* Fixed an issue for pages that have multiple AppMeasurement objects on a page

### v3.0 (April 13, 2018)

* Point release (recompiled, smaller code size)
* Plug-in now creates variables to be assigned to Adobe Analytics variables instead of return values
