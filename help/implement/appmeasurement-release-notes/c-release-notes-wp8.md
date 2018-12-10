---
description: null
seo-description: null
seo-title: Windows Phone 8
solution: Analytics,Marketing Cloud
subtopic: Release notes
title: Windows Phone 8
topic: Developer and implementation
uuid: 7378969a-d219-42bf-9750-141acc9e4b7d
index: y
internal: n
snippet: y
---

# Windows Phone 8{#windows-phone}

>[!NOTE]
>
>To find the current library version, turn on debug logging.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL Windows] Phone 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK. No further development will occur on this SDK.

## Version 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

Release Date: **August 21, 2013**

* Context Data keys now allow underscores.

## Version 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

Release Date: **May 22, 2013**

* Bug fixes and performance improvements.

## Version 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

Release Date: **April 18, 2013**

* Fixed an issue that was causing previous session length to sometimes be calculated incorrectly.

## Version 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

Release Date: **March 21, 2013**

* Fixed a localization issue with `DateTime` objects.

## Version 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

Release Date: **February 26, 2013**

* `ADMS_Measurement.visitorID` now gets pre-populated with the default value. 
* Fixed an issue that was sometimes causing auto-responses from cache.

## Version 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

Release Date: **February 21, 2013**

* Deprecated `offlineThrottleDelay` as the setting is no longer necessary due to thread optimization. The setting still exists to preserve backwards compatibility, but no longer has any effect. 
* `DayOfWeek` is now 1-based starting on Sunday to match the values collected on other platforms. 
* Fixed an issue with offline storage that was sometimes causing the app to crash.

