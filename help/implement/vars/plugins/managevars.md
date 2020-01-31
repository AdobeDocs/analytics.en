---
title: manageVars
description: Alter the values of more than one Analytics variable at a time
---

# Adobe Experience Cloud Plugin – manageVars

## Purpose of This Plugin

### What does this plugin do?
The manageVars plugin allows you to manipulate the values of multiple Adobe Analytics variables at one time; this version includes specific functionality to lowercase or remove unnecessary characters from multiple variable values at the same time.

### Why should I use this plugin?
You should use the manageVars plugin if you want to easily lowercase or "clean up" the value of multiple Analytics variable values at one time.

### Why shouldn't I use this plugin?
You won't need to use the manageVars plugin if you don't need to manipulate the values of multiple Analytics variables at the same time

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) and the pt plugin to run the manageVars plugin.  However, the manageVars plugin is useless without additional functions that the plugin can call to manipulate multiple variables at the same time; hence, this version includes two "starter" functions that allow you to both lowercase and "clean" multiple variable values at the same time.  The plugin can be "expanded" by creating new functions designed to manipulate multiple variables at the same time.

## How to Deploy

You may use one of the following three methods to deploy the manageVars plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v2.1 (Requires AppMeasurement; also pt plugin/other necessary callback function/plugins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires AppMeasurement; Also Requires the manageVars plugin) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires AppMeasurement and the manageVars/cleanStr plugin) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 (No Prerequisites Required) */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 (Requires AppMeasurement) */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```
**NOTE:** Adding the comments/version numbers of the code to the AppMeasurement file will help Adobe with troubleshooting any potential implementation issues.

### Method #2. Edit the Adobe Analytics Extension as contained within Adobe Experience Platform Launch

* Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
* Click on the desired property.
* Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
* Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
* Open the custom code editor and paste the plug-in code provided above into the edit window.
* Save and publish the changes to the Analytics extension.

### Method #3. Leverage the Common Analytics Plugin extension contained within Adobe Experience Platform Launch

* Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
* Click the desired property.
* Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
* Install (and publish) the "Common Analytics Plugins" extension
* For any Launch Rule that you want to use the plugin in, add an [!UICONTROL action] with the following configuration:
	* Extension: Common Analytics Plugins
	* Action Type: Initialize manageVars
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the manageVars plugin (via JavaScript), be sure to pass in the following arguments:

* **cb** (required, string): The name of a callback function that the plugin will call to manipulate the Adobe Analytics variables.  This version of the plugin includes the "lowerCaseVars" and the "cleanStr" callback functions
* **l** (optional, string): A comma-delimited list of the Adobe Analytics variables that you want to manipulate (or explicitly NOT manipulate per the "il" argument value); defaults to ALL Adobe Analytics variables when not set.  "ALL" Adobe Analytics variables include the following:
	* pageName
	* purchaseID
	* channel
	* server
	* pageType
	* campaign
	* state
	* zip
	* events
	* products
	* transactionID
	* prop1 – prop75
	* eVar1 – eVar250
	* hier1 – hier5
	* list1 – list3
	* All contextData variables
* **Il** (optional, boolean): Set equal to false if you want to exclude the list of variables declared in the l argument from being manipulated by the callback function; defaults to true

## Returns
The manageVars plugin returns nothing, per se, but changes the values of all Adobe Analytics variables per the callback function and the other arguments passed into the variable

## Cookies
The manageVars plugin does not create or use any cookies

## Example Calls

### Example #1
The following code...
```javascript
s.manageVars("lowerCaseVars");
```
...changes the values of all the variables described above to lowercased versions.  The sole exception to this is the events variable, as some of the events (e.g. scAdd, scCheckout, etc.) are case-sensitive and should not be lowercased
### Example #2
The following code...
```javascript
s.manageVars("lowerCaseVars", "events", false);
```
...essentially produces the exact same result as the first example since the events variable isn't lowercased by default.

### Example #3
The following code...
```javascript
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```
...will change (e.g. lowercase) only the values of eVar1, eVar2, eVar3, and list2
### Example #4
The following code...
```javascript
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```
...will change (e.g. lowercase) the values of all the variables described above EXCEPT for eVar1, eVar2, eVar3, and list2
### Example #5
The following code...
```javascript
s.manageVars("cleanStr");
```
...changes the values of all the variables described above, including the events variables.  Specifically, the cleanStr callback function does the following to each variables' value:
* Removes HTML encoding
* Removes whitespaces found at the beginning and end of the value
* Replaces left/right single quotes (e.g. ’) with a straight single quote (')
* Replaces tab characters, newline characters, and carriage return characters with spaces
* Replaces all double (or triple, etc.) spaces with single spaces

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.manageVars=function(cb,l,il)
```
...to this:
```javascript
[objectname].manageVars=function(cb,l,il)
```
Also be sure to change this...
```javascript
s.lowerCaseVars=function(v)
```
...to this:
```javascript
[objectname].lowerCaseVars=function(v)
```
And change this...
```javascript
s.cleanStr=function(b)
```
...to this:
```javascript
[objectname].cleanStr=function(b)
```
And (finally) change this...
```javascript
s.pt=function(l,de,cf,fa)
```
...to this:
```javascript
[objectname].pt=function(l,de,cf,fa)
```

## Version History

### 2.1 (2019-01-14)
* Bug fix for Internet Explorer 11 Browsers
* Changes for s.cleanStr, which now uses the regular cleanStr function as its base
### 2.0 (2018-05-07) (previous changes undocumented)
* Point release (including complete reanalysis/rewrite of plugin)
* Added cleanStr callback function



