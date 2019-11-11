---
description: AppMeasurement 3.x for Android
seo-description: Legacy documentation for AppMeasurement 3.x for Android
seo-title: AppMeasurement 3.x for Android
solution: Analytics
subtopic: Bookmarks
title: AppMeasurement 3.x for Android
topic: 
uuid: 
---

# AppMeasurement 3.x for Android

*Note: This document contains legacy information for previous versions of AppMeasurement, specifically for versions 3.x for Android.
For information on current AppMeasurement implementation, see [About AppMeasurement for Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).*

*Last updated 3/15/2018 AppMeasurement 3.x for Android*

Adobe AppMeasurement for Android lets you measure native Android applications in the Adobe Experience Cloud.

This guide is divided into two sections; one section for the Analyst that has Adobe Analytics experience and one section for the
Android developer with mobile app development experience.

**Supported Versions**: Android 2.0 or later.

**Download the Library**
Download instructions and links for all AppMeasurement mobile platforms are available at the Measuring and Optimizing
Mobile Applications page on Developer Connection. You must have a free Developer Connection account or a SiteCatalyst login to download the libraries. The download links do not appear until you have logged in.

## Analyst Quick Start

This section walks you through implementing the Android library and adding the code required for a standard implementation. Steps are included to show you how to send custom events and other data.

As the analyst, you need to enable the Mobile Application Reports for your report suite. If you have additional metrics to capture,you should provide your developer a description of the context data variables that should be sent by the application. For example, to collect a username after login, you could have your developer set the username into a context data variable called `myco.username`.

### Enable Mobile Application Reports in SiteCatalyst

SiteCatalyst provides an interface to enable Mobile App Lifecycle Tracking. This mapping lets SiteCatalyst automatically generate the Mobile Application Reports.

1. Open Admin Console > Report Suites > Edit Settings > Mobile Management > Mobile Application Reporting.
2. Click Enable Mobile App Lifecycle Tracking.

The lifecycle metrics are now captured, and Mobile Application Reports appear in the Reports menu in SiteCatalyst.

### Capture Additional Metrics using Processing Rules

If your implementation sends additional events and dimensions using context data, you must configure processing rules to capture that data.

Before creating Processing Rules, someone in your organization must become certified. For additional information, see the Processing Rules Help.

After Processing Rules are enabled, the Copy a Context Data Variable example demonstrates the process required to map context data.

### (Optional) Enable Offline Tracking

If you plan to store hits when the device is offline, your report suite must be timestamp-enabled.

After you enable offline tracking, all hits must be time-stamped or they are not collected. If you are currently reporting AppMeasurement data to a report suite that also collects data from JavaScript, you might need to set up a separate report suite for mobile data to avoid data loss, or include a custom timestamp on JavaScript hits using the s.timestamp variable.

If you are unsure if your report suite is timestamp-enabled, contact Client Care.

## Developer Quick Start

This section walks you through selecting and configuring the events, eVars, and props that you'll use to collect Android data. Steps are also included to create Processing Rules to copy the context data sent by the Android libraries to these variables.

The steps to implement the Android library and start sending measurement data are as follows:

* Get the Library
* Add the Library to your Project
* Add App Permissions
* A Quick Word on the TrackingHelper
* Implementation

### Get the Library
Visit Measuring and Optimizing Mobile Applications on Developer Connection to download the Android library. After unzipping the download file, you'll have the following software components:

* admsAppLibrary.jar: Library designed for use with Android devices and simulators. Requires Android 2.0 or later.
* Examples\TrackingHelper.java: Optional class that is designed to keep tracking code separate from your application logic.

### Add the Library to your Project

1. In the Eclipse IDE, right-click on the project name.
2. Select Build Path > Add External Archives.
3. Select `admsAppLibrary.jar`.
4. Click Open.
5. Right-click the project again, then select Build Path > Configure Build Path.
6. Click the Order and Export tab.
7. Ensure that `admsAppLibrary.jar` is selected.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using import com.adobe.ADMS.*;

### Add App Permissions

The AppMeasurement Library requires the following permissions to send data and record offline tracking calls:

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### A Quick Word on the TrackingHelper

The SDK includes an additional, optional class, called TrackingHelper. TrackingHelper provides a way to separate your measurement code from your application logic.

Consider the following example: In your application, you want to send an event that tracks each login. You could add the following code directly after your login code to send this event (don't worry about the code details, we'll get to those later):

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

This direct approach is OK, but wouldn't you rather put this code somewhere else so it is out of your way while you are developing your application? The TrackingHelper is that "somewhere else". Inside of TrackingHelper, you could place this code in a method called trackLogonEvent:

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

Now, in your application code, you can track a logon event with a simple call to trackLogonEvent:

TrackingHelper.trackLogonEvent("username");

The measurement call in your application code is down to a single line. Plus, if the underlying measurement logic needs to change, you'll need to update only the TrackingHelper. If another developer adds to your code, he or she can use the simplified methods you've defined without taking a crash course in the AppMeasurement library.

We think you'll prefer using the TrackingHelper for new implementations, even though setup requires an extra minute or two. The remaining steps in this guide walk you through the steps to set up TrackingHelper and start sending measurement data.

Be sure to copy TrackingHelper.java to a directory that contains class files for your app, and replace the package name at the top of this file to match your package structure (com.company.application). If you'd rather implement without TrackingHelper, you can find several samples inside of TrackingHelper that you can copy to your application.

### Implementation

1. Open TrackingHelper.java and update TRACKING_RSID and TRACKING_SERVER with your report suite ID and tracking server. For example:

```
private static final String TRACKING_RSID = "rsid";
private static final String TRACKING_SERVER = "server";
```

These values are required, and must be correct or measurement won't work. If you are unsure about these values, ask your SiteCatalyst expert.

2. Find the configureAppMeasurement method. This is where you enable SSL, enable offline tracking, and make other global changes to your configuration. For now, uncomment the line to enable debugLogging until things are working the way you'd expect.

3. Add a call to configureAppMeasurement from the root activity in your application.

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

That is all the code you need to start tracking custom metrics. However, with a few additional lines of code, you can enable lifecycle tracking to automatically send lifecycle metrics, including launches, upgrades, crashes, and daily and monthly users.

The AppMeasurement library does all of the heavy lifting, all you need to do is add two method calls to each of your application's Activity classes.

### (Recommended) Track Lifecycle Events

When lifecycle tracking is enabled, each time your app is launched, a single hit is sent to track installs, upgrades, engaged days, and the other Lifecycle Metrics.

To start tracking lifecycle events, In your app, add calls to the onResume() and onPause() methods in each Activity inside of your application, as shown in the following example. We also recommend passing the Activity or Service as the context object instead of the global Application context.

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

That's it! You've now implemented basic lifecycle tracking in your Android app. After your Web Analyst configures SiteCatalyst to process the AppMeasurement metrics you are reporting, your SiteCatalyst report suite will contain the default lifecycle metrics.

