---
title: getValOnce
description: Prevent an Analytics variable from being set to the same value twice in a row.
---

# Adobe plug-in: getValOnce

## Purpose of This Plugin

### What does this plug-in do?
The getValOnce plug-in prevents a variable from being set equal to the same value twice in a row (or more)

### Why should I use this plug-in?
The getValOnce plug-in is useful in situations where your organization would like to deduplicate, for example, multiple campaign click-through instances that might occur when users refresh a landing page or come back to the landing page via hitting the browser's back button.

### Why shouldn't I use this plug-in?
You your organization does not need to deduplicate a variable's value, then you won't need to use this plug-in.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run this plug-in

## How to Deploy

You may use one of the following three methods to deploy the getValOnce plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.


## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install (and publish) the "Common Analytics Plugins" extension
1. For any Launch Rule that you want to use the plug-in in, add an [!UICONTROL action] with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided above into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v2.0 (Requires AppMeasurement) */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getValOnce plug-in (via JavaScript), be sure to pass in the following arguments:

* **vtc** (required, string) - the variable to check and see whether it was just previously set to an identical value
* **cn** (optional, string) - the name of the cookie that will hold the value to check against, defaults to "s_gvo"
* **et** (optional, integer) - a number that specifies when the cn cookie will hit its expire time (in "x" minutes/days); defaults to 0, which forces the cn cookie to expire at the end of the session
* **ep** (optional, string) – Set this when the "et" argument is set; defaults to "d" (i.e. days)
	* Set the “ep” argument equal to "m" if you want the "cn" cookie to expire in "et" number of minutes
	* OR set the "ep" argument equal to "d" if you want the "cn" cookie to expire in "et" number of days

## Returns
If the variable specified in the vtc parameter has the exact same value as before, the getValOnce plug-in will return an empty string; otherwise it will return the (new) value passed into the variable.

## Cookies
The getValOnce plug-in creates a first-party cookie with a name equal to the name passed in via the cn argument.  Its value is equal to the value contained in the vtc argument and its expiration is dependent on the values passed in via the et/ep arguments.

## Example Calls

### Example #1
Use this call to prevent the same value being passed in to s.campaign more than once in a row for next 30 days:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```
In the above call, the plug-in will first compare the value already contained in the s_campaign cookie with the value coming from the current s.campaign variable.   If a match is not made, the plug-in will set the s_campaign cookie equal to the new value coming from s.campaign and then return the new value.   This comparison will happen for the next thirty days

### Example #2
Use this call to prevent the same value being set throughout the session:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```
This code prevents the same value from being passed into s.eVar2 more than once in a row throughout a user’s session.  It also ignores the “m” value in the epargument (at the end of the call) since the expiration time is set equal to 0.   The code also stores the comparison value in the s_ev2 cookie.

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plug-in code from this...

```js
s.getValOnce=function(vtc,cn,et,ep)
```
...to this:

```js
[objectname].getValOnce=function(vtc,cn,et,ep)
```
## Version History

### 2.0
* Point Release (recompiled, smaller code size)
### 1.1
* Added the option to choose minutes or days for the expiration via the 't' parameter'.
* Corrected the scope of the k variable used to restrict it to the plug-in only. (to prevent possible interaction with other js code on the customer’s page).

