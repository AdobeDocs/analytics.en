---
title: getLoadTime
description: Gets the page load time, allowing you to store that value in a variable.
---

# getLoadTime

The `getLoadTime` plug-in gets the page load time in tenths of a second. This plug-in is valuable to see how your page load time performs across your site. It operates outside of the `s` tracking object to increase load time accuracy.

> [!TIP] This plug-in outputs an integer value representing tenths of a second. If you would like to convert this value to seconds, create a calculated metric dividing this value by 10.

## Install the getLoadTime plug-in using Adobe Experience Platform Launch

You can install the `getLoadTime()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `getLoadTime()` function in the custom code editor of rules to assign variable values.

## Install the getLoadTime plug-in using AppMeasurement

You can install the `getLoadTime()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere you'd like.

Once installed, you can use the `getLoadTime()` function to assign variable values.

## Plug-in code

```js
function getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

## Use the getLoadTime plug-in with AppMeasurement and Launch custom code editor

The `getLoadTime()` function runs on page load and returns an integer representing tenths of a second. Use this function to assign variable values. It does not take any arguments.

```js
// Assign eVar1 to the number of tenths of seconds the page took to load
s.eVar1 = getLoadTime();

// Assign an event to accumulate page load time in reporting. You can then create a calculated metric in Analysis Workspace to determine average page load time for each page.
s.events = "event1=" + getLoadTime();

// Use the apl plug-in to append this event to the events variable.
// You can add this code to the doPlugins function for an easy and low-maintenance method to record load time in a custom event.
if(getLoadTime()) s.events = s.apl(s.events,"event1" + getLoadTime(),',',1);
```