Where to go from here:

* (Optional) Track Custom Events. Add custom methods to TrackingHelper to track all of the events you want to measure in your application. You might add methods to track logons, in-app purchases, and so on.
* (Optional) Track App States. An application state is similar to a page view. This section shows you how to add a custom method to TrackingHelper to track an app state.
* Video Measurement Quick Start. Add code to track video metrics including video views, total time played, and most popular videos.

### (Optional) Track Custom Events

Custom events are success metrics that are unique to your application. You might send a custom event when a user logs in, initiates an in-app purchase, or clicks a link to your Facebook page. The tracking helper class contains an example that shows how to track a custom event. You can use this method as a template to add additional event tracking methods.

In TrackingHelper.java, define a custom event track method:
```

public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

Throughout your code, you can call this method to track a custom event:

`TrackingHelper.trackCustomEvents();`

Use this process to add as many event tracking methods as you need. A Quick Word on the TrackingHelper contains an example method to track a login event.

### (Optional) Track App States

The tracking helper class also contains an example that shows how to track an application state. Tracking a custom state is very similar to tracking an event, the only difference is you use the trackAppState method instead of trackEvents.

```
measure.trackAppState("name", contextData);
```

From a reporting standpoint, trackAppState increments page views, while trackEvents does not.

## Video Measurement Quick Start

Video measurement is described in the Measuring Video in SiteCatalyst guide. The general process to measure video is very similar across all AppMeasurement platforms. This quick start section provides a basic overview of the developer tasks along with code samples.

The same library, admsAppLibrary.jar, is used for application and video tracking. The documentation refers to these methods as the media module for consistency across platforms.

You need to have a measurement instance configured before you can use the media module.

To implement video tracking on Android, complete the following tasks:

* Map Player Events to SiteCatalyst Variables
* Configure Milestones, Segments, and Call Frequency
* Track Player Events

### Map Player Events to SiteCatalyst Variables

To configure video measurement, you need to map the SiteCatalyst events and eVars that you selected for video tracking to context data variables. For more information, see SiteCatalyst Video Configuration.

Your Web Analyst should provide you with a Video Implementation Worksheet that contains a list of the SiteCatalyst variables that they configured to receive video data:

* Video Name (eVar): eVar2
* Video Name (Prop): prop2
* Segments (eVar): eVar3
* Content Type (eVar): eVar1
* Video Time (Event): event3
* Video Views (Event): event1
* Video Completes (Event): event7
* Video Segment Views (Event): event2

1. Add the following code after the code you added in Implementation, replacing the SiteCatalyst variable you selected with the example in the code:

```
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
contextDataMapping.put("a.media.name", "eVar2,prop2");
contextDataMapping.put("a.media.segment", "eVar3");
contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
namespace
contextDataMapping.put("a.media.timePlayed", "event3");
contextDataMapping.put("a.media.view", "event1");
contextDataMapping.put("a.media.segmentView", "event2");
contextDataMapping.put("a.media.complete", "event7");
mediaMeasure.ContextDataMapping = contextDataMapping;
```

2. Configure Milestones, Segments, and Call Frequency.

3. Track Player Events.


### Configure Milestones, Segments, and Call Frequency

Milestones let you send an event when a specific point in the video is reached. Segments let you divide your video into sections for more granular tracking. Call frequency lets you send measurement calls with time viewed at specific intervals. For more information, see Video Metrics.

### Map Milestones

You can define milestones based on a percentage of total length or based on seconds elapsed. This example defines milestones as a percentage of total length. For a 2 minute video, the following code sends milestone events at 30 seconds, 60 seconds, and 90 seconds.

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### Map Offset Milestones

This example defines milestones by seconds elapsed from the beginning of the video. For a 2 minute video, the following code send milestone events at 20 seconds, 40 seconds, and 60 seconds regardless of the total video length.

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### Examples

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### Track Player Events
To measure video, you need to add code that tells the media module when events occur in your player (using the open, play, stop, and close methods). When a user starts playing a video, you need to call the play method so the media module starts counting seconds viewed. 

If the user pauses the video, you need to call stop so the count is paused. This is typically performed using event handlers that are exposed by your player.

For example:

Load: Call open and play

Pause: Call stop. For example, if a user pauses a video after 15 seconds, call stop("Video1",15)

Buffer: Call stop while the video buffers. Call play when playback resumes.

Resume: Call play. For example, when a user resumes a video after initially playing 15 seconds of the video, call
s.play("Video1",15).

Scrub (slider): When the user drags the video slider, call stop. When the user releases the video slider, call play.

End: Call stop, then close. For example, at the end of a 100-second video, call stop("Video1",100), then close("Video1").

To accomplish this, you can define four custom functions that you can call from the media player event handlers. The various parameters passed into open, play, stop, and close come from the player. The following pseudocode demonstrates how this might be done:

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## Lifecycle Metrics

This worksheet lists the metrics and dimensions that are measured when automatic lifecycle tracking is enabled.

### Lifecycle Metrics and Dimensions
When configured, lifecycle metrics are sent in context data parameters to Analytics, parameters to Target with each mbox call, and as a signal to audience management. Analytics and Target use the same format, while audience management uses a different prefix for each metric.

For Analytics, the context data that is sent with each lifecycle tracking call is automatically captured in and reported using the metric or dimension listed in the first column, with the exceptions noted in the description column.

| Metric | Analytics Context | Analytics Context Audience Manager Signal Description | Data/Target Parameter |
|--- |--- |--- |--- |
|First Launches| a.InstallEvent|c_a_InstallEvent|Triggered on first run after installation (or re-installation).|
|Upgrades|a.UpgradeEvent|c_a_UpgradeEvent| Triggered on first run after upgrades (anytime the version number changes).|
|Daily Engaged Users|a.DailyEngUserEvent|c_a_DailyEngUserEvent|Triggered when the application is used on a particular day.|
|Monthly Engaged Users|Monthly Engaged Users|a.MonthlyEngUserEvent|Triggered when the application is used during a particular month.|
|Launches|a.LaunchEvent|c_a_LaunchEvent|Triggered on every run, including crashes and installs.| Launches Also triggered on a resume from background when the lifecycle session timeout has been exceeded.|
|Crashes|a.CrashEvent|c_a_CrashEvent|Triggered when the application does not exit gracefully. Event is sent on application start after crash (the application is considered to crash if quit is not called).|
|Previous Session Length|a.PreviousSessionLength|Cc_a_PreviousSessionLength|Aggregated total Previous Session Length in seconds.|

*Note: **Daily Engaged Users** and  **Monthly Engaged Users** are not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture these metrics.*

### Dimensions

| Metric | Analytics Context Data/Target Parameter | Analytics Context Audience Manager Signal | Description |
|--- |--- |--- |--- |
|Install Date| a.InstallDate|c_a_InstallDate|Date of first launch after installation. MM/DD/YYYY|
|Upgrades|a.UpgradeEvent|c_a_UpgradeEvent| Triggered on first run after upgrades (anytime the version number changes).|
|App ID|a.AppID|c_a_AppID|Stores the Application name and version in the following format:`[AppName] [BundleVersion]`. For example, myapp 1.1.|
|Days since first use|a.DaysSinceFirstUse|c_a_DaysSinceFirstUse|Number of days since first run.|
|Monthly Engaged Users|Monthly Engaged Users|a.MonthlyEngUserEvent|Triggered when the application is used during a particular month.|
|Launches|a.LaunchEvent|c_a_LaunchEvent|Triggered on every run, including crashes and installs.| Launches Also triggered on a resume from background when the lifecycle session timeout has been exceeded.|
|Crashes|a.CrashEvent|c_a_CrashEvent|Triggered when the application does not exit gracefully. Event is sent on application start after crash (the application is considered to crash if quit is not called).|
|Previous Session Length|a.PreviousSessionLength|Cc_a_PreviousSessionLength|Aggregated total Previous Session Length in seconds.|
|Days since last use|a.DaysSinceLastUse|c_a_DaysSinceLastUse|Number of days since last use.|
|Day of Week|a.DayOfWeek|c_a_DayOfWeek|Number of the week day the app was launched.|
|Hour of Day|a.HourOfDay|c_a_HourOfDay|Measures the hour the app was launched. 24 hour numerical format. Used for time parting to determine peak usage times.|
|Operating System Version|a.OSVersion|c_a_OSVersion|OS version.|
|Days since last upgrade|a.DaysSinceLastUpgrade|c_a_DaysSinceLastUpgrade|Number of days since the application version number has changed.|
|Launches since last upgrade|a.LaunchesSinceUpgrade|c_a_LaunchesSinceUpgrade|Number of launches since the application version number has changed.|
|Device Name|a.DeviceName|c_a_DeviceName|Stores the device name.|iOS: Comma-separated 2 digit string that Identifies the iOS device. The first number typically represents the device generation, and the second number typically versions different members of the device family. See iOS Device Versions for a list of common device names.|
|Carrier Name|a.CarrierName|c_a_CarrierName|Stores the name of the mobile service provider as provided by the device.|
|Resolution|a.Resolution|c_a_Resolution|Width x Height in actual pixels|

*Note: **Days since last upgrade**,  **Launches since last upgrade** and **Carrier name** are not automatically stored in an Analytics variable. You must create a processing rule to copy these values to an Analytics variable for reporting.*

## Context Data

Context data is the preferred method to send application data to collection servers.

Instead of explicitly assigning values to props and eVars, you can use context data variables to send name value pairs that are mapped in the SiteCatalyst. Based on these key value pairs, you can set events, copy values to eVars and props and execute additional conditional statements. This helps prevent you from making code updates to support different report suite configurations.

There are two ways to send context data with the tracking methods. Any context data set directly on the PersistentContextData object is sent in with each call. You can also pass context data as a parameter to a single tracking call that is sent with that call only.

### Persistent Context Data

Values placed in Persistent Context Data are sent with each server call. In the following example, "key" and "value" are sent with all trackAppState calls:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### Single Call Context Data

To send context data for a single call, send Context Data as a parameter to the tracking call (trackAppState, trackEvents, and so on).

In the following example, "key" and "value" are sent with all three trackAppState calls. However, "key2" and "value2" are sent only with the second trackAppState call:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## Configuration Variables

The following variables are set when the application launches:

*Note: All configuration variables are optional except ReportSuiteID and trackingServer.*

**Shared Instance**

Before making measurement calls, you must retrieve an instance of the library for each method you call on the measurement library:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Note: Configuration variables are private. Use the get and set methods to change these values.*

### Configuration Variables

**reportSuiteIDs**: (Required) The report suite or report suites (multi-suite tagging) that you wish to track. To track to multiple report suites, pass a comma delimited list of the names of each report suite.

You cannot override this variable for a single call, you must change the persistent value.

Syntax:

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

Examples:

`measure.setReportSuiteIDs("rsid");`

Multi-suite tagging:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**: (Required) Identifies the collection server.

This variable should be populated with your tracking server domain, without an "http://" or https://" protocol prefix. The protocol prefix is handled automatically by the library based on the ssl variable.

If ssl is true, a secure connection is made to this server. If ssl is false, a non-secure connection is made to this server.

You cannot override this variable for a single call, you must change the persistent value.

Syntax:

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

Examples:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**: Default: uuid
Unique identifier for each visitor. If you do not set a custom visitorID, a unique visitorID is
generated.

We recommend using the default unless you have a specific use case to set the visitorID. Setting a custom visitorID has the potential to cause duplicate visits when using lifecycle tracking. To avoid this, set the visitor ID before you configure app measurement.

**characterSet**: Default is UTF-8

Syntax:

```
String getCharSet()
void setCharSet(String charSet)
```

Examples:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**:Default is none (value defined for report suite is used)

The Currency Code used for purchases or currency events that are tracked in the Android application.

Syntax:

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

Examples:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**: Default is 5 minutes

Specifies the length of time, in seconds, that must elapse between app launches before the launch is considered a new session. This timeout also applies when your application is sent to the background and reactivated. The time that your app spends in the background is not included in the session length.

Syntax:

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

Examples:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**: Default is false

Enables (true) or disables (false) sending measurement data via SSL (HTTPS). You cannot override this variable for a single call, you must change the persistent value.

Syntax:

`void setSSL(boolean ssl)`

Examples:

`measure.setSSL(true);`

**debugLogging** Default is false

Enables (true) or disables (false) viewing debug information and the library version in the output console. By default, this variable is false. You cannot override this variable for a single call, you must change the persistent value.

Syntax:

`void setDebugLogging(boolean debugLogging)`

Examples:

`measure.setDebugLogging(true);`

##  Tracking Variables

**Shared Instance**

Before making measurement calls, you must retrieve an instance of the library for each method you call on the measurement library:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```
*Note: Configuration variables are private. Use the get and set methods to change these values.*

