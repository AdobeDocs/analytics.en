---
title: getPercentPageViewed
description: Retrieve the percentage of the page the visitor viewed.
---

# getPercentPageViewed

The `getPercentPageViewed` plugin measures a visitor's scroll activity through how much of a page the visitor viewed before moving on to another page. This plug-in is especially valuable for sites that have longer pages to see how far and how often visitors scroll. If your site does not have a lot of scrolling, this plug-in is not as applicable to your implementation.

## Install the getPercentPageViewed plug-in using Adobe Experience Platform Launch

You can install the `s.getPercentPageViewed()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `s.getPercentPageViewed()` function in the custom code editor of rules to assign variable values.

## Install the getPercentPageViewed plug-in using AppMeasurement

You can install the `s.getPercentPageViewed()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere after the tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Once installed, you can use the `s.getPercentPageViewed()` function to assign variable values.

## Plug-in code

> [!NOTE] This plug-in requires helper functions. Include the entire code block below, including helper functions, in your implementation.

```js
// getPercentPageViewed v3.01
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]);pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents,!1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""};

// handlePPVevents helper function (required for getPercentPageViewed v3.01 plug-in)
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}};

// p_fo (pageFirstOnly) helper function v2.0 (required for getPercentPageViewed v3.01 plug-in)
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
```

## Use the getPercentPageViewed plug-in with AppMeasurement and Launch custom code editor

The `s.getPercentPageViewed()` plugin returns nothing. Instead, it sets the following variables within the AppMeasurement object:

* `s._ppvPreviousPage`: The name of the previous page viewed. Final measurements are not available until an new page loads.
* `s._ppvHighestPercentViewed`: The furthest point that the visitor scrolled down on the previous page. If the visitor scrolled to the very bottom of the page, this value is `100`. If there is not enough content on a page to allow scrolling, this value is `100`.
* `s._ppvInitialPercentViewed`: The percentage of the previous page that was visible when the previous page first loaded. If there is not enough content on a page to allow scrolling, this value is `100`.
* `s._ppvHighestPixelSeen`: The highest number of total pixels seen (height-wise) as the visitor scrolled down the previous page.

Set some or all of these values to a custom variable for use in reporting. Record which custom variables you use in your [solution design document](../../prepare/solution-design.md).

> [!NOTE] This plug-in creates a cookie named `s_ppv` that records scroll information from page to page. It contains the above four variable values and expires at the end of the session.

```js
// Set each variable to a separate dimension
s.getPercentPageViewed();
s.eVar1 = s._ppvPreviousPage;
s.eVar2 = s._ppvHighestPercentViewed;
s.eVar3 = s._ppvInitialPercentViewed;
s.eVar4 = s._ppvHighestPixelSeen;

// Concatenate variables in fewer variables with explanation text in the dimension value
s.getPercentPageViewed();
s.eVar1 = s._ppvPreviousPage;
s.eVar2 = "Highest percent viewed: " + s._ppvHighestPercentViewed + " | Initial percent viewed: " + s._ppvInitialPercentViewed;
```

When you call `s.getPercentPageViewed()`, the following optional arguments are available:

* Page override: A page identifier tied to the above dimension values. It defaults to the `pageName` variable.
* Track changes to page size: If this argument is `false`, this plug-in does not consider any changes made to the page's size after its initial load. Its default value is `true`. Adobe recommends omitting this argument and leaving it as `true` in most cases.

```js
// Override the page identifier
s.getPercentPageViewed("Example page ID");

// Override page identifier and ignored changes to the size of the page after page load
s.getPercentPageViewed("Example page ID",false);
```
