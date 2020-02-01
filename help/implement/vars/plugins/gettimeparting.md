---
title: getTimeParting
description: Measure the time when a specific action takes place.
---

# Adobe plug-in: getTimeParting

## Purpose of This Plugin

### What does this plug-in do?
The getTimeParting plug-in provides a complete analytics solution that allows a client to capture the details of the time when any measurable activity takes place on its site.

### Why should I use this plug-in?
You should use the getTimeParting plug-in if you wish to breakdown your metrics by any repeatable division of time over a given date range.  For example, the getTimeParting plug-in will allow you to compare conversion rates between two different days of the week (e.g. all Sundays vs. all Thursdays), two different periods of the day (e.g. all mornings vs. all evenings), or even two subsequent minutes (e.g. all 10:00 AM instances vs. all 10:01 AM instances) for the date range you specify in the report.

Analysis Workspace provides similar, out-of-the-box dimensions that are formatted in a slightly different manner than what this plug-in provides (see here), so Adobe Consulting recommends you read through the remainder of this document (and the aforementioned link to the help section) to determine whether this plug-in provides data in a manner that's more suited to your needs.

### Why shouldn't I use this plug-in?

If you don't care about breaking down your metrics by a repeatable division of time over a specific date range, then you will not need to use the getTimeParting plug-in.  Also, if you find the Analysis Workspace Time-Parting Dimensions sufficient, then you will not need to implement this plug-in.

**Please note**: the solution that version 4.0+ of the getTimeParting plug-in provides is much different than what earlier versions of the plug-in have provided.  If you choose to upgrade from a version before 4.0, you should implement the solution "from scratch".  In other words, you should setup a completely brand new eVar – one eVar – to hold the data provided by the plug-in and read through this documentation carefully before implementing the solution.

**Also**: This version of the plug-in is not **fully** compatible with Microsoft Internet Explorer browsers, although the plug-in is fully compatible with Microsoft Edge browsers.   Visitors that use Internet Explorer will be able to provide the time but only in their local time zone rather than converted to the time zone you specify.  See the examples below for a solution that will not include data from Internet Explorer browsers but will still account for their presence.

## Prerequisites
None

## How to Deploy

You may use one of the following three methods to deploy the getTimeParting plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getTimeParting v6.2 (No Prerequisites Needed) */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getTimeParting plug-in (via JavaScript), be sure to pass in the following arguments:

**t**: (OPTIONAL but recommended, string) The name of the time zone to convert the visitor's local time to.  Defaults to “Etc/GMT”, or UTC/GMT time.  Visit https://en.wikipedia.org/wiki/List_of_tz_database_time_zones for the complete list of values to enter.

Common values include:

* "America/New_York" for Eastern Time
* "America/Chicago" for Central Time
* "America/Denver" for Mountain Time
* "America/Los_Angeles" for Pacific Time

## Returns
The getTimeParting plug-in returns a string containing the following:
* The current year
* The current month
* The current date (i.e. day of the month)
* The current day (i.e. day of the week)
* The current time (non-military time)
Each of the above items is delimited by a pipe ("|") character.

## Cookies
The getTimeParting plug-in does not create or use any cookies

## Example Calls

### Examples for Specific Time Zones
Use the following sample code if the client is in Paris, France:

```js
s.eVarX = getTimeParting("Europe/Paris");
```
If the client is in San Jose, California:

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```
If the client is in the African country of Ghana:

```js
s.eVarX = getTimeParting();
```
Ghana is within the UTC/GMT time zone.  This example shows that no plug-in argument will be necessary under such circumstances.

### Accounting for Internet Explorer Browsers
Use the following sample if you want to exclude time parting data from Internet Explorer Visitors (since the value returned from IE browsers can be in only the visitor's local time)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Results from calls
If a visitor from Denver, Colorado visits a site on August 31, 2020 at 9:15 AM,

Running the following code...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```
...would set s.eVar10 equal to "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"

While the following code...

```js
s.eVar10 = getTimeParting("America/Nome");
```
...would set s.eVar10 equal to "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"

The following code...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```
...would set s.eVar10 equal to "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"

And the following code...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```
...would set s.eVar10 equal to "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"

## s Object Replacement
The getTimeParting plug-in does not require AppMeasurement or any other plug-ins and thus does not need to be attached to the s object (or other AppMeasurement object)

## Version History

### 6.2 (2019-11-05)
* Small bug fixes
* Reduced Overall Code Size
### 6.1 (2018-11-26)
* Fix for Internet Explorer Browsers.  IE browsers are able return the time, but in only the visitor’s local time.
### 6.0 (2018-08-14)
* Complete rewrite to accommodate International Standards (now converts daylight savings and all time zones appropriately)
### 5.0 (2018-04-17)
* Point Release (recompiled, smaller code size)
* Removed the need for the s.tpDST parameter to be set as daylight savings start/end dates will now be detected automatically
### 4.0 (2016-08-22) - Changes in previous versions not available
* Version 4.0 provides a completely brand new solution and now includes Year/Month/Date information

