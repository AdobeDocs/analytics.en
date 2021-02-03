---
title: websiteBot
description: Dynamically identify desktop visitors that are not bots.
---

# Adobe plug-in: websiteBot

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `websiteBot` plug-in allows you to dynamically identify if desktop visitors are bots. You can use this data to drive greater accuracy in all types of reporting, which gives you a better way to measure legitimate site traffic.

This plug-in performs two checks:

* First, it determines whether the device is a desktop or mobile device using the `navigator.UserAgent` variable. Mobile devices are ignored.
* If it is a desktop device, it adds an event listener for mouse movement.

If the user agent is on a desktop and no mouse movement is detected, the plug-in sets the `websiteBot` variable to `true`. If the user agent is a mobile device, or if mouse movement is detected, the plug-in sets the `websiteBot` variable to `false`.

## Prerequisites

Adobe recommends the following before using this plug-in:

* **Configure eVar settings**: Set up an eVar under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings. Set the expiration to **"Visitor"** and allocation to **"Original Value (First)"**.
* **Collect user agent in a separate variable**: Collect the user agent string in a separate variable to monitor the efficacy of this plug-in. Set an eVar to `navigator.UserAgent` on every hit to collect this data.

## Install the plug-in using Launch custom code editor

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: websiteBot BETA v0.1 */

/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `websiteBot` variable is a boolean. It returns `true` if the plug-in detects a bot; otherwise it returns `false`.

## Example

```js
// Set eVar1 to detect bots. Dimension items in reporting are "true" or "false"
s.eVar1 = websiteBot;

// Use a ternary operator to set eVar values
s.eVar1 = websiteBot ? "Bot detected" : "Not a bot";
```

## Version History

### 0.1 (January 19, 2021)

* Beta release.
