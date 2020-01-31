---
title: getNewRepeat
description: Track activity of new vs. repeat visitors
---

# Adobe Plugin: getNewRepeat

## Plugin Purpose

### What does this plugin do?

The getNewRepeat plugin allows you to determine whether a visitor to the site is a new visitor or a repeat visitor within the last "x" number of days

### Why should I use this plugin?

You should use the getNewRepeat plugin if you want to identify visitors as being "new" if they haven't visited the site for at least "x" number of days after their last visit

### Why shouldn't I use this plugin?

You shouldn't use this plugin if you don't care whether the amount of time between visits should be the determining factor in labeling a legitimate repeat visitor as "new".

Adobe Analytics provides an out-of-the-box visit number report that you can leverage to determine the behavior of new visitors vs. repeat visitors.   In the out-of-the-box report, the visit number will be equal to 1 if the visitor receives a new Marketing Cloud/Visitor ID cookie during the visit.  The visit number will be equal to a number greater than 1 if the visitor makes a return visit to the site and already has a Marketing Cloud/Visitor ID cookie set when the visit starts.

Using this out-of-the-box data, you can create a segment that identifies visits from new visitors from those visits where the Visit Number equals 1.  You can create another segment that identifies visits from repeat/return visitors from those visits where the Visit Number is greater than 1:

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getNewRepeat plugin

## How to Deploy

You may use one of the following three methods to deploy the getNewRepeat plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file

Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v2.1 (Requires AppMeasurement) */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
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
	* Action Type: Initialize getNewRepeat
* Save and publish the changes to the rule

## How to Run the Plugin

When calling the getNewRepeat plugin (via JavaScript), be sure to pass in the following arguments:

* **d** (integer, optional): The minimum number of days required between visits that will identify visitors to the site as "New" visitors (even if they are return visitors).  If the d parameter is not set, then it will default to the value of 30 (i.e. 30 days).

## Returns

The getNewRepeat plugin will return the value of "New" if the cookie set by the plugin ("s_nr") doesn't exist (or has expired) OR if the visitor continues to send image requests during the visit where the return value was initially set equal to "New".

In other words, the return value will be equal to "New" in every hit of a visit where the visitor was identified as a "New" visitor.

The plugin will return the value of "Repeat" if the cookie set by the plugin ("s_nr") exists and the amount of time since the current hit and the time set in the cookie is greater than 30 minutes.   The plugin will also return "Repeat" if the visitor continues to send image requests during the visit where the return value was initially set equal to "Repeat".

In other words, the return value will be equal to "Repeat" in every hit of a visit where the visitor was identified as a "Repeat" visitor.

## Cookies

The getNewRepeat plugin creates a first-party cookie called "s_nr[LENGTH]" where [LENGTH] is equal to the d argument, or the number of days of inactivity before a visitor is considered "New" to the site (e.g. "s_nr30", "s_nr365", etc.).  The cookie will be equal to a unix timestamp representing the current time as well as the current status of the visitor (either "new" or "repeat").  The cookie will expire after the number of days of inactivity before a visitor is considered "New" has passed

## Example Calls

### Example #1
The following code will set s.eVar1 equal to the value of "New" for new visitors and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.
```javascript
s.eVar1=s.getNewRepeat();
```
### Example #2
If the visitor comes back to the site anytime from 31 minutes to 30 days since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "Repeat" and will continue to set s.eVar1 equal to the value of "Repeat" (with each new call) throughout the remainder of the visitor's visit to the site.
```javascript
s.eVar1=s.getNewRepeat();
```
### Example #3
If the visitor hasn't been to the site for at least 30 days since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "New" and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.
```javascript
s.eVar1=s.getNewRepeat();
```
### Example #4
If the visitor comes back to the site anytime 31 minutes to 365 days (i.e. 1 year) since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "Repeat" and will continue to set s.eVar1 equal to the value of "Repeat" (with each new call) throughout the remainder of the visitor's visit to the site.
```javascript
s.eVar1=s.getNewRepeat(365);
```
### Example #5
If the visitor hasn't been to the site for at least 365 days (i.e. 1 year) since the last time s.getNewRepeat() was called, the following code will set s.eVar1 equal to the value of "New" and will continue to set s.eVar1 equal to the value of "New" (with each new call) throughout the remainder of the visitor's visit to the site.
```javascript
s.eVar1=s.getNewRepeat(365);
```

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.getNewRepeat=function(d){
```
...to this:
```javascript
[objectname].getNewRepeat=function(d){
```

## Version History

### 2.1 (2019-09-30)
* Rearrangement of JavaScript logic (for reduced plugin size)
### 2.0 (2018-04-16) - Previous Versions Undocumented
* Point Release (recompiled, smaller code size)
* Removed the ability to name the cookie to store the visit info.  The plugin will now dynamically name the cookie based off the value passed into the d argument
