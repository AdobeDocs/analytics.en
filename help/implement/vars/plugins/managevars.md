---
title: manageVars
description: Alter the values of more than one Analytics variable at a time.
feature: Variables
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
---
# Adobe plug-in: manageVars

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `manageVars` plug-in allows you to manipulate the values of multiple Analytics variables at once. You can also set values to lowercase or remove unnecessary characters from multiple variable values at the same time. Adobe recommends using this plug-in if you want to clean up the value of multiple variables at once.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize manageVars
1. Save and publish the changes to the rule.-->

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `manageVars` function uses the following arguments:

* **`cb`** (required, string): The name of a callback function that the plug-in uses to manipulate the Analytics variables. You can use an Adobe function like `cleanStr` or your own custom function.
* **`l`** (optional, string): A comma-delimited list of Analytics variables that you want to manipulate. Defaults to ALL Adobe Analytics variables when not set, which includes:
  * `pageName`
  * `purchaseID`
  * `channel`
  * `server`
  * `pageType`
  * `campaign`
  * `state`
  * `zip`
  * `events`
  * `products`
  * `transactionID`
  * All props
  * All eVars
  * All hierarchy variables
  * All list variables
  * All context data variables
* **`Il`** (optional, boolean): Set to `false` if you want to *exclude* the list of variables declared in the `l` argument instead of including them. Defaults to `true`.

Calling this function returns nothing. Instead it changes the values of Analytics variables based on the desired callback function.

## Example Calls

### Example #1

The following code...

```js
manageVars("lowerCaseVars");
```

...changes the values of all the variables described above to lowercased versions.  The sole exception to this is the events variable, as some of the events (e.g. scAdd, scCheckout, etc.) are case-sensitive and should not be lowercased

### Example #2

The following code...

```js
manageVars("lowerCaseVars", "events", false);
```

...essentially produces the exact same result as the first example since the events variable isn't lowercased by default.

### Example #3

The following code...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...will change (e.g. lowercase) only the values of eVar1, eVar2, eVar3, and list2

### Example #4

The following code...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...will change (e.g. lowercase) the values of all the variables described above EXCEPT for eVar1, eVar2, eVar3, and list2

### Example #5

The following code...

```js
manageVars("cleanStr");
```

...changes the values of all the variables described above, including the events variables.  Specifically, the cleanStr callback function does the following to each variables' value:

* Removes HTML encoding
* Removes whitespaces found at the beginning and end of the value
* Replaces left/right single quotes (e.g. ’) with a straight single quote (')
* Replaces tab characters, newline characters, and carriage return characters with spaces
* Replaces all double (or triple, etc.) spaces with single spaces

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.1 (January 14, 2019)

* Bug fix for Internet Explorer 11 browsers.
* Changes for `s.cleanStr`, which now uses the regular `cleanStr` function.

### 2.0 (May 7, 2018)

* Point release (including complete reanalysis/rewrite of plug-in)
* Added `cleanStr` callback function