### Persistent Tracking Variables

**Evar**: Sets the specified eVar to the provided value. The eVar is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clear vars.

Syntax:

`void setEvar(int evarNum, String evarValue)`

Example:
`measure.setEvar(1, "value");`

**Prop**: Sets the specified prop to the provided value. The prop is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clearVars.

Syntax:

`void setProp(int propNum, String propValue)`

Example:

`measure.setProp(1, "value");`

**Hier**: Sets the specified heir variable to the provided value. The heir variable is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clearVars.

Syntax:

`void setHier(int hierNum, String hierValue)`

Example:

`measure.setHier(1, "value");`


**ListVar**: Sets the specified listVar to the provided value. The listVar is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clearVars.

Syntax:

`void setListVar(int listNum, String listValue)`

Example:

`measure.setListVar(1, "value");`

**purchaseID**: The purchaseID is used to keep an order from being counted multiple times by SiteCatalyst.

Whenever the purchase event is used on your site, you should assign this purchase a unique id using the purchaseID variable.

`measure.setPurchaseID("unique_id");`

**transactionID**: Integration Data Sources use a transaction ID to tie offline data to an online transaction (like a lead or purchase generated online).

Each unique transactionID sent to Adobe is recorded in preparation for a Data Sources upload of offline information about that transaction.

