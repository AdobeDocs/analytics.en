---
title: getGeoCoordinates
description: Track a visitor's geoLocation.
---

# Adobe plug-in: getGeoCoordinates

## Plugin Purpose

### What does this plug-in do?

The getGeoCoordinates plug-in allows you to capture the geolocation (latitude and longitude) of visitors' devices.

### Why should I use this plug-in?

You should use the getGeoCoordinates plug-in if you want to capture the geolocation (latitude and longitude) of visitors' devices.

### Why shouldn't I use this plug-in?

You won't need to use the getGeoCoordinates plug-in if you don't want to capture the geolocation (latitude and longitude) of visitors' devices.

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getGeoCoordinates plug-in

## How to Deploy

You may use one of the following three methods to deploy the getGeoCoordinates plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

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
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 (Requires AppMeasurement) */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

When calling the getGeoCoordinates plug-in (via JavaScript), you will not need to pass in any arguments.

## Returns

The getGeoCoordinates plug-in returns one of the following values
* "geo coordinates not available" for devices that do not have geoCoordinates available at the time that the plug-in runs.  This will usually be the case on the first hit of the visit – especially when visitors first need to provide consent on tracking their location – but should not be the case afterwards.
* "error retrieving geo coordinates" if the plug-in encounters any errors when trying to retrieve the device's geocoordinates
* "latitude=[LATITUDE] | longtitude=[LONGITUDE]" where [LATITUDE]/[LONGITUDE] are the latitude and longitude, respectively
**NOTE:** the coordinate values are rounded to the closest fourth decimal (e.g. the value of "40.438635333" would be returned as "40.4386") to limit the number of unique values to be captured.  The values should be close enough to pinpoint the device's exact location within around 20 feet.

## Cookies

The getGeoCoordinates plug-in uses the "s_ggc" first-party cookie to store the coordinates (to be passed over from hit to hit, if necessary)

## Example Calls

### Example #1
The following code...

```js
s.eVar1 = s.getGeoCoordinates();
```
...sets eVar1 equal to one of the above return values depending on the visitor's device status

### Example #2
The following code extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
	var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
	finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```
From there, you can determine whether a visitor is at, for example, the Statue of Liberty:

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
	var visitorAtStatueOfLiberty = true;
else
	var visitorAtStatueOfLiberty = false;
```

## Version History

### 1.0 (May 25, 2015)

* Initial release.
