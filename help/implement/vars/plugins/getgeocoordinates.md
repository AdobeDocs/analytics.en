---
title: getGeoCoordinates
description: Track a Visitor's geoLocation
---

# Adobe Plugin: getGeoCoordinates

## Plugin Purpose

### What does this plugin do?

The getGeoCoordinates plugin allows you to capture the geolocation (latitude and longitude) of visitors' devices.

### Why should I use this plugin?

You should use the getGeoCoordinates plugin if you want to capture the geolocation (latitude and longitude) of visitors' devices.

### Why shouldn't I use this plugin?

You won't need to use the getGeoCoordinates plugin if you don't want to capture the geolocation (latitude and longitude) of visitors' devices.

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the getGeoCoordinates plugin

## How to Deploy

You may use one of the following three methods to deploy the getGeoCoordinates plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file

Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 (Requires AppMeasurement) */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
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
	* Action Type: Initialize getGeoCoordinates
* Save and publish the changes to the rule

## How to Run the Plugin

When calling the getGeoCoordinates plugin (via JavaScript), you will not need to pass in any arguments.

## Returns

The getGeoCoordinates plugin returns one of the following values
* "geo coordinates not available" for devices that do not have geoCoordinates available at the time that the plugin runs.  This will usually be the case on the first hit of the visit – especially when visitors first need to provide consent on tracking their location – but should not be the case afterwards.
* "error retrieving geo coordinates" if the plugin encounters any errors when trying to retrieve the device's geocoordinates
* "latitude=[LATITUDE] | longtitude=[LONGITUDE]" where [LATITUDE]/[LONGITUDE] are the latitude and longitude, respectively
**NOTE:** the coordinate values are rounded to the closest fourth decimal (e.g. the value of "40.438635333" would be returned as "40.4386") to limit the number of unique values to be captured.  The values should be close enough to pinpoint the device's exact location within around 20 feet.

## Cookies

The getGeoCoordinates plugin uses the "s_ggc" first-party cookie to store the coordinates (to be passed over from hit to hit, if necessary)

## Example Calls

### Example #1
The following code...
```javascript
s.eVar1 = s.getGeoCoordinates();
```
...sets eVar1 equal to one of the above return values depending on the visitor's device status

### Example #2
The following code extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications
```javascript
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
	var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
	finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```
From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
```javascript
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
	var visitorAtStatueOfLiberty = true;
else
	var visitorAtStatueOfLiberty = false;
```

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...
```javascript
s.getGeoCoordinates=function(){
```
...to this:
```javascript
[objectname].getGeoCoordinates=function(){
```

## Version History

### 1.0 (2015-05-25)

* First release