`measure.setTransactionID("unique_id");`

**appState**: (page name)The value provided for the app state is stored in the page name variable.

`measure.setAppState("state");`

**channel**: measure.setChannel("mobile");

**appSection**: The value provided for the app section is stored in the server variable.

Syntax:

`void setAppSection(String Section)`

Example:
`measure.setAppSection("news");`

**campaign**

Syntax:

`void setCampaign(String Campaign)`

Example:

`measure.setCampaign("112233");`

**products**

Syntax:

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

Example:

`measure.setProducts("Running;Shoe");`

**events**

Syntax:

`void setEvents(String Event) //comma-delimited list`

Example:

`measure.setEvents("event1, event2");`

**geoState**

Syntax:

`void setGeoState(String GeoState)`

Example:

`measure.setGeoState("UT");`

**geoZip**

Syntax:

`void setGeoZip(String GeoZip)`

Example:

`measure.setGeoZip("12345");`

**Persistent Context Data**: Values placed in Persistent Context Data are sent with each server call. To send context data for a single call, send a contextData hashtable as a parameter to the tracking call (trackAppState, trackEvents, and so on).

Example:

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```
See Context Data.

**linkTrackVars**: A comma delimited list of variable names that restricts the current set of variables for link tracking. If linkTrackVars is not defined, AppMeasurement for Android sends all defined variables with a trackLink call.

Syntax:

`void setLinkTrackVars(String Vars) //comma-delimited list`

Example:

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**: A comma delimited list of events that restricts the current set of events for link tracking. If linkTrackEvents is not defined, AppMeasurement for Android sends all events with a trackLink call.

Syntax:

`void setLinkTrackEvents(String Events) //comma-delimited list`

Example:

`measure.setLinkTrackEvents("event1, event2");`

## Methods

This section contains a list of the methods provided by the Android library.

**Shared Instance**

Before making measurement calls, you must retrieve an instance of the library for each method you call on the measurement library:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### Initial Configuration

This method configures the required variables and must be called before other methods.

**configureMeasurement**: This method is used to configure the two parameters required to start application measurement. You must set the reportSuiteIDs and trackingServer values on the measurement object using this method prior to sending any server calls.

Syntax:

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

Examples:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### Event and State Tracking

These are the primary methods used to track custom events and app states.

**trackAppState**: This is the recommended way to track application states in your application. The value provided in appState appears as the page name variable of the server call. The appState string must be provided for each call since it isn't carried over to the next call.

Context data sent with this call is appended to any values in persistentContextData and sent with the call. Only values set in persistentContextData remain for the next call.

Syntax:

`void trackAppState(string AppStateName)`

Examples:

`measure.trackAppState("state");`
```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**: This is the recommended way to track events in your application. trackEvents is similar to trackAppState, but sends events instead of page names. Events are provided as a comma delimited string. The events string must be provided for each call since it isn't carried over to the next call.

This method makes an underlying call to trackLinkURL where linkURL is set to nil, linkType is set to "o", and the linkName is populated with the application ID.

This means that your linkTrackVars and linkTrackEvents apply for calls to trackEvents.

Context data sent with this call is appended to any values in persistentContextData and sent with the call. Only values set in persistentContextData remain for the next call.

Syntax:

`void trackEvents(string Events)`

Examples:

`measure.trackEvents("event1");`
```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**Import note if you are using the trackLink method**

trackEvents makes an underlying call to trackLink, where linkURL is set to null, linkType is set to "o", and the linkName is populated with the application ID. This is done to prevent the page view (state view) count from being incremented each time you send an event.

If you are calling trackLink directly and setting values for linkTrackVars and linkTrackEvents, these variable and event restrictions apply to TrackEvents. This means that only variables and events defined on these lists are sent with TrackEvents. You should set linkTrackVars and linkTrackEvents to null unless you want those restrictions applied to trackEvents. 

### Advanced Tracking (track and trackLink)

These methods provide additional tracking options, allowing you to populate props, eVars, and other SiteCatalyst variables directly. These should be used by customers with an existing implementation or customers who are very familiar with other SiteCatalyst implementations.

`track` and `trackLink` are the core measurement methods that are implemented in all versions of the Adobe Measurement Libraries across multiple platforms. In most circumstances when tracking mobile applications, it is easier to use trackAppState, trackEvents methods rather than calling track and trackLink directly.

Page view tracking (track) and link tracking (trackLink) sends all persistent variables that have values (non-null, non-empty, non-zero). You should reset or empty all variables, as needed, before calling track or trackLink.

*Note: Due to the multi-threaded nature of modern applications, setting persistent variable values to send with a future tracking call is not recommended (using setEvar, setProp, setHier, SetListVar, and setPersistentContextData). For example, if a variable value is set in multiple threads, the value might be in an inconsistent state when the tracking callis made. To avoid this, we recommend passing context data with each tracking call and setting the variable value in Processing Rules.

**Method Descriptions**

**track**: Sends a standard page view, along with any additional variables that are set on the measurement object, to the collection server.

Each call to track sends all persistent data defined on the measurement object (these are listed in the description for clearVars), plus any contextData or variables you provide for that call only. If you send a variable that is defined, any value in the corresponding persistent variable is overwritten.

Syntax:

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

Examples:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**: Sends custom, download or exit link data to Adobe data collection servers, along with any trackconfig variables that have values.

Use trackLink to track all activity that should not capture a page view.

Syntax:

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**: Identifies the clicked URL. If no URL is specified, the name is used. Use this only when
linking to a Web page from within your Android application. Otherwise, pass in null for this parameter.

**linkType**: Identifies the link report that will display the URL or name. Supported values include:
* “o” (Custom Links)
* “d” (File Downloads)
* “e” (Exit Links)

**linkName**: The name that appears in the link report. If no name is specified, the report uses the URL.

To collect data, you must specify either the linkURL, or linkName parameter. When not using one of these parameters, context data or additional variables, pass in null as the value.

Examples:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**: Sets the specified eVar to the provided value. The eVar is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clear vars.

Syntax:

`void setEvar(int evarNum, String evarValue)`

**setProp**: Sets the specified prop to the provided value. The prop is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clear vars.

Syntax:

`void setProp(int propNum, String propValue)`

**setHier**: Sets the specified heir variable to the provided value. The heir variable is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clear vars.

Syntax:

`void setHier(int hierNum, String hierValue)`

