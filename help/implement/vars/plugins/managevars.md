---
title: manageVars
description: Alter the values of more than one Analytics variable at a time.
---

# Adobe plug-in: manageVars

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `manageVars` plug-in allows you to manipulate the values of multiple Analytics variables at once. You can also set values to lowercase or remove unnecessary characters from multiple variable values at the same time. Adobe recommends using this plug-in if you want to clean up the value of multiple variables at once.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize manageVars
1. Save and publish the changes to the rule.

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `manageVars` method uses the following arguments:

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

Calling this method returns nothing. Instead it changes the values of Analytics variables based on the desired callback function.

## Example Calls

### Example #1

The following code...

```js
s.manageVars("lowerCaseVars");
```

...changes the values of all the variables described above to lowercased versions.  The sole exception to this is the events variable, as some of the events (e.g. scAdd, scCheckout, etc.) are case-sensitive and should not be lowercased

### Example #2

The following code...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...essentially produces the exact same result as the first example since the events variable isn't lowercased by default.

### Example #3

The following code...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...will change (e.g. lowercase) only the values of eVar1, eVar2, eVar3, and list2

### Example #4

The following code...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...will change (e.g. lowercase) the values of all the variables described above EXCEPT for eVar1, eVar2, eVar3, and list2

### Example #5

The following code...

```js
s.manageVars("cleanStr");
```

...changes the values of all the variables described above, including the events variables.  Specifically, the cleanStr callback function does the following to each variables' value:

* Removes HTML encoding
* Removes whitespaces found at the beginning and end of the value
* Replaces left/right single quotes (e.g. ’) with a straight single quote (')
* Replaces tab characters, newline characters, and carriage return characters with spaces
* Replaces all double (or triple, etc.) spaces with single spaces

## Version History

### 2.1 (January 14, 2019)

* Bug fix for Internet Explorer 11 browsers.
* Changes for `s.cleanStr`, which now uses the regular `cleanStr` function.

### 2.0 (May 7, 2018)

* Point release (including complete reanalysis/rewrite of plug-in)
* Added `cleanStr` callback function
