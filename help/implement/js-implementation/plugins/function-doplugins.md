---
description: JavaScript plug-ins are usually called by the doPlugins function, which is executed when the t() function is called in the Code to Paste.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: doPlugins Function
topic: Developer and implementation
uuid: 367d5550-f8e2-477d-8681-18ae9665d699
---

# doPlugins Function

JavaScript plug-ins are usually called by the doPlugins function, which is executed when the t() function is called in the Code to Paste.

Consequently, if you set a variable in the `doPlugins` function, you may overwrite a variable you set on the HTML page. The only time the `doPlugins` function is not called is when the *`usePlugins`* variable is set to `false`.

**Code Example**

The `doPlugins` function is typically called `s_doPlugins`. However, in certain circumstances (usually when more than one version of [!DNL Analytics] code may appear on a single page), you can change the `doPlugins` function name. If the standard `doPlugins` function needs to be renamed to avoid conflicts, assign `doPlugins` the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**Using doPlugins**

This function provides an easy way to give default values to variables, or to take values from query string parameters on any page of the site. Using `doPlugins` can be easier than populating the values in the HTML page, because only one file must be updated. Changes to the JavaScript file are not always immediate. Return visitors to your site are often using cached versions of the JavaScript file. Meaning, updates to the file may not be applied to all visitors for up to one month after the change is made.

The following examples show how you can use the `doPlugins` function to set a default value for a variable and to get a value from the query string.

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**Installed Plug-ins**

To find out whether a plugin is included in your JavaScript file and ready for use, look in the [!UICONTROL Plugins Section] of the JavaScript file. The following example shows what the `getQueryParam` function looks like in the [!UICONTROL Plugins Section].

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ...
// 

```

