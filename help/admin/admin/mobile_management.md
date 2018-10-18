---
description: Enabling mobile management activates the mobile solution variables that capture lifecyle and other metrics from mobile applications.
seo-description: Enabling mobile management activates the mobile solution variables that capture lifecyle and other metrics from mobile applications.
seo-title: Mobile Management
solution: Analytics
title: Mobile Management
topic: Admin tools
uuid: a7168e73-9e32-4088-8161-52abcbff7f8f
index: y
internal: n
snippet: y
---

# Mobile Management

Enabling mobile management activates the mobile solution variables that capture lifecyle and other metrics from mobile applications.

See [Mobile App Development & AppMeasurement Libraries](../data_collection/developer.md#concept_0151FC2D93434EE6BB3300D7F1A33E4A) for details on capturing lifecycle metrics in your mobile app.

This integration between Adobe Analytics and Mobile Services

* Lets you share your KPI (Key Performance Indicator) data from Mobile Services to Adobe Analytics. 
* Lets you enable location tracking. 
* Adds new reports under Analytics > Reports > Mobile App. 
* Adds 25 new Adobe Mobile classifications. 
* Adds 5 new Adobe Mobile metrics. 
* Adds new Adobe Mobile dimensions. 
* Synchronizes data to Analytics every 15 minutes

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Mobile Management]** > **[!UICONTROL Mobile Application Reporting]**.

## 1. Enable App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

Enable App Reports v3.0 to measure the following metrics:

* **Acquisition** - track referring URLs for app download campaigns. 
* **Lifecycle** - foundation level of reporting provided by measurement sent on each app launch. 
* **App Actions** - reports and pathing based on in-app actions. 
* **Lifetime Value** - understand how users accrue value over time using app KPIs (such as purchases, ad views, video completes, social shares, photo uploads). 
* **Timed Events** - measure the amount of time that elapses (in-app & total time) between key app actions (such as time before first purchase).

## 2. Enable Location Tracking {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

Enabling Location Tracking lets you:

* Track latitude and longitude data and report on it in Analysis Workspace and Mobile Services. 
* Identify, create and visualize specific Points of Interest (POIs) within Mobile Services. POIs must be defined in the mobile SDK configuration file. 
* Track bluetooth beacons (UUID, major, minor, and proximity).

## 3. (Optional) Enable/Disable Legacy Reporting and Attribution for Background Hits {#section_1708BCAA87AA4884986F7532759C5DD4}

Enabled background hits (hits generated when the app is in the background) means that they treated as regular foreground hits. They now show up in regular reporting and this also affects attribution. This configuration is usually only desirable to maintain consistency with legacy implementations.

Instead, we recommend that you “include background hits” in a [virtual report suite](virtual-report-suites.md#concept_FAD66217A68146B892AB76580DA62616). This allows you to see the hits but they will not affect visit and visitor counts adversely. 
Mobile classifications are enabled after you enable **[!UICONTROL Mobile Management]** > **[!UICONTROL Mobile Application Reporting]**.

Classifications are used to categorize values into groups and report at the group level. For example, you can classify all Paid Search campaigns into a category like "pop music terms" and report on the success of that category relative to metrics like Instances (a.k.a. Click-throughs), and conversion to success events. 

<table id="table_B3D8AD7DA1204AFEB909C47E1A7293A5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Classification </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>First Launch Date </p> </td> 
   <td colname="col2"> <p>Date of first launch after installation or re-installation. </p> <p><span class="codeph"> MM/DD/YYYY</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>App ID </p> </td> 
   <td colname="col2"> <p>Stores the Application name and version in the following format: </p> <p><span class="codeph"> [AppName] [BundleVersion]</span> </p> <p>For example,<span class="codeph"> myapp 1.1</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Launch Number </p> </td> 
   <td colname="col2"> <p>Number of times the application was launched or brought out of the background. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days Since First Use </p> </td> 
   <td colname="col2"> <p>Number of days since first run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days Since Last Use </p> </td> 
   <td colname="col2"> <p>Number of days since last use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hour of Day </p> </td> 
   <td colname="col2"> <p>Measures the hour the app was launched and uses the 24-hour numerical format. Used for time parting to determine peak usage times. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Day of Week </p> </td> 
   <td colname="col2"> <p>Number of the week day the app was launched. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Device Name </p> </td> 
   <td colname="col2"> <p>Stores the device name. </p> <p>Comma-separated two-digit string that identifies the device. The first number typically represents the device generation, and the second number typically versions different members of the device family. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Operating System Version </p> </td> 
   <td colname="col2"> <p>OS version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resolution </p> </td> 
   <td colname="col2"> <p>Width x Height in actual pixels. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lifetime value (eVar) </p> </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLifetimeValue</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acquisition Source </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acquisition Medium </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acquisition Term </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acquisition Content </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acquisition Name </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location (Down to 10 km) </p> </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLocation</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location (Down to 100 m) </p> </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLocation</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location (down to 1 m) </p> </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLocation</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Point of Interest Name </p> </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLocation</span> methods when device is in a defined POI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Distance to Point of Interest Center </p> </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLocation</span> methods when device is in a defined POI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In-App Message ID </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In-App Message Online </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Push Opt-In </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Payload ID </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

