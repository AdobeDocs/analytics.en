---
description: The getTimeParting plug-in populates custom variables with hour of day, day of week, and weekend and weekday values into custom variables. Analysis Workspace offers out-of-the-box Time Parting dimensions. The plug-in should be used if time parting dimensions are needed in other Analytics solutions, outside of Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
---

# getTimeParting

The getTimeParting plugin provides a complete analytics solution that allows you to capture the details of the time when any measurable activity takes place on your site.  

You should use the getTimeParting plugin if you wish to breakdown your metrics by any repeatable division of time over a given date range.  For example, the getTimeParting plugin will allow you to compare conversion rates between two different days of the week (e.g. all Sundays vs. all Thursdays), two different periods of the day (e.g. all mornings vs. all evenings), or even two subsequent minutes (e.g. all 10:00 AM instances vs. all 10:01 AM instances) for the date range you specify in the report. 

[!DNL Analysis Workspace] provides similar, out-of-the-box dimensions that are formatted in a slightly different manner than what this plugin provides (see [here](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html)).  Adobe Consulting recommends you read through the remainder of this help section to determine whether this plugin provides data in a manner that's more suited to your needs.  

If you don't need to break down your metrics by a repeatable division of time over a specific date range, then you will not need to use the getTimeParting plugin.  Also, if you find the [!DNL Analysis Workspace] Time-Parting Dimensions sufficient, then you will not need to implement this plugin.

>[!CAUTION] The solution that version 4.0+ of the getTimeParting plugin provides is much different than what earlier versions of the plugin have provided.  If you choose to upgrade from a version before 4.0, you should implement the solution "from scratch".  In other words, you should setup a completely brand new eVar – one eVar – to hold the data provided by the plugin and read through this documentation carefully before implementing the solution.  

>[!CAUTION] Also: This version of the plugin is not *fully* compatible with Microsoft Internet Explorer browsers, although the plugin is fully compatible with Microsoft Edge browsers.   Visitors that use Internet Explorer will be able to provide the time but only in their *local* time zone rather than converted to the time zone you specify.  See the examples below for a solution that will not include data from Internet Explorer browsers but will still account for their presence. 

> [!NOTE] The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

> [!WARNING] Always test all plugin implementations before deploying to production to ensure that data collection is working as expected.

## Prerequisites

None

## How to Implement

* Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement code:

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] You may also use a tag manager like Adobe Launch to deploy the plugin code without the need to attach it to AppMeasurement or any other analytics solution

* Run the getTimeParting function as described below within the doPlugins function or in any other location where you need to capture the time parting data 

**Arguments to Pass In**

* t: (**OPTIONAL but recommended**, string) The name of the time zone to convert the visitor's local time to.  Defaults to “Etc/GMT”, or UTC/GMT time when not set.  Visit [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] for the complete list of values to enter.  

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

## Example Calls

Use the following code if you are located in Paris, France and want to use eVar10 (in Adobe Analytics) to capture the time parting data:

```s.eVar10 = getTimeParting("Europe/Paris")```

Use the following code if you are located in San Jose, California:

```s.eVar10 = getTimeParting("America/Los_Angeles")```

Use the following code if you are located in the African country of Ghana:

```s.eVar10 = getTimeParting();```

Ghana is within the UTC/GMT time zone.  Thus, this example shows that no plugin argument will be necessary under such circumstances.

Use the following code if you are located in New York and do not want to include data from Internet Explorer Visitors (since the values returned from IE browsers can be provided in only the visitor's local time)
```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**Results From Calls**

If a visitor from Denver, Colorado visits a site on August 31, 2020 at 9:15 AM, the following code…
```s.eVar10 = getTimeParting("Europe/Athens");``` 
…would set s.eVar10 equal to **year=2020 | month=August | date=31 | day=Monday | time=6:15 PM**

The following code…
```s.eVar10 = getTimeParting("America/Nome");```
… would instead set s.eVar10 equal to **year=2020 | month=August | date=31 | day=Monday | time=6:15 AM**

The following code…
```s.eVar10 = getTimeParting("Asia/Calcutta");```
… would instead set s.eVar10 equal to **year=2020 | month=August | date=31 | day=Monday | time=8:45 PM**

The following code…
```s.eVar10 = getTimeParting("Australia/Sydney");```
… would instead set s.eVar10 equal to **year=2020 | month=September | date=1 | day=Tuesday | time=1:15 AM**

## Adobe Analytics Setup

If you want to capture the time parting data in Adobe Analytics, please setup a new eVar with the following characteristics:

*	Name: Time Parting
*	Allocation: Most Recent (Last)
*	Expire After: Visit
*	All other attributes use the default values provided
