---
title: getNewRepeat
description: Track activity of new vs. repeat visitors.
---

# Adobe plug-in: getNewRepeat

## Plugin Purpose

### What does this plug-in do?

The getNewRepeat plug-in allows you to determine whether a visitor to the site is a new visitor or a repeat visitor within the last "x" number of days

### Why should I use this plug-in?

You should use the getNewRepeat plug-in if you want to identify visitors as being "new" if they haven't visited the site for at least "x" number of days after their last visit

### Why shouldn't I use this plug-in?

You shouldn't use this plug-in if you don't care whether the amount of time between visits should be the determining factor in labeling a legitimate repeat visitor as "new".

Adobe Analytics provides an out-of-the-box visit number report that you can leverage to determine the behavior of new visitors vs. repeat visitors.   In the out-of-the-box report, the visit number will be equal to 1 if the visitor receives a new Marketing Cloud/Visitor ID cookie during the visit.  The visit number will be equal to a number greater than 1 if the visitor makes a return visit to the site and already has a Marketing Cloud/Visitor ID cookie set when the visit starts.

Using this out-of-the-box data, you can create a segment that identifies visits from new visitors from those visits where the Visit Number equals 1.  You can create another segment that identifies visits from repeat/return visitors from those visits where the Visit Number is greater than 1:

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getNewRepeat plug-in

## How to Deploy

You may use one of the following three methods to deploy the getNewRepeat plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the getNewRepeat plug-in (via JavaScript), be sure to pass in the following arguments:

* **d** (integer, optional): The minimum number of days required between visits that will identify visitors to the site as "New" visitors (even if they are return visitors).  If the d parameter is not set, then it will default to the value of 30 (i.e. 30 days).

## Returns

The getNewRepeat plug-in will return the value of "New" if the cookie set by the plug-in ("s_nr") doesn't exist (or has expired) OR if the visitor continues to send image requests during the visit where the return value was initially set equal to "New".

In other words, the return value will be equal to "New" in every hit of a visit where the visitor was identified as a "New" visitor.

The plug-in will return the value of "Repeat" if the cookie set by the plug-in ("s_nr") exists and the amount of time since the current hit and the time set in the cookie is greater than 30 minutes.   The plug-in will also return "Repeat" if the visitor continues to send image requests during the visit where the return value was initially set equal to "Repeat".

In other words, the return value will be equal to "Repeat" in every hit of a visit where the visitor was identified as a "Repeat" visitor.

## Cookies

The getNewRepeat plug-in creates a first-party cookie called "s_nr[LENGTH]" where [LENGTH] is equal to the d argument, or the number of days of inactivity before a visitor is considered "New" to the site (e.g. "s_nr30", "s_nr365", etc.).  The cookie will be equal to a unix timestamp representing the current time as well as the current status of the visitor (either "new" or "repeat").  The cookie will expire after the number of days of inactivity before a visitor is considered "New" has passed

## Example Calls

### Example #1
The following code will set s.eVar1 equal to the value of "New" for new visitors and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat();
```
### Example #2
If the visitor comes back to the site anytime from 31 minutes to 30 days since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "Repeat" and will continue to set s.eVar1 equal to the value of "Repeat" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat();
```
### Example #3
If the visitor hasn't been to the site for at least 30 days since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "New" and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat();
```
### Example #4
If the visitor comes back to the site anytime 31 minutes to 365 days (i.e. 1 year) since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "Repeat" and will continue to set s.eVar1 equal to the value of "Repeat" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat(365);
```
### Example #5
If the visitor hasn't been to the site for at least 365 days (i.e. 1 year) since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "New" and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.

```js
s.eVar1=s.getNewRepeat(365);
```

## Version History

### 2.1 (September 30, 2019)

* Rearrangement of JavaScript logic to reduce plug-in size

### 2.0 (April 16, 2018)

* Recompiled with smaller code size
* Removed the ability to name the cookie to store the visit info. The plug-in now dynamically names the cookie based on the value passed into the `d` argument.
