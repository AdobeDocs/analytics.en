---
description: Determines whether a visitor is a new visitor or a repeat visitor, and captures this information in a Analytics variable.
keywords: Analytics Implementation
seo-description: Determines whether a visitor is a new visitor or a repeat visitor, and captures this information in a Analytics variable.
seo-title: getNewRepeat
solution: Analytics
subtopic: Plug-ins
title: getNewRepeat
topic: Developer and implementation
uuid: e3e9f362-e0b1-4a2b-bb5b-98eddaa0a7f4
---

# getNewRepeat

Determines whether a visitor is a new visitor or a repeat visitor, and captures this information in a Analytics variable.

Use this plug-in to answer the following questions:

* What percentage of my visitors are new (as opposed to repeat) visitors? 
* Do return visitors generate higher conversion per capita than new visitors? What is this ratio? 
* Do my marketing campaigns cause persistence across visits? For example, do users who click through my campaigns then return later?

> [!NOTE] The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**: No changes required for this section.

**Plug-in Configuration**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Choose one Custom Traffic (s.prop) variable or one Custom Conversion (s.eVar) variable for use in capturing persisted value data. This should be a variable that has been enabled using the Admin Console, but which is not currently in use for any other purpose. You can use the following example and update it based on your requirements.

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* has two optional arguments:

1. The first optional argument is the number of days that the cookie should last. The default value if this argument is omitted is 30 days.
1. The second optional argument is the cookie name. A default value is used if this argument is omitted.

**PLUGINS SECTION**: Add the following code to the area of the [!DNL s_code.js] file labeled PLUGINS SECTION. Do not make any changes to this portion of the plug-in code.

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

Always test plug-in installations extensively to ensure that data collection is as expected before deploying in a production environment.
