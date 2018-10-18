---
description: Measures a visitor's scroll activity to see how much of a page they view before moving on to another page. This plugin lets you determine how much of your content users are seeing on average, so that you can optimize your page lengths and layouts based on user behaviors.
keywords: Analytics Implementation
seo-description: Measures a visitor's scroll activity to see how much of a page they view before moving on to another page. This plugin lets you determine how much of your content users are seeing on average, so that you can optimize your page lengths and layouts based on user behaviors.
seo-title: getPercentPageViewed
solution: Analytics
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: b16399aa-23da-4c75-94e4-17345478f399
index: y
internal: n
snippet: y
---

# getPercentPageViewed

Measures a visitor's scroll activity to see how much of a page they view before moving on to another page. This plugin lets you determine how much of your content users are seeing on average, so that you can optimize your page lengths and layouts based on user behaviors.

 You can also use classifications to group percentages (such as *`Less than 25%`* or *`Less than 50%`*) so that you can identify page-viewing trends.

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**Returns:** Nothing. Instead, it sets the following variables within the AppMeasurement object:

* s._ppvPreviousPage: The name of the previous page viewed (as final measurements aren't available until a new page loads)
* s._ppvHighestPercentViewed: The highest percent of the previous page that the visitor viewed (height-wise); in other words, the furthest point that the visitor scrolled down on the previous page
* s._ppvInitialPercentViewed: The percent of the previous page that was visible when the previous page first loaded
* s.ppvHighestPixelsSeen: The highest number of total pixels seen (height-wise) as the visitor scrolled down the previous page

**pid {optional, string):** A page identifier that will be correlated with the percentages provided by the plugin measurements. Defaults to the Analytics' pageName variable OR the URL if the pageName variable is not set.

**ch {optional, boolean):** Set this equal to false if you don't want the plugin to take into consideration any changes made to a page's size after its initial load (due to SPA code, dynamic HTML, etc.). true is the recommended/default value for this argument

**Sample Calls**

```js
 
   s.getPercentPageViewed=function(pid,ch);

```

**Returns**

* If there was not a previous page view in this visit, an empty string is returned 
* If pid is "-", or unspecified, an integer containing the last page's maximum percent viewed is returned 
* Otherwise, an array is returned with the following elements:

    * array[0] - Page ID 
    * array[1] - Maximum percent viewed 
    * array[2] - Initial percent viewed 
    * array[3] - Maximum vertical pixels viewed 
    * array[4] - Viewport width in CSS pixels new 
    * array[5] - Viewport height in CSS pixels new 
    * array[6] - Display width in real pixels (reflecting orientation) new 
    * array[7] - Display height in real pixels (reflecting orientation) new 
    * array[8] - Final pixel density new 
    * array[9] - Device orientation, set to one of the following text strings: new

        * "L" - Landscape (rotation did not occur) 
        * "P" - Portrait (rotation did not occur) 
        * "LP" - started landscape, ended portrait 
        * "PL" - started portrait, ended landscape

**Plugins Section**: Add the following code to the area of the [!DNL s_code.js] file labeled PLUGINS SECTION. Do not make any changes to this portion of the plug-in code.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.0 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */ 
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 
 
/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.0 Plugin) */ 
s.handlePPVevents=function(){if(s_c_il){for(var b=0,d=s_c_il.length;b<d;b++)if("undefined"!=typeof s_c_il[b]&&s_c_il[b]._c&&"s_c"==s_c_il[b]._c){var a=s_c_il[b];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight));b=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round(b/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0]) !==a.ppvID||1==a.ppvChange&&a.c_r("s_tp")&&f!=a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var c=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<c.length?c[0]:escape(a.ppvID);var g=1<c.length?parseInt(c[1]):d,h=2<c.length?parseInt(c[2]) :d;c=3<c.length?parseInt(c[3]):b;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(b>c?b:c));a.c_w("s_ppv",e)}}}; 
 
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; /******************************************** END CODE TO DEPLOY ********************************************/ 

```

**Notes**

* Always test plug-in installations to ensure that data collection is as expected before deploying in a production environment. 
* Because the plug-in passes the percentage of page viewed on the previous page, data is not collected for the final hit of the visit. One way to help mitigate this limitation is to use a function on all exit links to call *`s.getPercentPageViewed()`*. 
* This plug-in relies on the ability to set cookies in the user's web browser. If the user does not accept first-party cookies, the plug-in will not pass data into [!DNL Analytics]. 
* The plug-in creates its own first-party cookie named [!DNL s_ppv]. 
* A very small percentage of users will not pass percentage of page viewed data due to browser limitations. However, this plug-in has been successfully tested in IE, Firefox, Chrome, Safari, and Opera.

