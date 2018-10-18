---
description: Records the number of seconds your page was the active tab within the browser, and passes that value into a metric on the next page view.
keywords: Analytics Implementation
seo-description: Records the number of seconds your page was the active tab within the browser, and passes that value into a metric on the next page view.
seo-title: getPageVisibility
solution: Analytics
title: getPageVisibility
topic: Developer and implementation
uuid: caa90cee-6a13-456f-a870-d0016ff62b6f
index: y
internal: n
snippet: y
---

# getPageVisibility

Records the number of seconds your page was the active tab within the browser, and passes that value into a metric on the next page view.

>[!NOTE]
>
>This is a beta version of the plugin, and additional updates may be forthcoming.

This plug-in requires [getVisitStart](../../js_implementation/c_mplementation_plug-ins/getVisitStart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

This plug-in also records the total seconds the page was within the browser (both active and passive viewing time). It is required to use the getPreviousValue plug-in in order to track the previous page name associated with the page visibility events. Tracking these values helps you better understand visitor engagement and more accurately track visitor behavior on your sites.

It is required that you use the getPreviousValue plug-in to track the previous page name associated with the page visibility events. Tracking these values helps you better understand visitor engagement and more accurately track visitor behavior on your sites.

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing Analytics. This plug-in is compatible only with AppMeasurement tracking libraries.

## Required Supporting Plug-ins {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList 
* getPreviousValue 
* getVisitStart

## Plug-in Code and Implementation {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Config Section**

The `s.pvel` variable should contain the three events you wish to use: 

|  Event  | Definition  |
|---|---|
|  Total Page Visibility Seconds (Numeric)  | The amount of time the page was active within the browser  |
|  Total Page Seconds (Numeric)  | The amount of time the page was loaded in the browser, regardless of its visibility state  |
|  Total Page Visibility Instances (Counter)  | The total number of times a value was recorded for the previous two events  |

**Sample Calls**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 

```

**doPlugins Section**

To initialize the plug-in, two lines of code are required in the `doPlugins` section of your s_code, preferably after you have designated the `s.pageName` variable.

**Sample Calls**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 

```

**Plug-ins Section**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 

```

## Notes {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* Always test plug-in installations to ensure that data collection is as expected before deploying in a production environment. 
* Because the plug-in passes the page visibility seconds and total seconds as they are associated with the previous page, data is not collected for the final page view of the visit. 
* This plug-in relies on the ability to set cookies in the user's web browser. If the user does not accept first-party cookies, the plug-in will not pass data into Analytics. 
* The plug-in creates its own first-party cookies named `s_tps` and `s_pvs`. 

* A very small percentage of users will not pass percentage of page viewed data due to browser limitations, and logic is contained within the plugin to ensure that the data is not skewed as a result. However, this plug-in has been successfully tested in IE, Firefox, Chrome, and Safari. 
* Due to the way the plugin measures total seconds and associates that value with the previous page name, there will be differences between default time spent on page metrics and total seconds metrics. 
* Calculated metrics can be created to aid in summarizing and understanding visitor behavior associated with these metrics:

    * **Page Visibility Ratio **(Total Page Visibility Seconds / Total Page Seconds) 
    * **Total Hidden Seconds **(Total Page Seconds - Total Page Visibility Seconds) 
    * ** Average Page Visibility Seconds **(Total Page Visibility Seconds/Total Page Visibility Instances) 
    * **Average Page Hidden Seconds** ((Total Page Seconds - Total Page Visibility Seconds)/Total Page Visibility Instances)

* Due to the way the plug-in rounds up the seconds, there can be a 1-2 second difference between the total page visibility seconds and total seconds, with total seconds being higher. (To be resolved in a future update) 
* Using the getVisitStart plug-in should account for visitors that have a new visit start after a period of 30+ minutes of inactivity. This is not working as designed; however, there will likely be a workaround when we incorporate the “total active seconds” in a future iteration of the plug-in.

## Frequently Asked Questions {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**Will this plug-in make additional server calls? **

The plugin will only record page visibility values on subsequent page view server calls. No additional server calls are used in conjunction with it.

**If I do not want to capture total page seconds or total page visibility instances, can I leave those out of the event list? **

Yes, the total page seconds and total visibility instances are optional events and can be left out of the list if desired.

**Will the events captured make sense if I use them in reports other than the Previous Page Name? **

Since the plugin records values on the subsequent image request only other eVars that have been captured in a ‘previous page’ context could be applied, i.e. ‘Previous Page URL’.

**Will the plug-in send the visibility time on an s.tl() call, or only on an s.t() call?**

The visibility time is only recorded with s.t() calls. 
