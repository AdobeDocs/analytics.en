---
description: The getVisitNum plug-in determines how many visits a user has made to your site and captures this number in a Analytics variable.
keywords: Analytics Implementation
seo-description: The getVisitNum plug-in determines how many visits a user has made to your site and captures this number in a Analytics variable.
seo-title: getVisitNum
solution: Analytics
subtopic: Plug-ins
title: getVisitNum
topic: Developer and implementation
uuid: cd2c3e09-bd13-42e3-a7be-d6409fa2c188
index: y
internal: n
snippet: y
---

# getVisitNum

The getVisitNum plug-in determines how many visits a user has made to your site and captures this number in a Analytics variable.

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**: No changes required for this section.

**Plug-in Configuration**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Choose one Custom Traffic (s.prop) variable or one Custom Conversion (s.eVar) variable for use in capturing visit number data. This should be a variable that has been enabled using the Admin Console, but which is not currently in use for another purpose. You can use the following example and update it based on your requirements.

`s.prop1=s.getVisitNum();`

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

**PLUGINS SECTION**: Add the following code to the area of the [!DNL s_code.js] file labeled PLUGINS SECTION. Do not make any changes to this portion of the plug-in code.

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**Parameters**

* tp = (string, optional) Tracking period. use "d" for day, "w" for week, "m" for month, or a number for a custom number of days.

    * If day, week, or month is selected then the visit number will reset at the end of the day/week/month. 
    * If a custom number of days is selected then the visit number will reset after that number of days. 
    * If no value is provided then "m" will be used.

* c = (string, optional) Specify the persistent cookie name. Default is 's_vnum'. 
* c2 = (string, optional) Specify the session cookie name. Default is 's_invisit'

**Returns**

* returns the visit number (1,2,3,etc) of the visit. This number is incremented only on the first page of each visit. 
* returns "unknown visit number" if the plug-in is unable to identify the visit number (cookies are blocked).

**Examples**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**Notes**

* Always test plug-in installations extensively to ensure that data collection is as expected before deploying in a production environment. 
* This plug-in relies on the ability to set cookies in the user's web browser. If the user does not accept cookies, all visits will appear to be first visits.

