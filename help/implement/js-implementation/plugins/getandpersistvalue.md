---
description: The getAndPersistValue plug-in obtains a value of your choosing and populates it into a Analytics variable for a determined period. A common use is to see how many page views a campaign generates after a click-through, which enables you to easily see the most common pages for each campaign.
keywords: Analytics Implementation
seo-description: The getAndPersistValue plug-in obtains a value of your choosing and populates it into a Analytics variable for a determined period. A common use is to see how many page views a campaign generates after a click-through, which enables you to easily see the most common pages for each campaign.
seo-title: getAndPersistValue
solution: Analytics
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
---

# getAndPersistValue

The getAndPersistValue plug-in obtains a value of your choosing and populates it into a Analytics variable for a determined period. A common use is to see how many page views a campaign generates after a click-through, which enables you to easily see the most common pages for each campaign.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. This example lets you determine how many page views the tracking code generated as a result of the original click-through.

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**: No changes required for this section.

**Plug-in Configuration**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Choose one Custom Traffic (s.prop) variable or one Custom Conversion (s.eVar) variable for use in capturing persisted value data. This should be a variable that has been enabled using the Admin Console, but which is not currently in use for any other purpose. You can use the following example and update it based on your requirements.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* has three arguments:

1. Currently populated variable or value to persist ( *`s.campaign`* shown above). 
1. Cookie name, used to store the value ( *`s_getval`* shown above). 
1. Period of time for persistence, in days. "30" as shown above would cause the value to be populated into the selected variable on every page view made by the user for the next 30 days. If omitted, the setting defaults to *session*.

**PLUGINS SECTION**: Add the following code to the area of the [!DNL s_code.js] file labeled PLUGINS SECTION. Do not make any changes to this portion of the plug-in code.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Always test plug-in installations extensively to ensure that data collection is as expected before deploying in a production environment. 
