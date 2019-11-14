---
description: The getValOnce plug-in prevents a given variable from being set to the previously defined value. It uses a cookie to determine a variable's last seen value. If the current value matches the cookie value, the variable is overwritten with a blank string before it is sent to Adobe's processing servers. This plug-in is useful to prevent conversion variable instance inflation caused when users refresh the page or click the Back button.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getValOnce
topic: Developer and implementation
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
---

# getValOnce

The getValOnce plug-in prevents a given variable from being set to the previously defined value. It uses a cookie to determine a variable's last seen value. If the current value matches the cookie value, the variable is overwritten with a blank string before it is sent to Adobe's processing servers. This plug-in is useful to prevent conversion variable instance inflation caused when users refresh the page or click the Back button.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

**Parameters**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **Variable:** The variable that will be checked. This is typically the same as the variable being defined.
* **Cookie:** The name of the cookie that stores the previous value to compare against. The cookie can be any value.
* (Optional) **Expiration:** The number of days the cookie will expire. If not set or set to 0, the default expiration is the browser session.
* (Optional) **Minute:** If you set this to the string value *`m`*, the expiration value is defined in minutes instead of days. If not set, *`days`* is the default expiration.

**Properties**

* This plug-in is commonly used on conversion variables. However, you can use it on any [!DNL Analytics] variable.
* When Javascript encounters this function, it compares the defined value to what is stored in the cookie. If the defined value is different from the cookie value, the defined value is set. If the defined value is the same as the cookie value, an empty string is returned.
* The cookie can only store a single value, meaning the plug-in only looks as the last defined value.
* The plug-in does not stop all values from defining the variable after it is defined. The plug-in only prevents the last value from being set multiple times consecutively.
* If the end user blocks or rejects cookies, the original value is always returned.
* The plug-in's session is different from what [!DNL Analytics] defines as a session (or visit). [!DNL Analytics] terminates a session after 12 hours of activity or 30 minutes of inactivity. Because the plug-in uses the browser's session definition, it is terminated only after the user closes the tab or exits the browser.

    * If a user closes your page, opens a different tab and navigates back to your site within 30 minutes, the plug-in creates a new session while keeping the [!DNL Analytics] visit open.
    * If a user keeps the browser window open without clicking on a link for more than 30 minutes, the [!DNL Analytics] visit expires while keeping the browser session open.

> [!NOTE] The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Implementation {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

> [!NOTE] If your organization uses Marketing Channels and has rules set up based on `s.campaign`, it is recommended that you not use the getValOnce plugin when setting the `s.campaign`value. Doing so could lead to an incorrect channel being assigned on a secondary campaign click-through.

To implement this plug-in, place the following code within your [!DNL s_code.js] file

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Once the above code is implemented, define the desired variable using the *`getValOnce`* function. The following are several examples on how it can be implemented:

**Preventing the same campaign value from being defined if a duplicate value is detected within 30 days of cookie being set:** 
`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`  **Prevents the same eVar1 value from being defined if a duplicate value is detected within 30 minutes of the cookie being set:** 
`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`  **Prevents the same eVar2 value from being defined multiple times in the same browser session:** 
`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`  **Notes**

* Always test plug-in installations extensively to ensure that data collection is as expected before deploying in a production environment.
* Make sure you delete the cookie or use new, unique values during testing or variables will not be sent.

