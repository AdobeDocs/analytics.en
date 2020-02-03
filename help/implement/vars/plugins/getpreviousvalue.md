---
title: getPreviousValue
description: Get the last value passed into a variable.
---

# Adobe plug-in: getPreviousValue

## Purpose of This Plugin

### What does this plug-in do?
The getPreviousValue plug-in allows you to set an Analytics variable equal to the value of a variable that was either set on a previous page or contained in a previous Analytics web beacon

### Why shouldn't I use this plug-in?
If you use a plug-in that already provides previous-page-based information (e.g. getPercentPageViewed, etc.) you will not need to use this plug-in.

## Prerequisites
You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getPreviousValue plug-in

## How to Deploy

You may use one of the following three methods to deploy the getGeoCoordinates plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the getPreviousValue plug-in (via JavaScript), be sure to pass in the following arguments:
* **v** (string, required): The Analytics variable that has the value that you want to pass over to the next image request   Most cases use s.pageName (for retrieving the previous pageName value).
* **c** (string, optional): The name of the cookie that will store the value to be passed over to the next image request.  If the c argument is not set, then it will default to the name of "s_gpv"

## Returns
* The getPreviousValue plug-in always returns the last value that was passed into the variable specified in the v argument.   This means that if the variable was not set to a value during the hit just before the current one but instead, for instance, was last set five hits ago, a call to the plug-in will still return the value passed into the variable give hits ago and will continue to do so until the variable's value changes.
* The plug-in will return nothing on the first page of a visit (i.e. when a new visitor comes to the site OR more than 30 minutes has passed since a visitor has visited the site)

## Cookies
The getPreviousValue plug-in creates a first-party cookie, the name of which is passed in via the c argument.  The contents of the cookie contain the previous value that you want to store/retrieve.   The cookie expires after 30 minutes of inactivity (i.e. at the end of the visit).

## Example Calls

### Example #1
The following code...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```
* First sets s.prop7 equal to the value passed into s.pageName in the previous image request (i.e. the value stored in the "gpv_Page" cookie)
* The code will then reset the "gpv_Page" cookie, making it equal to the current value of s.pageName
* If s.pageName is not set at the time this code runs, then the code will reset the expiration for the cookie's current value

### Example #2
The following code sets s.prop7 equal to the last value passed into s.pageName, but only if event1 is also contained within s.events, as determined via the inList plug-in, at the time the call takes place.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Example #3
The following code sets s.prop7 equal to the last value passed into s.pageName but only if s.pageName is currently set on the page at the same time.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Example #4
The following code sets s.eVar10 equal to the value passed into s.eVar1 in the previous image request.   The previous eVar1 value would have been contained in the "s_gpv" cookie.  The code will then set the "s_gpv" cookie equal to the current value of s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Unlikely Quirks
If the variable associated with the v argument is set to a new value and the getPreviousValue plug-in runs BUT an Analytics server call is NOT sent at the same time, the new v argument value will still be considered the "previous value" the next time the plug-in runs.
For example, assume the following code runs on the first page of the visit:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```
This code would produce a server call where the pageName argument is equal to "home" and the p7 (prop7) argument is not set.  However, the call to s.getPreviousValue would store the value of s.pageName (i.e. "home") in the cookie specified in the call (i.e. the "gpv_Page" cookie).
Now, assume that immediately afterwards, on the same page, the following code runs (for whatever reason):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```
Since the s.t() function does not run in this code block, another image request will not be created.  However, when the s.getPreviousValue() function code runs this time, s.prop7 will be set equal to the previous value of s.pageName (i.e. "home") and then will store the new value of s.pageName (i.e. "happy value") in the "gpv_Page" cookie.
Assume the visitor navigates to a different page and the following code runs on this page:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```
When the s.t() call function runs, it will create an image request where s.pageName="page 2" and s.prop7 is equal to "happy value", which was the value of s.pageName when the last call to getPreviousValue took place.   The s.prop7 value of "home" was never contained in any real image request even though "home" was the first value passed into s.pageName.

## Version History

### v2.0 (October 7, 2019)

* Point release (complete logic rewrite).
