---
description: Gets the page load time in tenths of a second and lets you store the value in a prop, eVar, and/or a numeric event.
keywords: Analytics Implementation
seo-description: Gets the page load time in tenths of a second and lets you store the value in a prop, eVar, and/or a numeric event.
seo-title: getLoadTime
solution: Analytics
title: getLoadTime
topic: Developer and implementation
uuid: 5d26a69b-cbde-4be1-bac1-5ee8a4e55ca3
---

# getLoadTime

Gets the page load time in tenths of a second and lets you store the value in a prop, eVar, and/or a numeric event.

To use this plugin, you insert the function code, then call the function twice in your [!DNL s_code.js] file. Once at the beginning of the file, and then again in the `doPlugins` section. This plugin is intentionally not defined as a method of the s object. Doing so would have added to the calculated page load time.

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_968AC379C3004C359A85AFED5A48D5AE}

**Add the function**

Add the following definition of the `s_getLoadTime` function in [!DNL s_code.js], anywhere before the "DO NOT ALTER ANYTHING BELOW THIS LINE" section:

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Make the initial function call**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**Make the final function call**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

Usage Example 1 - Save the page load time in prop10 and eVar20:

```js
s.eVar20=s.prop10=s_getLoadTime();
```

Usage Example 2 - Save the page load time in numeric event99:

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(Optional) Add support for older browsers**

To support older browsers that don't provide the [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/) property, include the following line in the HEAD section of the page's HTML near the beginning and prior to invoking .js, .css, or other files:

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

