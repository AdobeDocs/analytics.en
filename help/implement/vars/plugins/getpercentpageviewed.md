---
title: getPercentPageViewed
description: Retrieve the percentage of the page the visitor viewed.
---

# Adobe plug-in: getPercentPageViewed

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help gain more value out of your use of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getPercentPageViewed` plug-in measures a visitor's scroll activity to see how much of a page they view before moving on to another page. This plug-in is not necessary if your pages are small in height or do not want to measure scroll activity.

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
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the getPercentPageViewed plug-in (via JavaScript), be sure to pass in the following arguments:

* **pid** (optional, string):  A page-based identifier that will be correlated with the percentages provided by the plug-in's measurements.  Defaults to the Analytics' pageName variable OR the URL if the pageName variable is not set.
* **ch** (optional, boolean):  Set this equal to false (or 0) if you don't want the plug-in to take into consideration any changes made to a page's size after its initial load (due to SPA code, dynamic HTML, etc.).  "true" (or 1) is the recommended/default value for this argument

## Returns
The getPercentPageViewed plug-in returns nothing; instead, it sets the following variables within the AppMeasurement object:
* s._ppvPreviousPage = The name of the previous page viewed (As final scrolling measurements for the current page aren't available until after a **new** page loads)
* s._ppvHighestPercentViewed = The highest percent of the previous page that the visitor viewed (height-wise); in other words, the furthest point that the visitor scrolled down to on the previous page
* s._ppvInitialPercentViewed = The percent of the previous page that was visible when the previous page first loaded
* s._ppvHighestPixelsSeen = The highest number of total pixels seen (height-wise) as the visitor scrolled down the previous page
* s._ppvFoldsSeen = The highest number of "page folds" that were reached as the visitor scrolled down the previous page (including the "top-of-page" fold)
* s._ppvFoldsAvailable = The number of total "page folds" that were available to scroll down on the previous page

## Cookies
The getPercentPageViewed plug-in creates a first-party cookie, called s_ppv, that is passed from page to page.  The contents of the cookie contain the values inserted in the four variables described above and expires at the end of the session.

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

### v4.0 (October 7, 2019)

* Added `s._ppvFoldsSeen` and `s._ppvFoldsAvailable` solutions

### v3.01 (August 13, 2018)

* Fixed an issue for pages that have multiple AppMeasurement objects on a page

### v3.0 (April 13, 2018)

* Point release (recompiled, smaller code size)
* Plug-in now creates variables to be assigned to Adobe Analytics variables instead of return values
