---
description: Determines the number of days since a user last visited your site, and captures this information in a Analytics variable.
keywords: Analytics Implementation
seo-description: Determines the number of days since a user last visited your site, and captures this information in a Analytics variable.
seo-title: getDaysSinceLastVisit
solution: Analytics
subtopic: Plug-ins
title: getDaysSinceLastVisit
topic: Developer and implementation
uuid: cad95882-3bd0-4f94-a0c3-4e7b6058d246
---

# getDaysSinceLastVisit

Determines the number of days since a user last visited your site, and captures this information in a Analytics variable.

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) now includes a **[!UICONTROL Days since last visit]** dimension out of the box, thereby nullifying the need for this plugin.

This return frequency data can be used to answer the following questions:

* How frequently do users revisit my site? 
* How does return frequency correlate with conversion? Do repeat buyers visit frequently or infrequently? 
* Do users who click through my campaigns then return frequently?

The plug-in can also generate values used for segmentation. For example, you can create a segment to view all of the data for only those visits that were preceded by 30 or more days of non-visitation by the user.

> [!NOTE] The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_5600DBB819F143D59527A73BD94418DE}

**CONFIG SECTION**

No changes required.

**Plugin Config**

Place the following code within the `s_doPlugins()` function, which is located in the area of the [!DNL s_code.js] file labeled *Plugin Config*. Choose one Custom Traffic (s.prop) variable and/or one Custom Converesion (s.eVar) variable for use in capturing return frequency data. This selection should be a variable that has been enabled using the Admin Console but is not currently in use for any other purpose. The following is given as an example, and should be updated appropriately based on your needs.

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**PLUGINS SECTION** 
Add the following code to the area of the [!DNL s_code.js] file labeled *PLUGINS SECTION*. Do not make any changes to this portion of the plug-in code.

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**Notes**

* Always test plug-in installations extensively to ensure that data collection is as expected before deploying in a production environment.
* The plug-in categorizes users by return frequency into the following groups:

    * First Visit 
    * Less than 1 day 
    * Less than 7 days 
    * More than 7 days 
    * More than 30 days

* This plug-in relies on cookies to flag a user has having visited previously. If the browser does not accept cookies, the plug-in returns a value of *Cookies Not Supported*.

