---
title: Tracking opt-out reason
description: Previews what data would be excluded if you enabled Privacy Settings.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
---
# Tracking opt-out reason

The 'Tracking opt-out reason' dimension acts as a preview to data that would be excluded if you enabled Privacy Settings. This dimension is primarily used to determine if your implementation would be negatively impacted if you enabled [Privacy Settings](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) under Report Suite Settings.

Typical implementations see 1% or less of their overall report suite traffic under this dimension if Privacy Settings have not yet been enabled. Percentages higher than 1% of all traffic suggests a potential implementation problem that prevents AppMeasurement from setting first-party cookies.

## Populate this dimension with data

This dimension works out of the box for all implementations that have not yet enabled [Privacy Settings](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). If your organization has already enabled the **[!UICONTROL Remove users who have blocked all cookies]** setting for both desktop and mobile browsers, this dimension does not contain data.

## Dimension items

Dimension items include `"Cookies disabled by Desktop Browser"` and `"Cookies disabled by Mobile Browser"`.

* **Cookies disabled by Desktop Browser**: The visitor blocked cookies using a desktop browser, and **[!UICONTROL Remove users who have blocked all cookies on desktop browsers]** is disabled.
* **Cookies disabled by Mobile Browser**: The visitor blocked cookies using a mobile browser, and **[!UICONTROL Remove users who have blocked all cookies on mobile browsers]** is disabled.
