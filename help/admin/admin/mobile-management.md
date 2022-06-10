---
description: Enabling app management activates the mobile solution variables that capture lifecyle and other metrics from mobile applications.
title: App Management
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
---
# App Management

Enabling app management activates the mobile solution variables that capture lifecyle and other metrics from mobile applications.

This integration between Adobe Analytics and Mobile Services:

* Lets you share your KPI (Key Performance Indicator) data from Mobile Services to Adobe Analytics.
* Lets you enable location tracking.
* Adds new reports under Analytics > Reports > Mobile App.
* Adds 25 new Adobe Mobile classifications.
* Adds 5 new Adobe Mobile metrics.
* Adds new Adobe Mobile dimensions.
* Synchronizes data to Analytics every 15 minutes

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

## Step 1. Enable App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

Enable App Reports v3.0 to measure the following metrics:

* **Acquisition** - track referring URLs for app download campaigns.
* **Lifecycle** - foundation level of reporting provided by measurement sent on each app launch.
* **App Actions** - reports and pathing based on in-app actions.
* **Lifetime Value** - understand how users accrue value over time using app KPIs (such as purchases, ad views, video completes, social shares, photo uploads).
* **Timed Events** - measure the amount of time that elapses (in-app & total time) between key app actions (such as time before first purchase).

## Step 2. Enable Location Tracking {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

Enabling Location Tracking lets you:

* Track latitude and longitude data and report on it in Analysis Workspace and Mobile Services.
* Identify, create and visualize specific Points of Interest (POIs) within Mobile Services. POIs must be defined in the mobile SDK configuration file.
* Track bluetooth beacons (UUID, major, minor, and proximity).

## Step 3. (Optional) Enable/Disable Legacy Reporting and Attribution for Background Hits {#section_1708BCAA87AA4884986F7532759C5DD4}

Enabled background hits (hits generated when the app is in the background) means that they treated as regular foreground hits. They now show up in regular reporting and this also affects attribution. This configuration is usually only desirable to maintain consistency with legacy implementations.

Instead, we recommend that you "include background hits" in a [virtual report suite](/help/components/vrs/vrs-about.md). This allows you to see the hits but they will not affect visit and visitor counts adversely.
Mobile classifications are enabled after you enable **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

Classifications are used to categorize values into groups and report at the group level. For example, you can classify all Paid Search campaigns into a category like "pop music terms" and report on the success of that category relative to metrics like Instances (a.k.a. Click-throughs), and conversion to success events.

| Classification | Definition |
|--- |--- |
|First Launch Date|Date of first launch after installation or re-installation.   MM/DD/YYYY|
|App ID|Stores the Application name and version in the following format:   `[AppName] [BundleVersion]`  For example, `myapp 1.1.`|
|Launch Number|Number of times the application was launched or brought out of the background.|
|Days Since First Use|Number of days since first run.|
|Days Since Last Use|Number of days since last use.|
|Hour of Day|Measures the hour the app was launched and uses the 24-hour numerical format. Used for time parting to determine peak usage times.|
|Day of Week|Number of the week day the app was launched.|
|Device Name|Stores the device name.  Comma-separated two-digit string that identifies the device. The first number typically represents the device generation, and the second number typically versions different members of the device family.|
|Operating System Version|OS version.|
|Resolution|Width x Height in actual pixels.|
|Lifetime value (eVar)|Populated by  trackLifetimeValue methods.|
|Acquisition Source||
|Acquisition Medium||
|Acquisition Term||
|Acquisition Content||
|Acquisition Name||
|Location (Down to 10 km)|Populated by  trackLocation methods.|
|Location (Down to 100 m)|Populated by  trackLocation methods.|
|Location (down to 1 m)|Populated by  trackLocation methods.|
|Point of Interest Name|Populated by  trackLocation methods when device is in a defined POI.|
|Distance to Point of Interest Center|Populated by  trackLocation methods when device is in a defined POI.|
|In-App Message ID||
|In-App Message Online||
|Push Opt-In||
|Payload ID||
