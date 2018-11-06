---
description: Analytics provides a number of variables to collect Analytics data. For example, the value in the pageName variable is the name of the Web page being reported. This section lists the variables that are supported by AppMeasurment.
keywords: Analytics Implementation;appmeasurement variables
seo-description: Analytics provides a number of variables to collect Analytics data. For example, the value in the pageName variable is the name of the Web page being reported. This section lists the variables that are supported by AppMeasurment.
seo-title: Overview of variables
solution: Analytics
subtopic: Variables
title: Overview of variables
topic: Developer and implementation
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
index: y
internal: n
snippet: y
---

# Overview of variables

Analytics provides a number of variables to collect Analytics data. For example, the value in the pageName variable is the name of the Web page being reported. This section lists the variables that are supported by AppMeasurment.

For a listing of how each variable appears in Analytics reports, see [Variables - How They Are Used in Reporting](https://marketing.adobe.com/resources/help/en_US/reference/?f=variable_definitions).

<!-- 

<p>The following is for a client issue reported by Gundy on 1/22/16 in an email "Documentation and JavaScript Update Request". This may be a KB issue. Awaiting word from Russ. - Blake </p>

 -->

## How to Set Variables {#section_E52CF9E8FDF74164A1511E0D9D31884D}

AppMeasurement requires that all configuration variables be set before the initial call to the track function, *`t()`*. If configuration variables are set after the call to *`t()`*, unexpected results may occur.

Configuration variables are set inside the *`doPlugins`* function, which is called during the execution of the track function. The specific configuration variable causing this issue is *`trackInlineStats`*, which enables ClickMap data collection. This leaves the ClickMap module in an indeterminate state, which results in the first tracking call appending the string "undefined" to the Adobe Analytics beacon, affecting the currency code.

To resolve this issue, move all configuration variables above the doPlugins function.

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at http://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 

```

