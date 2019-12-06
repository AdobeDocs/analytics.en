---
description: Measures a visitor's scroll activity to see how much of a page they view before moving on to another page. This plugin lets you determine how much of your content users are seeing on average, so that you can optimize your page lengths and layouts based on user behaviors.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
---

# getPercentPageViewed

The getPercentPageViewed plugin measures a visitor's scroll activity to see how much of a page the visitor viewed before moving on to another page.

>[!NOTE]
>You do not need to use the getPercentPageViewed plugin if your web pages are small in height and there is no need to measure how far visitors scroll down. Also, if you want to measure scroll activity on exit pages only, you cannot use this plugin.

## Prerequisites

You must have AppMeasurement and the handlePPVevents helper plugin to run the getPercentPageViewed plugin.

## Implementation

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>Adding the bolded comments/version numbers of the code to the AppMeasurement file helps Adobe Consulting with troubleshooting any potential implementation issues.

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## Arguments to pass in

|Argument|Definition|
|---|---|
|pid (optional, string)|A page identifier that is correlated with the percentages provided by the plugin measurements. It defaults to the Analytics pageName variable or the URL if the pageName variable is not set|
|ch (optional, Boolean)|"True" is the recommended/default value for this argument. Set this equal to "false" if you do not want this plugin to consider any changes made to a page's size after its initial load, due to SPA code, dynamic HTML, etc.|

## Returns

The getPercentPageViewed plugin returns nothing. Instead, it sets the following variables within the AppMeasurement object:

* `s._ppvPreviousPage`: The name of the previous page viewed (because final measurements are not available until an new page loads.)
* `s._ppvHighestPercentViewed`: The highest percent of the previous page that the visitor viewed (height-wise). In other words, the furthest point that the visitor scrolled down on the previous page.
* `s._ppvInitialPercentViewed`: The percentage of the previous page that was visible when the previous page first loaded.
* `s._ppvHighestPixelSeen`: The highest number of total pixels seen (height-wise) as the visitor scrolled down the previous page.

## Cookies

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. The contents of the cookie contain the values inserted in the four variables described above and expire at the end of the session.

## Example Calls

**Sample Call 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

The code sample above:
* Determines if s.pageName is set and if so, the code will run the getPercentPageViewed function.
* When the `getPercentPageViewed` function runs, it creates the variables described in the "Returns" section above.
* If the "Returns" variables were successfully set:

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * The code also sets s.prop2 equal to the Highest Percentage Viewed of the previous page and the Initial Percentage Viewed of the previous page.

>[!NOTE]
>If an entire page is visible when it first loads, both the Highest Percentage Viewed and the Initial Percentage Viewed dimensions would be equal to 100. However, if an entire page is not visible when it first loads, but the visitor never scrolls down the page before moving on to the next page, then both the Highest Percentage Viewed and the Initial Percentage Viewed dimensions would be equal to the same value.

**Sample Call 2**

Assume that s.prop5 has been set aside to capture a rolled-up "page type" rather than the entire page name.

The following code determines if s.prop5 has been set and, if so, stores its value as the "previous page" to correlate with the Highest Percentage Viewed and the Initial Percentage Viewed dimensions. The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## S Object Replacement

When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this:

`s.getPercentPageViewed=function(pid,ch)`

to this:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Code to Deploy

Plugins Section: Add the following code to the area of the `s_code.js` file labeled PLUGINS SECTION. Do not make any changes to this portion of the plug-in code.

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
