---
title: getTimeParting
description: Measure the time when a specific action takes place
---

# Adobe Experience Cloud Plugin – getTimeParting

## Purpose of This Plugin

### What does this plugin do?
The getTimeParting plugin provides a complete analytics solution that allows a client to capture the details of the time when any measurable activity takes place on its site.

### Why should I use this plugin?
You should use the getTimeParting plugin if you wish to breakdown your metrics by any repeatable division of time over a given date range.  For example, the getTimeParting plugin will allow you to compare conversion rates between two different days of the week (e.g. all Sundays vs. all Thursdays), two different periods of the day (e.g. all mornings vs. all evenings), or even two subsequent minutes (e.g. all 10:00 AM instances vs. all 10:01 AM instances) for the date range you specify in the report.

Analysis Workspace provides similar, out-of-the-box dimensions that are formatted in a slightly different manner than what this plugin provides (see here), so Adobe Consulting recommends you read through the remainder of this document (and the aforementioned link to the help section) to determine whether this plugin provides data in a manner that's more suited to your needs.

### Why shouldn't I use this plugin?

If you don't care about breaking down your metrics by a repeatable division of time over a specific date range, then you will not need to use the getTimeParting plugin.  Also, if you find the Analysis Workspace Time-Parting Dimensions sufficient, then you will not need to implement this plugin.

**Please note**: the solution that version 4.0+ of the getTimeParting plugin provides is much different than what earlier versions of the plugin have provided.  If you choose to upgrade from a version before 4.0, you should implement the solution "from scratch".  In other words, you should setup a completely brand new eVar – one eVar – to hold the data provided by the plugin and read through this documentation carefully before implementing the solution.

**Also**: This version of the plugin is not **fully** compatible with Microsoft Internet Explorer browsers, although the plugin is fully compatible with Microsoft Edge browsers.   Visitors that use Internet Explorer will be able to provide the time but only in their local time zone rather than converted to the time zone you specify.  See the examples below for a solution that will not include data from Internet Explorer browsers but will still account for their presence.

## Prerequisites
None

## How to Deploy

You may use one of the following three methods to deploy the getTimeParting plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file
Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 (No Prerequisites Needed) */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
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
	* Action Type: Initialize getTimeParting
* Save and publish the changes to the rule

## How to Run the Plugin
When calling the getTimeParting plugin (via JavaScript), be sure to pass in the following arguments:

**t**: (OPTIONAL but recommended, string) The name of the time zone to convert the visitor's local time to.  Defaults to “Etc/GMT”, or UTC/GMT time.  Visit https://en.wikipedia.org/wiki/List_of_tz_database_time_zones for the complete list of values to enter.

Common values include:

* "America/New_York" for Eastern Time
* "America/Chicago" for Central Time
* "America/Denver" for Mountain Time
* "America/Los_Angeles" for Pacific Time

## Returns
The getTimeParting plugin returns a string containing the following:
* The current year
* The current month
* The current date (i.e. day of the month)
* The current day (i.e. day of the week)
* The current time (non-military time)
Each of the above items is delimited by a pipe ("|") character.

## Cookies
The getTimeParting plugin does not create or use any cookies

## Example Calls

### Examples for Specific Time Zones
Use the following sample code if the client is in Paris, France:
```javascript
s.eVarX = getTimeParting("Europe/Paris");
```
If the client is in San Jose, California:
```javascript
s.eVarX = getTimeParting("America/Los_Angeles");
```
If the client is in the African country of Ghana:
```javascript
s.eVarX = getTimeParting();
```
Ghana is within the UTC/GMT time zone.  This example shows that no plugin argument will be necessary under such circumstances.

### Accounting for Internet Explorer Browsers
Use the following sample if you want to exclude time parting data from Internet Explorer Visitors (since the value returned from IE browsers can be in only the visitor's local time)
```javascript
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Results from calls
If a visitor from Denver, Colorado visits a site on August 31, 2020 at 9:15 AM,

Running the following code...
```javascript
s.eVar10 = getTimeParting("Europe/Athens");
```
...would set s.eVar10 equal to "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"

While the following code...
```javascript
s.eVar10 = getTimeParting("America/Nome");
```
...would set s.eVar10 equal to "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"

The following code...
```javascript
s.eVar10 = getTimeParting("Asia/Calcutta");
```
...would set s.eVar10 equal to "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"

And the following code...
```javascript
s.eVar10 = getTimeParting("Australia/Sydney");
```
...would set s.eVar10 equal to "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"

## s Object Replacement
The getTimeParting plugin does not require AppMeasurement or any other plugins and thus does not need to be attached to the s object (or other AppMeasurement object)

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

