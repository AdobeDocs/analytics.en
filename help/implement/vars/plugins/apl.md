---
title: apl
description: Append values to variables that support multiple values.
---

# apl

The `apl` plug-in, also known as the `appendList` plug-in, adds values to an existing delimited string. This plug-in is valuable for Analytics variables that can hold multiple values in the same hit:

* You can add events to the `events` variable
* You can add values to a list variable without duplicating a value in the list
* You can add a product to the `products` variable based on page logic
* You can add values to the `linkTrackVars` or `linkTrackEvents` variables for use in link tracking

This plug-in has an option to check for existing values. It helps prevent duplicate values when inserting a value in the string.

## Install the apl plug-in using Adobe Experience Platform Launch

You can install the `s.apl()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `s.apl()` function in the custom code editor of rules to assign variable values.

## Install the apl plug-in using AppMeasurement

You can install the `s.apl()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere after the tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)).
3. Save the JS file and upload the new version to your web server.

Once installed, you can use the `s.apl()` function to assign variable values.

## Plug-in code

> [!NOTE] This plug-in requires that you also install the [`split`](split.md) plug-in.
