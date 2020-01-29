---
description: This plug-in operates by using the Navigation Timing JavaScript API for accurately measuring performance on the web. This provides a native method to get accurate and detailed timing statistics for page load events & asset load times. Previously, measurements of this sort have either utilized the JavaScript Date object for timing metrics, or a rudimentary extrapolation of the Navigation Timing metrics. Both methodologies, even though they provide some trended data for page load times, are unreliable.
keywords: Analytics Implementation
title: performanceTiming
topic: Developer and implementation
uuid: ab2a6c51-8791-41e7-9bea-c1ce8d312de8
---

# performanceTiming

This plug-in operates by using the Navigation Timing JavaScript API for accurately measuring performance on the web. This provides a native method to get accurate and detailed timing statistics for page load events & asset load times. Previously, measurements of this sort have either utilized the JavaScript Date object for timing metrics, or a rudimentary extrapolation of the Navigation Timing metrics. Both methodologies, even though they provide some trended data for page load times, are unreliable.

## What This Plug-In Does {#section_4E0771B959FD4F86B4B91BD18CA01DF1}

>[!IMPORTANT]
>
>This is a beta version of the plugin, and additional updates may be forthcoming.

This plug-in utilizes the following detailed events to track the individual timing components of a page load: 

|  Event  | Name  | Calculated From  |
|---|---|---|
|  1  | Redirect Timing  | fetchStart - navigationStart  |
|  2  | App Cache Timing  | domainLookupStart - fetchStart  |
|  3  | DNS Timing  | domainLookupEnd - domainLookupStart  |
|  4  | TCP Timing  | connectEnd - connectStart  |
|  5  | Request Timing  | responseStart - connectEnd  |
|  6  | Response Timing  | responseEnd - responseStart  |
|  7  | Processing Timing  | loadEventStart - domLoading  |
|  8  | onLoad Timing  | loadEventEnd - loadEventStart  |
|  9  | Total Page Load Time  | loadEventEnd - navigationStart  |
|  10  | Performance Instances  | Counter  |

The following graph illustrates the timing attributes defined by the PerformanceTiming interface and the PerformanceNavigation interface with or without redirect, respectively.

![](assets/timing-attributes.png)

Full details on the Navigation Timing object can be found here:

[https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface](https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface)

In addition, the plugin can optionally use the performanceEntries object to record the asset name, asset load time start, and asset load time duration details for each individual asset loaded on a given page. A large amount of information is recorded with this plugin, and as such it requires that the DOM storage object is enabled in order to store the page load information between page views. Please be sure that your company's privacy policy allows for the use of the DOM storage object before enabling this functionality. It also requires the use of a listVar to track all assets.

## Required Supporting Plug-Ins {#section_B6447EB6548942EFBC219AEFDC245639}

* appendList 
* getPreviousValue

## Plug-In Code and Implementation {#section_564D77E1CF0E445586D95AD9769CE57D}

> [!NOTE] The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should be done only by a developer with experience using and implementing Adobe Analytics. This plugin is compatible only with [!DNL AppMeasurement] tracking libraries.

**Config Section (before doPlugins):**

`s.pte`: Comma-separated list of events containing the 10 events you wish to use - the individual timing event components (events 1 - 8), the total page load time (event 9), and total performance instances (event 10) - in that specific order.

`s.ptc`: Set to determine whether or not to execute the plugin within doPlugins. Always set to false.

*Sample Calls*

```
s.pte = 'event10,event11,event12,event13,event14,event15,event16,event17,event18,event19' 
//[--------------------------- 1 to 8 ---------------------------][-- 9 --][- 10 -] 
s.ptc = false; 

```

**doPlugins Section:**

To initialize the plug-in, one line of code is required in the `doPlugins` section of your s_code, preferably after you have designated the `s.pageName`variable. If you wish to utilize the asset load time functionality within the plug-in, you must pass in the name of the list variable to be used. Otherwise, only the performance timing entries will be tracked in the events you previously specified in the `s.pte` variable.

> [!NOTE] In order to correlate performance timing entries with pages on your site, you must also initialize the `getPreviousValue` plug-in. We recommend comparing these performance entries with either the previous page name or the previous page URL value.

*Sample Calls*

```
/* Performance Timing */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.performanceTiming('list2')  

```

**Plugins Section:**

Lastly, add the plug-in itself to your JavaScript implementation.

