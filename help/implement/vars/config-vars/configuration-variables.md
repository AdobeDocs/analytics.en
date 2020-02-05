---
title: Configuration variables
description: Use configuration variables to help determine how data is collected.
---

# Configuration variables overview

Configuration variables control the way data is captured and processed in reporting. They do not typically contain dimension or metric values.

## Setting configuration variables

In JavaScript implementations using `AppMeasurement.js`, configuration variables are typically set at the top of the JS file.

In implementations using Adobe Experience Platform Launch, configuration variables are typically found by configuring the Adobe Analytics extension:

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Click on the property that you want to edit.
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] Make sure all configuration variables are set before calling a track function (`t()` or `tl()`). Avoid setting configuration variables in the `doPlugins()` function.
