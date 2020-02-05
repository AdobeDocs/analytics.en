---
title: getTimeParting
description: Measure the time when a specific action takes place.
---

# Adobe plug-in: getTimeParting

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getTimeParting` plug-in allows you to capture the details of the time when any measurable activity takes place on your site. This plug-in is valuable when you want to breakdown metrics by any repeatable division of time over a given date range. For example, you can compare conversion rates between two different days of the week, such as all Sundays vs. all Thursdays. You can also compare periods of the day, such as all mornings vs. all evenings.

Analysis Workspace provides similar, out-of-the-box dimensions that are formatted slightly differently than this plug-in. See [time parting dimensions](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) in the Analyze user guide for more information. Some organizations find that Analysis Workspace's out-of-the-box dimensions are sufficient.

> [IMPORTANT] Version 4.0+ of this plug-in is significantly different than earlier versions. Adobe highly recommends implementing this plug-in "from scratch". Code referencing the plug-in before version 4.0 is not compatible with the current version of this plug-in.

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
    * Action Type: Initialize getTimeParting
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
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getTimeParting` method uses the following argument:

**`t`** (Optional but recommended, string): The name of the time zone to convert the visitor's local time to.  Defaults to UTC/GMT time. See [List of TZ database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) on Wikipedia for a complete list of valid values.

Common valid values include:

* `"America/New_York"` for Eastern Time
* `"America/Chicago"` for Central Time
* `"America/Denver"` for Mountain Time
* `"America/Los_Angeles"` for Pacific Time

Calling this method returns a string that contains the following delimited by a pipe (`|`):

* The current year
* The current month
* The day of the month
* The day of the week
* The current time (AM/PM)

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

## Version History

### 6.2 (November 5, 2019)

* Small bug fixes
* Reduced overall code size

### 6.1 (November 26, 2018)

* Fix for Internet Explorer browsers. They can return the time, but in only the visitor’s local time.

### 6.0 (August 14, 2018)

* Complete rewrite to accommodate international standards. Now converts daylight savings and all time zones appropriately.

### 5.0 (April 17, 2018)

* Point Release (recompiled, smaller code size)
* Removed the need for the `tpDST` parameter, since daylight savings start/end dates are now detected automatically

### 4.0 (August 22, 2016)

* Provides a brand new solution and now includes year, month, and date information.