**setListVar**: Sets the specified listVar to the provided value. The listVar is sent with all tracking calls until it is cleared by setting it to an empty string, or by calling clear vars.

Syntax:

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**: Values placed in Persistent Context Data are sent with each server call. To send context data for a single call, send a contextData hashtable as a parameter to the tracking call (trackAppState, trackEvents, and so on).

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

See Context Data.

**clearVars**: Removes values from the following variables on the object:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Syntax:

`void clearVars()`

Examples:
`measure.clearVars();`

**Offline Tracking**

*Note: To enable offline AppMeasurement, your report suite must be timestamp-enabled.*

The following variables let you store measurement calls when the application is offline. To enable offline AppMeasurement, your report suite must be timestamp-enabled. After you make this change, all hits must be time-stamped or they are dropped. If you are currently reporting AppMeasurement data to a report suite that also collects data from JavaScript, you might need to set up a separate report suite for Offline AppMeasurement to avoid data loss.

When enabled, Offline AppMeasurement behaves in the following way:
* The application sends a server call, but the data transmission fails.
* AppMeasurement generates a timestamp for the current hit.
* AppMeasurement buffers the hit data, and backs up buffered hit data to persistent storage to prevent data loss.

At each subsequent hit, or at the interval defined by offlineThrottleDelay, AppMeasurement attempts to send the buffered hit data, maintaining the original hit order. If the data transmission fails, it continues to buffer the hit data (This continues while the device is offline).

### Configuration Methods

**setOfflineTrackingEnabled**: Default is false. Enables or disables offline tracking for the measurement library.

Syntax:

`void setOfflineTrackingEnabled(boolean Enabled);`

Examples:
``
measure.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**: Default is 1000. Maximum number of offline hits stored in the queue. If the hit limit is set over 5000, performance may suffer.

Syntax:

`void setOfflineHitLimit(int offlineHitLimit)`

Examples:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**: Returns the number of stored tracking calls in the offline queue.

Syntax:

`int getTrackingQueueSize()`

Examples:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**: Removes all stored tracking calls from the offline queue.

Syntax:

`void clearTrackingQueue()`

Examples:

`measure.clearTrackingQueue();`

**Warning: use caution when clearing the queue manually as it cannot be reversed.**


**setOnline and setOffline**: Manually set the online or offline state of the measurement object. The library automatically detects when the device is offline or online, so these methods are needed only if you want to force measurement offline. SetOnline is used only to return to the online state after manually going offline.

When measurement is offline:

* If offlineTrackingEnabled is true: hits are stored until measurement is online.
* If offlineTrackingEnabled is false: hits are discarded.

Syntax:

```
void setOnline()
void setOffline()
```

Examples:

```
measure.setOffline();
measure.setOnline();
```

## Offline Tracking

AppMeasurement lets you measure application usage even when the Android device is offline.

*Note: To enable offline AppMeasurement, your report suite must be timestamp-enabled.*

See Offline Tracking.

## Target

Adobe provides the ability to deliver targeted content within Android applications.

The content returned from Test&Target can be any text-‐based content such as HTML, XML or plain text. Once the content is loaded, it is then up to the Android application developer to decide how the content is consumed within the application. The content can be displayed as HTML, or used to change the behavior of the application. This guide provides a simple use example of the Test&Target classes.

Requirements

* JDK 5/6/7
* Android SDK for Platform 1.5 or later.

The example in this section is based on Eclipse.

**Get the Library**

Visit Measuring and Optimizing Mobile Applications on Developer Connection to download the Android library.

After unzipping the download file, you'll have the following software components:

* admsAppLibrary.jar: Library designed for use with Android devices and simulators. Requires Android 2.0 or later.
* Examples\TrackingHelper.java: Optional class that is designed to keep tracking code separate from your application logic.

**Add the Library to your Project**

1. In the Eclipse IDE, right-click on the project name.
2. Select Build Path > Add External Archives.
3. Select admsAppLibrary.jar.
4. Click Open.
5. Right-click the project again, then select Build Path > Configure Build Path.
6. Click the Order and Export tab.
7. Ensure that admsAppLibrary.jar is selected.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using `importcom.adobe.ADMS.*;`

**Add App Permissions**

The AppMeasurement Library requires the following permissions to send data and record offline tracking calls:

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Example

After you add the library to your project and add app permissions, you can use the two Test&Target classes, MboxFactory and Mbox.

The following example shows how to load HTML content from Test&Target into a WebView within a simple Android application. This example assumes that the associated HTML Offers and campaign have already been created in the Test&Target Admin Tool, and that the campaign has been approved.

1. Complete the steps in Implementation, then import the testandtarget package at the top of your Application or Activity
subclass:

`com.adobe.adms.testandtarget.*;`

2. Follow the numbered code below for creating an mbox (see comments for explanation of each line of code). To complete this step, you will need to know your client code and the name of the mbox used in the campaign setup in the Test&Target Admin Tool.

```
public class AndroidDemoApplication extends Activity {
private WebView _webView;
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
_webView = new WebView(this);
setContentView(_webView);
// 1. Create an instance of the MboxFactory class with your client code.
MboxFactory factory = new MboxFactory("androiddemo16");
// 2. Use the MboxFactory instance to create an Mbox.
Mbox mbox = factory.create("DemoApp");
// 3. Set the default content for the Mbox.
mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
/**
* 4. Create a custom MboxContentConsumer to consume the content returned. The
* CustomMboxContentConsumer class defined below simply displays the content
* returned in a BrowserField as HTML.
*/
CustomConsumer consumer = new CustomConsumer(_webView);
mbox.addOnLoadConsumer(consumer);
// 5. Load the Mbox.
mbox.load();
...
```

3. Define the custom class that implements the MboxContentConsumer interface. This abstract interface only requires that you define a method named “consume” to pass content into. The CustomConsumer class defined below simply displays the content in a WebView.

```
class CustomConsumer implements MboxContentConsumer {
private WebView _view;
public CustomConsumer(WebView webview) {
_view = webview;
}
public void consume(String content) {
_view.loadData(content, "text/html", "utf-8");
}
}
```

4. Right-click your project, and select Run As > Android Application to build and test your application. If you have correctly setup and approved your Test&Target campaign, you should see your offer displayed in the Android device emulator.

**Lifecycle Metrics**

If lifecycle metrics are enabled, lifecycle metrics are sent as parameters to each mbox load.

* (Recommended) Track Lifecycle Events
* Lifecycle Metrics

## Audience Management

Adobe provides the ability to send signals and retrieve visitor segments from audience management.

### Requirements

* JDK 5/6/7
* Android SDK for Platform 1.5 or later.

The example in this section is based on Eclipse.

### Get the Library

Visit Measuring and Optimizing Mobile Applications on Developer Connection to download the Android library.

After unzipping the download file, you'll have the following software components:

