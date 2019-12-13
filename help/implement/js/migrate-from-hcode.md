---
description: The following table contains a list of tasks you need to perform to migrate your implementation.
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
subtopic: JavaScript AppMeasurement
title: Migrating to AppMeasurement for JavaScript
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
---

# Migrating to AppMeasurement for JavaScript

The following table contains a list of tasks you need to perform to migrate your implementation.

>[!NOTE]
>
>We recommend migrating to the [Identity Service](/help/implement/js-implementation/c-unique-visitors/visid-service.md) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) Check plug-in compatibility

Where: s\_code.js

Some plug-ins are no longer supported. See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) .

![](assets/step2_icon.png) Download the new AppMeasurement

Where: Admin > Code Manager

The download zip contains a minified AppMeasurement.js file, and Javascript files for the Media and Integrate modules.

![](assets/step3_icon.png) Copy your s\_code.js customization to `AppMeasurement.js`.

Where: s\_code.js and AppMeasurement.js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (Optional) Update plug-ins

Where: AppMeasurement.js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md).

![](assets/step5_icon.png) (Optional) Update Media and Integrate modules

Where: AppMeasurement.js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Deploy new JavaScript

Where: Your website

The new JavaScript file can be deployed according to your standard process. Your existing page code is compatible with this version.

## Example page code and global configuration

This section contains example code for your core JavaScript file and the pages on your site.

>[!IMPORTANT]
>
>This example uses the visitor ID service, which is deployed as part of your [JavaScript Implementation](/help/implement/js-implementation/javascript-implementation-overview.md). Enabling the visitor ID service in AppMeasurement before you have included the Visitor API JavaScript file on all site pages could result in duplicate visitor counts. To avoid duplicate visitor counts, make sure that you understand and follow the process described in [Visitor ID Service](/help/implement/js-implementation/c-unique-visitors/visid-service.md).

### Example AppMeasurement.js Code {#section_4351543F2D6049218E18B48769D471E2}

>[!IMPORTANT]
>
>Configuration variables should be set above the *`doPlugins`* function.

For new implementations, you can paste the following global configuration code at the beginning of AppMeasurement.js to get started:

```js
//initialize AppMeasurement 
var s_account="INSERT-RSID-HERE" 
var s=s_gi(s_account) 
 
/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/ 
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE") 
 
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
 
/* uncomment below to use doPlugins */ 
/* s.usePlugins=true 
function s_doPlugins(s) { 
 
// use implementation plug-ins that are defined below 
// in this section. For example, if you copied the append 
// list plug-in code below, you could call: 
// s.events=s.apl(s.events,"event1",",",1); 
 
} 
s.doPlugins=s_doPlugins */ 
 
/* WARNING: Changing any of the below variables will cause drastic 
changes to how your visitor data is collected.  Changes should only be 
made when instructed to do so by your account manager.*/ 
s.trackingServer="INSERT-TRACKING-SERVER-HERE" 
s.trackingServerSecure="INSERT-SECURE-TRACKING-SERVER-HERE" 
 
/************************** PLUGINS SECTION *************************/ 
 
// copy and paste implementation plug-ins here - See "Implementation Plug-ins" @ 
// https://marketing.adobe.com/resources/help/en_US/sc/implement/#Implementation_Plugins 
// Plug-ins can then be used in the s_doPlugins(s) function above  
 
/****************************** MODULES *****************************/ 
 
// copy and paste implementation modules (Media, Integrate) here 
// AppMeasurement_Module_Media.js - Media Module, included in AppMeasurement zip 
// AppMeasurement_Module_Integrate.js - Integrate Module, included in AppMeasurement zip 
 
/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  

```

### Example Page Code {#section_042412C29CC249E298F19B2BC2F43CE7}

For new implementations, you can paste the following page code just after the opening <body> tag on pages you want to track:

```js
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
var s_code=s.t();if(s_code)document.write(s_code)//--></script>
```

Make sure that you have also included a reference to `AppMeasurement.js` and `VisitorAPI.js` on each page. See [JavaScript Implementation](/help/implement/js-implementation/javascript-implementation-overview.md) for instructions.

## AppMeasurement plug-in support

Plug-in support in the current version of JavaScript AppMeasurement.

## Tested Plug-ins {#section_48415FB895E6455FAC34B0B96DE6EBE7}

The following plug-ins were tested and verified as compatible:

* [s.abort flag](/help/implement/js-implementation/plugins/abort.md)
* [appendList](/help/implement/js-implementation/plugins/appendlist.md) 
* [doPlugins function](/help/implement/js-implementation/plugins/function-doplugins.md)
* [getAndPersistValue](/help/implement/js-implementation/plugins/getandpersistvalue.md)
* [getDaysSinceLastVisit](/help/implement/js-implementation/plugins/getdayssincelastvisit.md)
* [getLoadTime](/help/implement/js-implementation/plugins/getloadtime.md)
* [getNewRepeat](/help/implement/js-implementation/plugins/getnewrepeat.md) 
* [getPageVisibility](/help/implement/js-implementation/plugins/pagevisibility.md)
* [getPercentPageViewed](/help/implement/js-implementation/plugins/getpercentpageviewed.md)
* [getPreviousValue](/help/implement/js-implementation/plugins/getpreviousvalue.md)
* [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md)
* [getTimeParting](/help/implement/js-implementation/plugins/gettimeparting.md)
* [getValOnce](/help/implement/js-implementation/plugins/getvalonce.md)
* [getVisitNum](/help/implement/js-implementation/plugins/getvisitnum.md)
* [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md)
* [hitGovernor](/help/implement/js-implementation/plugins/hitgovernor.md)
* [Internal Traffic](/help/implement/js-implementation/plugins/internal-traffic.md)
* [performanceTiming](/help/implement/js-implementation/plugins/performancetiming.md)
* [trackTNT](/help/implement/js-implementation/plugins/tracktnt.md)
