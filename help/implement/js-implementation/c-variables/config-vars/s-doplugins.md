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
