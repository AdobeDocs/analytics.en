---
title: getAndPersistValue
description: Store a value that can be retrieved later at any time.
---

# Adobe plug-in: getAndPersistValue

## Plugin Purpose

### What does this plug-in do?

The getAndPersistValue plug-in allows you to store a value in a cookie that can be retrieved later during a visit.

### Why should I use this plug-in?

You should use the getAndPersistValue plug-in if you want to persistently and automatically set an Analytics variable equal to the same value in every server call after the variable was initially set.

### Why shouldn't I use this plug-in?

From a conversion perspective, the built-in persistence of eVars eliminates the need to set them equal to the same value in every server call after they were initially set.   In general, if you have no need to automatically set an Analytics variable equal to the same value in every server call after the variable was initially set, then you have no need for the getAndPersistValue plug-in.

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getAndPersistValue plug-in

## How to Deploy

You may use one of the following three methods to deploy the getAndPersistValue plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 (Requires AppMeasurement) */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the getAndPersistValue plug-in (via JavaScript), be sure to pass in the following arguments:

* **vtp**: (required) The value that is meant to persist from page to page after it has been written to the cookie specified in the cn argument
* **cn**: (optional) The name of the cookie that will store the value to persist (as set within the vtp argument).  If the cn argument is not set, then it will default to the name of "s_gapv"
* **ex**: (optional) The number of days that the value is set to persist before it expires.  If the argument is set equal to 0 (i.e. zero, without quotes) or is not set at all, the value will stop persisting at the end of the visit (i.e. after 30 minutes of inactivity)

## Returns

If the variable/value to be passed in via the vtp argument has been set on the current page before the getAndPersistValue plug-in is called, then the plug-in will first set the cookie specified in the cn argument equal to the value of the vtp argument and then return the (new) value of the cookie.
The plug-in will only return the value of the cookie if the variable in the vtp argument hasn't been set on the page.

## Cookies

The getAndPersistValue sets a first-party cookie with a name that you specify via the cn argument.  The length of the cookie depends on the value that is persisting (i.e. the vtp argument's value).  The cookie will expire depending on the value of the ex argument

## Example Calls

### Example #1
The following code will set eVar21 equal to the value of "hello".  The code will then set the ev21gapv cookie, which will expire in 28 days, equal to the value of eVar21 (i.e. "hello").  The code will then (re)set eVar21 equal to the value of the ev21gapv cookie.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #2
Assume that eVar21 has not been set on the current page yet but was set equal to "hello" on a previous page within the last 28 days.   The following code will only set eVar21 equal to the value of the ev21gapv cookie (i.e. "hello").  It does not reset the ev21gapv cookie since eVar21 was not set on the current page before the function was called.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #3
Assume that eVar21 has not been set on the current page yet but was set equal to "hello" on a previous page within the last 28 days.  The following code will set only prop35 equal to the value of the ev21gapv cookie (i.e. "hello").  It will not set eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #4
The following code will set eVar21 equal to the value of "howdy".  The code will then set (or reset) the ev21gapv cookie, which will expire in 28 days, equal to the value of eVar21 (i.e. "howdy").  The code will then set prop35 equal to the value of the ev21gapv cookie (i.e. "howdy").

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #5
Assume that s.eVar21 has not been set on any pages within the last 28 days.  The following code will set s.eVar21 equal to nothing since the ev21gapv cookie would have expired 28 days after it was last set.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Example #6
The following code will set eVar30 equal to "shopping".  It will then set the s_gapv cookie, which will expire at the end of the browser session, equal to the value of s.eVar30 (i.e. "shopping").  It will then set s.eVar30 equal to the value of the s_gapv cookie (i.e. the getAndPersistValue call returns the value of the s_gapv cookie, which in this case is "shopping").

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```
If s.eVar30 is not set to an explicit value on any additional pages seen during the session but is set (in doPlugins) via the following code...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```
...s.eVar30 will be set equal to "shopping" (i.e. the persisted value of the s_gapv cookie)

## Version History

### 2.0 (April 16, 2018)

* Point release (smaller code size)
* Passing 0 into the `ex` argument now forces expiration after 30 minutes of inactivity rather than expiration at the end of the browser session.

### 1.0 (January 18, 2016)

* Initial release.
