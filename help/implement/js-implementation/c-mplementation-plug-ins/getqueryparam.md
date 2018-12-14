---
description: Returns the value of a specified query string parameter, if found in the current page URL. Because important data (such as campaign tracking codes, internal search keywords, etc.) is available in the query string on a page, getQueryParam is helps capture the data into Analytics variables.
keywords: Analytics Implementation
seo-description: Returns the value of a specified query string parameter, if found in the current page URL. Because important data (such as campaign tracking codes, internal search keywords, etc.) is available in the query string on a page, getQueryParam is helps capture the data into Analytics variables.
seo-title: getQueryParam
solution: Analytics
subtopic: Plug-ins
title: getQueryParam
topic: Developer and implementation
uuid: ba202756-c728-4ebc-8fd9-5bc29a9f673b
index: y
internal: n
snippet: y
---

# getQueryParam

Returns the value of a specified query string parameter, if found in the current page URL. Because important data (such as campaign tracking codes, internal search keywords, etc.) is available in the query string on a page, getQueryParam is helps capture the data into Analytics variables.

>[!IMPORTANT]
>
>This plug-in is used by H code only. [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) provides this functionality natively using [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

Once installed in your [!DNL AppMeasurement] for JavaScript code, the plug-in is configured by selecting a [!DNL Analytics] variable to populate using data found in the query string, and specifying which query string values to capture. The plug-in detects the specified query string, if present, and populates the chosen variable with its value. If no query string parameter is found with that value, an empty string is returned. If a query string parameter exists but does not have a value (such as param1 in `?param1&param2=value`), the word *`true`* is returned.

>[!NOTE]
>
>The base code for the plug-in must be installed in your [!DNL AppMeasurement] for JavaScript code before the examples below will work.

If you wanted to use *`s.campaign`* to capture campaign tracking codes available as values of the *`cid`* query parameter, you would enter the following in the *`doPlugins()`* function in your [!DNL AppMeasurement] for JavaScript code:

`s.campaign=s.getQueryParam('cid')`

In this example, if the user arrived at a landing page on your site where the URL was [!DNL https://www.yoursite.com/index.html?cid=123456], then *`s.campaign`* would receive a value of *123456*. This could be seen using the [!DNL DigitalPulse] Debugger, which should show *v0=123456* as part of the image request.

>[!NOTE]
>
>The parameter *`cid`* and others are used here as examples. You can replace them with any query string parameters that exist on your site.

The *`getQueryParam`* plug-in has two additional arguments (options) that can be used to capture data into Analytics variables:

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

If *p* is a list of query string parameters and more than one query string parameter is found in the URL, all values are returned in a list separated by the delimiter, *d*, which can be a single character or a string of characters, such as " : " (space-colon-space). If *d* is omitted, no delimiter is used between values. If one query string parameter should take precedence over another, when both are found, use an *if* statement as shown below.

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

As of version *`getQueryParam`* v2.0, the plug-in accepts an optional third argument, *u*, which allows you to specify the URL from which you would like to extract query string parameters. By default (i.e. if this third argument is omitted or left blank), the plug-in uses the page URL. For example, if you would like extract a query string from the referrer, you can use the following code:

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

The flag "f" should be used in this third argument with frames, when the necessary query string parameter is found in the address bar rather than the current frame's URL:

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

When using frames and the *f* parameter, it is recommended that the *`getValOnce`* plug-in be used to prevent the campaign tracking code to be sent with each page view.

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

**Plug-in Code**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```

