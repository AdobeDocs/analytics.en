---
description: Captures the value of a Analytics variable on the next page view. For example, you can use plug-in to capture the s.pageName value from the previous page view into a Custom Traffic variable. It also has an option to capture a previous value only when designated success events are set.
keywords: Analytics Implementation
seo-description: Captures the value of a Analytics variable on the next page view. For example, you can use plug-in to capture the s.pageName value from the previous page view into a Custom Traffic variable. It also has an option to capture a previous value only when designated success events are set.
seo-title: getPreviousValue
solution: Analytics
subtopic: Plug-ins
title: getPreviousValue
topic: Developer and implementation
uuid: 20da7b4a-9820-4690-a1cc-d10b6dd627a7
---

# getPreviousValue

Captures the value of a Analytics variable on the next page view. For example, you can use plug-in to capture the s.pageName value from the previous page view into a Custom Traffic variable. It also has an option to capture a previous value only when designated success events are set.

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**: No changes required for this section.

**Plug-in Configuration**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Choose one Custom Traffic (s.prop) variable or one Custom Conversion (s.eVar) variable for use in capturing persisted value data. This should be a variable that has been enabled using the Admin Console, but which is not currently in use for any other purpose. You can use the following example and update it based on your requirements.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* has three arguments:

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). When left blank or omitted, the plug-in captures the previous value on all page views.

**PLUGINS SECTION**: Add the following code to the area of the [!DNL s_code.js] file labeled PLUGINS SECTION. Do not make any changes to this portion of the plug-in code.

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 

```

**Notes**

* Always test plug-in installations extensively to ensure that data collection is as expected before deploying in a production environment.
* If no value is present for the selected variable on any given page, the text *no value* will be set in the cookie.
* A fixed 30-minute cookie expiration is now set for each cookie, and refreshed with each page load. The plug-in works for the length of a visit.
* Because the function must be called as part of the plug-ins section of code, the code runs each time *`s.t()`* or *`s.tl()`* is called.

* The chosen variable should be populated with a value prior to the call to *`s.getPreviousValue`*. Because the *`s_doPlugins()`* function is executed after the variables on the page are populated, this issue rarely occurs. It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.