```js
/* Plugin: Performance Timing Tracking - 0.11 BETA */
s.performanceTiming=new Function("v",""
+"var s=this;if(v)s.ptv=v;if(typeof performance!='undefined'){if(perf"
+"ormance.timing.loadEventEnd==0){s.pi=setInterval(function(){s.perfo"
+"rmanceWrite()},250);}if(!s.ptc||s.linkType=='e'){s.performanceRead("
+");}else{s.rfe();s[s.ptv]='';}}");
s.performanceWrite=new Function("",""
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)"
+";try{if(s.c_r('s_ptc')==''&&performance.timing.loadEventEnd>0){try{"
+"var pt=performance.timing;var pta='';pta=s.performanceCheck(pt.fetc"
+"hStart,pt.navigationStart);pta+='^^'+s.performanceCheck(pt.domainLo"
+"okupStart,pt.fetchStart);pta+='^^'+s.performanceCheck(pt.domainLook"
+"upEnd,pt.domainLookupStart);pta+='^^'+s.performanceCheck(pt.connect"
+"End,pt.connectStart);pta+='^^'+s.performanceCheck(pt.responseStart,"
+"pt.connectEnd);pta+='^^'+s.performanceCheck(pt.responseEnd,pt.respo"
+"nseStart);pta+='^^'+s.performanceCheck(pt.loadEventStart,pt.domLoad"
+"ing);pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.loadEventStart"
+");pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.navigationStart);"
+"s.c_w('s_ptc',pta);if(sessionStorage&&navigator.cookieEnabled&&s.pt"
+"v!='undefined'){var pe=performance.getEntries();var tempPe='';for(v"
+"ar i=0;i<pe.length;i++){tempPe+='!';tempPe+=pe[i].name.indexOf('?')"
+">-1?pe[i].name.split('?')[0]:pe[i].name;tempPe+='|'+(Math.round(pe["
+"i].startTime)/1000).toFixed(1)+'|'+(Math.round(pe[i].duration)/1000"
+").toFixed(1)+'|'+pe[i].initiatorType;}sessionStorage.setItem('s_pec"
+"',tempPe);}}catch(err){return;}}}catch(err){return;}");

s.performanceCheck=new Function("a","b",""
+"if(a>=0&&b>=0){if((a-b)<60000&&((a-b)>=0)){return((a-b)/1000).toFix"
+"ed(2);}else{return 600;}}");

s.performanceRead=new Function("",""
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)"
+";var cv=s.c_r('s_ptc');if(s.pte){var ela=s.pte.split(',');}if(cv!='"
+"'){var cva=s.split(cv,'^^');if(cva[1]!=''){for(var x=0;x<(ela.lengt"
+"h-1);x++){s.events=s.apl(s.events,ela[x]+'='+cva[x],',',2);}}s.even"
+"ts=s.apl(s.events,ela[ela.length-1],',',2);}s.linkTrackEvents=s.apl"
+"(s.linkTrackEvents,s.pte,',',2);s.c_w('s_ptc','',0);if(sessionStora"
+"ge&&navigator.cookieEnabled&&s.ptv!='undefined'){s[s.ptv]=sessionSt"
+"orage.getItem('s_pec');sessionStorage.setItem('s_pec','',0);}else{s"
+"[s.ptv]='sessionStorage Unavailable';}s.ptc=true;");

/* Remove from Events 0.1 - Performance Specific,
removes all performance events from s.events once being tracked. */
s.rfe=new Function("",""
+"var s=this;var ea=s.split(s.events,',');var pta=s.split(s.pte,',');"
+"try{for(x in pta){s.events=s.rfl(s.events,pta[x]);s.contextData['ev"
+"ents']=s.events;}}catch(e){return;}");

/* Plugin Utility - RFL (remove from list) 1.0*/
s.rfl=new Function("l","v","d1","d2","ku",""
+"var s=this,R=new Array(),C='',d1=!d1?',':d1,d2=!d2?',':d2,ku=!ku?0:"
+"1;if(!l)return'';L=l.split(d1);for(i=0;i<L.length;i++){if(L[i].inde"
+"xOf(':')>-1){C=L[i].split(':');C[1]=C[0]+':'+C[1];L[i]=C[0];}if(L[i"
+"].indexOf('=')>-1){C=L[i].split('=');C[1]=C[0]+'='+C[1];L[i]=C[0];}"
+"if(L[i]!=v&&C)R.push(C[1]);else if(L[i]!=v)R.push(L[i]);else if(L[i"
+"]==v&&ku){ku=0;if(C)R.push(C[1]);else R.push(L[i]);}C='';}return s."
+"join(R,{delim:d2})");
```

## Notes {#section_131C5D97A0094880AFC3A2BBE0BC9DE4}

* Always test plug-in installations to ensure that data collection is as expected before deploying in a production environment.
* Because the plug-in passes the performance data as they are associated with the previous page, data is not collected for the final page view of the visit.
* If you are tracking asset timing, this plug-in relies on the ability to set DOM storage values in the user's web browser. If the user does not accept cookies and have DOM storage enabled, the plug-in will not pass data into Analytics.
* A very small percentage of users will not pass navigation timing data due to browser limitations, and logic is contained within the plugin to ensure that the data is not skewed as a result - particularly with a small portion of mobile browsers. However, this plug-in has been successfully tested in IE, Firefox, Chrome, and Safari.
* [!UICONTROL Calculated Metrics] should be created to aid in summarizing and understanding visitor behavior associated with these metrics:

    * Average Redirect Timing (Redirect Timing/Performance Timing Instances) 
    * Average App Cache Timing (App Cache Timing/Performance Timing Instances) 
    * Average DNS Timing (DNS Timing/Performance Timing Instances) 
    * Average TCP Timing (TCP Timing/Performance Timing Instances) 
    * Average Request Timing (Request Timing/Performance Timing Instances) 
    * Average Response Timing (Response Timing/Performance Timing Instances) 
    * Average Processing Timing (Processing Timing/Performance Timing Instances) 
    * Average onLoad Timing (onLoad Timing/Performance Timing Instances) 
    * Average Page Load Timing (Total Page Load Time/Performance Timing Instances)

