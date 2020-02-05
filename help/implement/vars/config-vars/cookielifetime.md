---
title: cookieLifetime
description: Override the expiration for cookies that AppMeasurement creates.
---

# cookieLifetime

Cookies set by AppMeasurement typically have an expiration of 2 years. Use the `cookieLifetime` variable to override the expiration date for cookies set by AppMeasurement.

> [!NOTE] This variable impacts unique visitor counts and attribution. Use caution when setting this variable.

## Cookie Lifetime in Adobe Experience Platform Launch

Cookie Lifetime is a dropdown under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Cookie Lifetime] dropdown.

This dropdown contains the following values:

* **Default**: Cookie expires after 2 years.
* **None**: AppMeasurement does not set cookies.
* **Session**: Cookie expires at the end of the visitor's session.
* **Seconds**: Cookie expires after the specified number of seconds have elapsed. For example, setting this dropdown to [!UICONTROL Seconds] and placing `86400` into the custom field forces cookies to expire after exactly 24 hours.

## s.cookieLifetime in AppMeasurement and Launch custom code editor

The `s.cookieLifetime` variable is a string that determines the expiration date of cookies set by AppMeasurement.

* If set to `SESSION`, cookies set by AppMeasurement expire after the browser session completes.
* If set to `NONE`, AppMeasurement does not attempt to set cookies.
* If set to an integer string, cookies set by AppMeasurement expire after the specified number of seconds have elapsed.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
