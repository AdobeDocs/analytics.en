---
description: JavaScript plug-ins are usually called by the doPlugins function, which is executed when the t() function is called in the Code to Paste.
keywords: Analytics Implementation
seo-description: JavaScript plug-ins are usually called by the doPlugins function, which is executed when the t() function is called in the Code to Paste.
seo-title: Call plug-ins with doPlugins function
solution: Analytics
subtopic: Plug-ins
title: Call plug-ins with doPlugins function
topic: Developer and implementation
uuid: 29e7d9ac-0054-486b-bd10-fa98cf7f1bdb
index: y
internal: n
snippet: y
---

# Call plug-ins with doPlugins function

JavaScript plug-ins are usually called by the doPlugins function, which is executed when the t() function is called in the Code to Paste.

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. The only time the *`doPlugins`* function is not called is when the [!UICONTROL usePlugins] variable is set to 'false.'

## Code Example {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

AppMeasurement for JavaScript:

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

H code:

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>H code and earlier versions use a different syntax to support some very old browsers (such as IE 4 and 5).

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

The *`doPlugins`* function is typically called *`s_doPlugins`*. In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 

```

## Using doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

The *`doPlugins`* function provides an easy way to give default values to variables or to take values from [!UICONTROL query string parameters] on any page of the site. Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. Keep in mind that changes to the JavaScript file are not always immediate. Return visitors to your site are often using cached versions of the JavaScript file. This means that updates to the file may not be applied to all visitors for up to one month after the change is made.

The following example shows how the *`doPlugins`* function can be used to set a default value for a variable and to get a value from the query string.

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 

```

## Installed Plug-ins {#section_C5494347D85940A78670032199787CD0}

To find out whether a plug-in is included in your JavaScript file and ready for use, look in the [!UICONTROL Plugins Section] of the JavaScript file. The following example shows the [!UICONTROL getQueryParam] function.

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 

```