* admsAppLibrary.jar: Library designed for use with Android devices and simulators. Requires Android 2.0 or later.
* Examples\TrackingHelper.java: Optional class that is designed to keep tracking code separate from your application logic.

### Add the Library to your Project

1. In the Eclipse IDE, right-click on the project name.
2. Select Build Path > Add External Archives.
3. Select admsAppLibrary.jar.
4. Click Open.
5. Right-click the project again, then select Build Path > Configure Build Path.
6. Click the Order and Export tab.
7. Ensure that admsAppLibrary.jar is selected.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using `importcom.adobe.ADMS.*;`

### Add App Permissions

The AppMeasurement Library requires the following permissions to send data and record offline tracking calls:
* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Code Sample

After you add the library to your project, you can use the ADMS_AudienceManager class. To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. Configure audience management:

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

Replace mycompany.demdex.net with your endpoint. Audience management can be configured at any point in your
application.


2. Optionally set the dpid and dpuuid.

`ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. Create a trait dictionary and submit the dictionary in a signal.

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

The visitor profile dictionary is returned in the callback as the content parameter.

### Lifecycle Metrics

If lifecycle metrics are enabled and audience management is configured in application:didFinishLaunchingWithOptions:, a signal containing lifecycle metrics is sent after configuration completes.

* (Recommended) Track Lifecycle Events
* Lifecycle Metrics

### ADMS_AudienceManager Reference

**Methods**

**ConfigureAudienceManager**: Sets the audience management endpoint.

Syntax:

`public static void ConfigureAudienceManager(String server, Context context);`

Example:

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**: Returns boolean indicating whether or not Audience Manager methods will provide debug logging in your console.

Syntax:

`public static boolean GetDebugLogging();`

**GetDpid**: Returns the dpid.

Syntax:

`public static String GetDpid();`

**GetDpuuid**: Returns the dpuuid.

Syntax:

`public static String GetDpuuid();`

**GetVisitorProfile**: This method can be called at any time after you've submitted a signal to retrieve the most recent visitor profile.

The visitor profile contains all of the key value pairs that were returned in the stuff object.

Syntax:

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**: Enables or disables debug logging in your console.

Syntax:

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**: If newDpid and newDpuuid are set, they will be sent with each signal.

Syntax:

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**: Sends in a dictionary of traits and receives the updated visitor profile in callback.

The uuid from the JSON response is stored internally and used with all subsequent signals. A pixel request is also sent to each URL found in the dests object.

Syntax:

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### Interfaces

**Methods**


**AudienceManagerCallback**

Syntax:

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

Interface for object used in callback from SubmitSignal call.


## PhoneGap Plug-in

This plug-in lets you send Android AppMeasurement calls from your PhoneGap project.

For help creating a PhoneGap project, see PhoneGap Getting Started with Android.

To download the plug-in, see PhoneGap iOS and Android Plug-ins for SiteCatalyst.

### Include the Plug-in

1. Copy ADMS_plugin.java to the package in your src folder.
2. copy ADMS_Helper.js to the assets/www/js folder in your PhoneGap project.
3. In the res/xml folder, open config.xml file and register an new plugin by creating a new child node under plugins: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

For example, if you package is named com.example.phonegaptest, then your plugin node would be the following: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### Include the AppMeasurement Library

To download the AppMeasurement library, see Get the Library.

1. Copy admsAppLibrary.jar to the libs folder in your PhoneGap project.
2. Verify admsAppLibrary.jar is in your build path by right-clicking on libs > Build Path > Configure Build Path.
3. In the Libraries tab, if it's not already in your list, click Add JARs and select admsAppLibrary.jar from your libs folder.


### Lifecycle Metrics Auto Tracking

Tracking the Lifecycle Metrics requires configuration outside of PhoneGap. To enable Lifecycle Auto Tracking, complete the Implementation steps in the Developer Quick Start.

### Use the Plug-in

In html files where you want to use tracking, include:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

That's it, you are now ready to make measurement calls. See PhoneGap Plug-in Methods.

### Troubleshooting

**My syntax is correct, why is the code in the plugin not getting reached?**

Check your output console for the following error: `java.lang.ClassNotFoundException: ADMS_plugin`

If this error occurs, make sure you did step 3 in the Include the Plug-in section.

## PhoneGap Plug-in Methods

In html files where you want to use these methods, include:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**Configuration Methods**


**configureMeasurementWithReportSuiteIDsTrackingServer**: This method is used to configure the two parameters required to start application measurement. You must set the reportSuiteIDs and trackingServer values on the measurement object using this method prior to sending any server calls.

Syntax:

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

Example:

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline and setOffline**: Manually set the online or offline state of the measurement object. The library automatically detects when the device is offline or online, so these methods are needed only if you want to force measurement offline. SetOnline is used only to return to the online state after manually going offline.

When measurement is offline:

* If offlineTrackingEnabled is true: hits are stored until measurement is online.
* If offlineTrackingEnabled is false: hits are discarded.

Syntax:

```
void setOnline();
void setOffline();
```

Example:

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**: Enables (true) or disables (false) viewing debug information. By default, this variable is false.

You cannot override this variable using variable overrides.

Syntax:

`void setDebugLogging(bool debugLogging);`

Example:

`ADMS.setDebugLogging(true);`

### Event and State Tracking Methods


**trackAppState**: This is the recommended way to track application states (for example, pages) in your application. The value provided in appState appears as the page name variable of the server call. The appState string must be provided for each call since it isn't carried over to the next call.

Syntax:

`void trackAppState(string stateName);`

Example:

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**: This is the recommended way to track application states (for example, pages) in your application. The value provided in appState appears as the page name variable of the server call. The appState string must be provided for each call since it isn't carried over to the next call.

Context data sent with this call is appended to any values in persistentContextData and sent with the call. Only values set in persistentContextData remain for the next call.

Syntax:

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData: JSON object with key-value pairs to send in context data.

Example:

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**: This is the recommended way to track events in your application. trackEvents is similar to trackAppState, but sends events instead of page names. Events are provided as a comma trackEvents delimited string. The events string must be provided for each call since it isn't carried over to the next call.

This method makes an underlying call to trackLinkURL where linkURL is set to null, linkType is set to "o", and the linkName is populated with the application ID.

This means that your linkTrackVars and linkTrackEvents apply for calls to `trackEvents`.

Syntax:

`void trackEvents(string eventNames);`

Example:

`ADMS.trackEvents("login,event2");`

**Import note if you are using the trackLink method**

`trackEvents` makes an underlying call to trackLinkURL, where linkURL is set to null, linkType is set to "o", and the linkName is populated with the application ID. This is done to prevent the page view (state view) count from being incremented each time you track events.

If you are calling trackLinkURL directly and setting values for linkTrackVars and linkTrackEvents, these variable and event restrictions apply to TrackEvents. This means that only variables and events defined on these lists are sent with TrackEvents. You should set linkTrackVars and linkTrackEvents to null unless you want those restrictions applied to trackEvents.

**trackEventsWithContextData**: This is the recommended way to track events in your application. trackEvents is similar to trackAppState, but sends events instead of page names. Events are provided as a comma delimited string. The events string must be provided for each call since it isn't carried over to the next call.

This method make an underlying call to trackLinkURL where linkURL is set to null, linkType is set to "o", and the linkName is populated with the application ID.  

This means that your linkTrackVars and linkTrackEvents apply for calls to trackEvents.

Context data sent with this call is appended to any values in persistentContextData and sent with the call. Only values set in persistentContextData remain for the next call.

Syntax:

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData: JSON object with key-value pairs to send in context data.

Example:

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**Import note if you are using the trackLink method**

trackEvents makes an underlying call to trackLinkURL, where linkURL is set to null, linkType is set to "o", and the linkName is populated with the application ID. This is done to prevent the page view (state view) count from being incremented each time you track events.

If you are calling trackLinkURL directly and setting values for linkTrackVars and linkTrackEvents, these variable and event restrictions apply to TrackEvents. This means that only variables and events defined on these lists are sent with TrackEvents. You should set linkTrackVars and linkTrackEvents to null unless you want those restrictions applied to trackEvents.

**Advanced Tracking Methods (track and trackLink)**

These methods provide additional tracking options, allowing you to populate props, eVars, and other SiteCatalyst variables directly. These should be used by customers with an existing implementation or customers who are very familiar with other SiteCatalyst implementations.

`track` and `trackLink` are the core measurement methods that are implemented in all versions of the Adobe Measurement Libraries across multiple platforms. In most circumstances when tracking mobile applications, it is easier to use trackAppState, trackEvents methods rather than calling track and trackLink directly.

Page view tracking (track) and link tracking (trackLink) sends all persistent variables that have values (non-null, non-empty, non-zero). You should reset or empty all variables, as needed, before calling track or trackLink.

**Methods**

**track**: Sends a standard page view, along with any additional variables that are set on the measurement object, to the collection server.

Syntax:

`void track();`

Example:

`ADMS.track();`

**trackWithContextData**: Sends a standard page view, along with any additional variables that are set on the measurement object, to the collection server.

Each call to trackWithContextData sends all persistent data defined on the measurement object (these are listed in the description for clearVars), plus any contextData you provide for that call only.

Syntax:

`void trackWithContextData(JSON cData);`

cData: JSON object with key-value pairs to send in context data.

Example:

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**: Sends a standard page view, along with any additional variables that are set on the measurement object, to the collection server.

Each call to trackWithContextDataAndVariables sends all persistent data defined on the measurement object (these are listed in the description for clearVars), plus any contextData and variables you provide for that call only. If you send a variable that is defined, any value in the corresponding persistent variable is overwritten.

Syntax:

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData: JSON object with key-value pairs to send in context data.

Example:

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**: Sends custom, download or exit link data to Adobe data collection servers, along with any track config variables that have values.

Use trackLink to track all activity that should not capture a page view.

Each call to trackLinkURLWithLinkTypeNameContextDataVariables sends all persistent data defined on the measurement object (these are listed in the description for clearVars), plus any contextData you provide for that call only.

Syntax:

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData: JSON object with key-value pairs to send in context data.

Example:

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### Set and Get AppMeasurement Variables

**Methods**

**setEvarToValue**: Sets the specified eVar to the provided value. The eVar is sent with the next tracking call.

Syntax:

`void setEvarToValue(int evar, string value);`

Example:

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**: Sets the specified prop to the provided value. The prop is sent with next tracking call.

Syntax:

void setPropToValue(int prop, string value);

Example:

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**: Sets the specified hier variable to the provided value. The variable is sent with next tracking call.

Syntax:

`void setHierToValue(int hier, string value);`

Example:

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**: Sets the specified listvar to the provided value. The listvar is sent with next tracking call.

Syntax:

`void setListVarToValue(int list, string value);`

Example:

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**: Gets the specified variable.

Syntax:

`void getEvar(int evar, function success, function fail);`

Example:

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**: Gets the specified variable.

Syntax:

`void getProp(int prop, function success, function fail);`

Example:

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**: Gets the specified variable.

Syntax:

`void getHier(int hier, function success, function fail);`

Example:

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**: Gets the specified variable.

Syntax:

`void getListVar(int list, function success, function fail);`

Example:

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**: Removes values from the following variables on the object:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Syntax:

`void clearVars();`

Example:

`ADMS.clearVars();`

**trackingQueueSize**: Gets or sets the number of stored tracking calls in the offline queue.

Syntax:

`void trackingQueueSize(function success, function fail);`

Example:

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**: Removes all stored tracking calls from the offline queue. Warning: use caution when clearing the queue manually as it cannot be reversed.

Syntax:

`void clearTrackingQueue();`

Example:

`ADMS.clearTrackingQueue();`

### Set and Get Configuration Variables

**Methods**

**getVersion**: Gets the library version.

Syntax:

`void getVersion(function success, function fail);`

Example:

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**: (Required) The report suite or report suites (multi-suite tagging) that you wish to track. To track to multiple report suites, pass a comma delimited list of the names of each report suite.

You cannot override this variable for a single call, you must change the persistent value.

Syntax:
`void setReportSuiteIDs(string reportSuiteIDs);`

Example:

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**: (Required) Identifies the collection server.

This variable should be populated with the value generated for you in Code Manager.

The same value is used for secure tracking if ssl is enabled.

You cannot override this variable for a single call, you must change the persistent value.

Syntax:

`void setTrackingServer(string trackingServer);`

Example:

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

Syntax:

`void setDataCenter(string dataCenter);`

Example:

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**: Default is CFUUID.

Unique identifier for each visitor. If you do not set a custom visitorID, a unique visitorID is generated (using Apple's CFUUID) on initial launch and then stored in a user defaults key. This key is used by AppMeasurement and PhoneGap from that point forward. This key is also saved and restored during the standard application backup process.

Syntax:

`void setVisitorID(string visitorId);`

Example:

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**: Default is UTF-8.

Syntax:

`void setCharSet(string charSet);`

Example:

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**: Default is none (value defined for report suite is used).

The Currency Code used for purchases or currency events that are tracked in the iOS application.

Syntax:

`void setCurrencyCode(string currencyCode);`

Example:

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**: Defaultis false.

Enables (true) or disables (false) sending measurement data via SSL (HTTPS). You cannot override this variable for a single call, you must change the persistent value.

Syntax:

`void setSSLEnabled(bool sslEnabled);`

Example:

`ADMS.setSSLEnabled(false);`

### Set and Get Persistent Tracking Variables

**Methods**

**setPurchaseID**:

Syntax:

`void setPurchaseID(string purchaseId);`

Example:

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

Syntax:

`void setTransactionID(string transactionId);`

Example:

`ADMS.setTransactionID("transaction1");`

**setAppState**:

Syntax:

`void setAppState(string stateName);`

Example:

`ADMS.setAppState("myAppState");`

**setChannel**:

Syntax:

`void setChannel(string channel);`

Example:

`ADMS.setChannel("myChannel");`

**setAppSection**:

Syntax:

`void setAppSection(string appSection);`

Example:

`DMS.setAppSection("myAppSection");`

**setCampaign**:

Syntax:

`void setCampaign(string campaign);`

Example:

`ADMS.setCampaign("myCampaign");`

**setProducts**:

Syntax:

`void setProducts(string products);`

Example:

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

Syntax:

`void setEvents(string events);`

Example:

`ADMS.setEvents("event1, event2");`

**setGeoState**

Syntax:

`void setGeoState(string state);`

Example:

`ADMS.setGeoState("FL");`

**setGeoZip**:

Syntax:

`void setGeoZip(string zip);`

Example:

`ADMS.setGeoZip("39984");`

**setPersistentContextData**: Context data is the recommended way to collect data. To send context data, create a JSON object and assign key value pairs for the values you want to send.

Syntax:

`void setPersistentContextData(JSON cData);`

Example:

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

Syntax:

`void persistentContextData(function success, function fail);`

Example:

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**: A comma delimited list of variable names that restricts the current set of variables for link tracking.

If linkTrackVars is not defined, the PhoneGap plug-in sends all defined variables with a trackLink call.

Syntax:

`void setLinkTrackVars(string linkTrackVars);`

Example:

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**: A comma delimited list of events that restricts the current set of events for link tracking. If linkTrackEvents is not defined, the PhoneGap plug-in sends all events with a trackLink call.

Syntax:

`void setLinkTrackEvents(string linkTrackEvents);`

Example:

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**: A comma delimited list of variables that restricts the current set of variables for light tracking calls. This variables you send with a light server call are configured by ClientCare.

Syntax:

`void setLightTrackVars(string lightTrackVars);`

Example:

`ADMS.setLightTrackVars("prop1,hier3");`

### Offline Tracking

**Methods**

**setOfflineTrackingEnabled**:

Syntax:

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

Example:

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

Syntax:

`void setOfflineHitLimit(int offlineHitLimit);`

Example:

`ADMS.setOfflineHitLimit(3000);`

## Android Version 2.x to 3.x Migration Guide

* AppMeasurement is now ADMS_Measurement. Find locations where you reference this class and update the name to ADMS_Measurement.
* getInstance is now sharedInstance. Find locations where you call getInstance and replace it with sharedInstance.
* Remove all calls to churn measurement (getChurnInstance). These calls are handled by auto tracking and the variables are now inserted using context data.
* Timestamp is removed. The library handles timestamps automatically.

The syntax for the following methods have changed. Updated examples for all properties and methods are available in Configuration Variables and Methods.


### Report Suite

**Previous Version (2.1.x)** 

`account`

**New Version (3.x)**

`reportSuiteIDs`

### Track

**Previous Version (2.1.x)** 


`String track()`

`String track(Hashtable variableOverrides)`

**New Version (3.x)**

Pass null for unused values.

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### Track Link

**Previous Version (2.1.x)** 

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**New Version (3.x)**

These two calls have been replaced with a single call. Pass null for unused values.

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### Offline Tracking Methods

**Previous Version (2.1.x)** 

`void forceOffline();`


`void forceOnline();`
 
 **New Version (3.x)**

`void setOnline();`

`void setOffline();`


### Renamed Variables

The following list shows version 2.x variables with their corresponding values in version 3.x. Several variables were removed from version 3.x to make the library more mobile focused and to simplify implementation.


*Note: The 3.x version uses getters and setters instead of public variables. You'll need to update locations in your code where you set variables directly to use the get and set methods.*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## Using Bloodhound to Test Mobile Applications

The Bloodhound Tool lets you send server calls to a local computer to test mobile applications. 

*Important: As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided.*

During application development, Bloodhound lets you view server calls locally, and optionally forward the data to Adobe collection servers.

Bloodhound is available for Mac and Windows.

### Requirements

* An Intel-based Mac computer running Snow Leopard (10.6) or later, or a Windows PC.
* Network connectivity to your mobile devices or simulators.

### Download

See Bloodhound - App Measurement QA Tool on Developer Connection.

### Installation

* Mac: Open the dmg you downloaded and drag Bloodhound to the Applications folder.
* Windows: Run the installation file you downloaded.

### Using Bloodhound

After you start the tool, the server is disabled until you click the Start button. Click the Start button when you are ready to capture server calls from your application.

Optionally, you can specify a custom port number (must be above 1024) before you start the server. If you do not provide a port number, the server automatically selects an open port.

After the server is running, you need to configure your applications or devices to send data to the tool, as discussed in the next section.

### Configure Devices to Send Hits to Bloodhound

You can changing proxy settings on the device to send http requests to the tool. Requests that are sent to the tool can optionally be forwarded to Adobe Data Collection servers.

If your device does not support a proxy, you can send the hits directly to bloodhound for testing.

*Note: Bloodhound does not support SSL tracking. You must disable SSL in the AppMeasurement library when testing using Bloodhound.*

#### iOS Devices

The iOS Device must be on the same network as the computer hosting Bloodhound.

1. Navigate to Settings > Wi-Fi.
2. Click the blue arrow to the right of your current Wi-Fi network.
3. Scroll to the HTTP Proxy settings.
4. Select Auto.
5. Enter the Proxy URL and port (from the Bloodhound UI) into the URL field.

#### Other Devices

If the device supports proxy auto config, simply use the Proxy URL (From the Bloodhound UI) as the Proxy Auto Config (PAC) URL. Proxy support varies across Android versions, and there are some proxy configuration tools available for Android to simplify configuration.

### Send Hits Directly

For devices that do not support proxy (iOS Simulator, older Android versions, etc) it is possible to specify Bloodhound as your tracking server in order to capture the hits it generates. To do this set your tracking server to "<Bloodhound IP>:<BloodhoundPort>".

For example:

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### Troubleshooting/Common Issues

* Bloodhound only functions with non-ssl tracking. Any tracking hits sent via SSL are not captured, regardless of the method used above.

## Android Widgets

Android widgets can be tracked using the same methods as your app. Widgets share the application context with your app, so hit order and visitor identification is preserved.

The following guidelines will help you track Android widgets:

* Do not implement lifecycle metrics (startActivity/stopActivity) calls in the widget itself.
* To track when a widget is added to the home screen, add a trackState or trackEvent call to the onEnabled method of the widget.
* To track when the app is launched from a widget, add a trackState or trackEvent call before you create the intent to launch your application.
* If you are interested in tracking the context of an action, you can define a ContextData variable that provides the option of segmenting each out separately (for example, AppExperienceType="widget" vs. "app").
