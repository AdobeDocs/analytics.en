---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---


# s.doPlugins

The  variable is a reference to the  function, and allows the  function to be called at the appropriate location within the JavaScript file.

The *`s_doPlugins`* function is called each time any of the following occurs:

* The *`t()`* function is called 
* The *`tl()`* function is called 
* An exit or download link is clicked 
* Any page element being tracked by visitor click map is clicked

The *`doPlugins`* function is used to run customized routines to gather or alter data. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

## Syntax and Possible Values

The *`s_doPlugins`* function should not be in quotes, and *`doPlugins`* should always be assigned to the exact name of the *`s_doPlugins`* function (if that function is renamed).

```js
s.doPlugins=s_doPlugins;
```

## Examples

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* The only reason to change the object name (such as from s to s_mc) is if you share content with or pull content from other customers. Renaming the *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. While the best solution is to use a different object name than other JavaScript files on the same page, doing so is not required.

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


