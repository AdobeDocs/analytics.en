---
title: getTimeParting
description: Capture details of the time of visitor actions.
---

# getTimeParting

The `getTimeParting` plug-in allows you to capture the details of the time when any measurable activity takes place on your site. This plug-in is valuable when you want to breakdown metrics by any repeatable division of time over a given date range. For example, you can compare conversion rates between two different days of the week, such as all Sundays vs. all Thursdays. You can also compare periods of the day, such as all mornings vs. all evenings.

Analysis Workspace provides similar, out-of-the-box dimensions that are formatted slightly differently than this plug-in. See [time parting dimensions](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) in the Analyze user guide for more information. Some organizations find that Analysis Workspace's out-of-the-box dimensions are sufficient.

> [IMPORTANT] Version 4.0+ of this plug-in is significantly different than earlier versions. Adobe highly recommends implementing this plug-in "from scratch". Code referencing the plug-in before version 4.0 is not compatible with the current version of this plug-in.

## Install the getTimeParting plug-in using Adobe Experience Platform Launch

You can install the `getTimeParting()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `getTimeParting()` function in the custom code editor of rules to assign variable values.

## Install the getTimeParting plug-in using AppMeasurement

You can install the `getTimeParting()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere you'd like.
3. Save the JS file and upload the new version to your web server.

Once installed, you can use the `getTimeParting()` function to assign variable values.

## Plug-in code

```js
// getTimeParting v4.0
function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}
```

## Use the getTimeParting plug-in with AppMeasurement and Launch custom code editor

The `getTimeParting()` function returns a multi-value string, delimited by pipes (`|`). Each value contains a date dimension:

* The current year
* The current month
* The current day of the month
* The current day of the week
* The current time (AM/PM)

```js
// Assigns eVar1 a value in the following format: "year=2020 | month=January | date=1 | day=Wednesday | time=12:00 AM"
s.eVar1 = getTimeParting();
```

The plug-in takes one optional (but recommended) argument - a string that contains the name of the desired time zone. See [List of tz database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) on Wikipedia for the full list of valid string values for this argument. If this argument is omitted, UTC time is returned. Common values for the United States include:

* `"America/New_York"` for Eastern Time
* `"America/Chicago"` for Central Time
* `"America/Denver"` for Mountain Time
* `"America/Los_Angeles"` for Pacific Time

You can use this argument for several use cases:

* Use your report suite's time zone to match time-based dimensions in reporting.
* Use a different time zone for the ability to use time-based dimensions with different time zones.
* Use the visitor's time zone to see time relative to the visitor.

> [!NOTE] Internet Explorer always uses local time and ignores the time zone argument. You can check to see if `document.documentMode` exists to exclude these visitors. This plug-in is compatible with Microsoft Edge.

```js
// If your report suite uses Mountain Time, set the timezone offset argument to match it
s.eVar1 = getTimeParting("America/Denver");

// If your report suite uses Mountain Time but you have analysts in Tokyo that prefer to use their own time zone
s.eVar1 = getTimeParting("America/Denver");
s.eVar2 = getTimeParting("Asia/Tokyo");

// Omit browsers that only use the browser's local time
if (!document.documentMode) s.eVar1 = getTimeParting("America/New_York");
else s.eVar1 = "Internet Explorer visitors";

// Detect and use the visitor's time zone offset - Internet Explorer uses this behavior by default
if (!document.documentMode) s.eVar1 = getTimeParting(Intl.DateTimeFormat().resolvedOptions().timeZone);
else s.eVar1 = getTimeParting();
```
