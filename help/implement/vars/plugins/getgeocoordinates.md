---
title: getGeoCoordinates
description: Track a visitor's geoLocation.
feature: Variables
exl-id: 8620d083-7fa6-432b-891c-e24907e7c466
---
# Adobe plug-in: getGeoCoordinates

{{plug-in}}

The `getGeoCoordinates` plug-in allows you to capture the latitude and longitude of visitors' devices. Adobe recommends using this plug-in if you want to capture geo-location data in Analytics variables.

## Install the plug-in using the Web SDK extension

Adobe offers an extension that allows you to use most commonly-used plug-ins with the Web SDK.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click **[!UICONTROL Tags]** on the left, then click the desired tag property.
1. Click **[!UICONTROL Extensions]** on the left, then click the **[!UICONTROL Catalog]** tab
1. Locate and install the **[!UICONTROL Common Web SDK Plugins]** extension.
1. Click **[!UICONTROL Data Elements]** on the left, then click the desired data element.
1. Set the desired data element name with the following configuration:
    * Extension: Common Web SDK Plugins
    * Data Element: `getGeoCoordinates`
1. Save and publish the changes to the data element.

## Install the plug-in manually implementing the Web SDK

This plug-in is not yet supported for use within a manual implementation of the Web SDK.

## Install the plug-in using the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins with Adobe Analytics.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getGeoCoordinates
1. Save and publish the changes to the rule.

## Install the plug-in using custom code editor

If you do not want to use the Common Analytics Plugins plug-in extension, you can use the custom code editor.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v2.0  */
function getGeoCoordinates(){if(arguments&&"-v"===arguments[0])return{plugin:"getGeoCoordinates",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getGeoCoordinates="2.0");window.cookieWrite=window.cookieWrite||function(a,c,f){if("string"===typeof a){var h=window.location.hostname,b=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){b=2<b?b:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<b;)e=h.lastIndexOf(".",e-1),b--;e=0<e?h.substring(e):h}}g=e;c="undefined"!==typeof c?""+c:"";if(f||""===c)if(""===c&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(c)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===c:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var c=" "+document.cookie,b=c.indexOf(" "+a+"="),d=0>b?b:c.indexOf(";",b);return(a=0>b?"":decodeURIComponent(c.substring(b+2+a.length,0>d?c.length:d)))?a:""};var d="";b=cookieRead("s_ggc").split("|");var k={timeout:5E3,maximumAge:0},l=function(a){a=a.coords;cookieWrite("s_ggc",parseFloat(a.latitude.toFixed(4))+"|"+parseFloat(a.longitude.toFixed(4)),30);d="latitude="+parseFloat(a.latitude.toFixed(4))+" | longitude="+parseFloat(a.longitude.toFixed(4))},m=function(a){d="error retrieving geo coordinates"};1<b.length&&(d="latitude="+b[0]+" | longitude="+b[1]);navigator.geolocation&&navigator.geolocation.getCurrentPosition(l,m,k);""===d&&(d="geo coordinates not available");return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getGeoCoordinates` function does not use any arguments. It returns one of the following values:

* `"geo coordinates not available"`: For devices that do not have geo-location data available at the time that the plug-in runs. This value is common on the first hit of the visit, especially when visitors first need to provide consent on tracking their location.
* `"error retrieving geo coordinates"`: When the plug-in encounters any errors when attempting to retrieve the device's location
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Where [LATITUDE]/[LONGITUDE] are the latitude and longitude, respectively

>[!NOTE]
>
>Coordinate values are rounded to the closest fourth decimal. For example, the value of `"40.438635333"` is rounded to `"40.4386"` to limit the number of unique values to be captured. The values are close enough to pinpoint the device's exact location within around 20 feet.

This plug-in uses a cookie named `"s_ggc"` to store coordinates between hits if necessary.

## Examples

```js
// Sets eVar1 to one of the above return values depending on the visitor's device status.
s.eVar1 = getGeoCoordinates();

// Extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications.
var coordinates = getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}

// From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongitude >= -74.0446 && finalLongitude <= -74.0444)
{
  var visitorAtStatueOfLiberty = true;
}
else
{
  var visitorAtStatueOfLiberty = false;
}
```

## Version History

### 2.0 (March 19, 2021)

* Added version number as context data.

### 1.0 (May 25, 2015)

* Initial release.
