---
description: null
solution: Analytics,Experience Cloud
subtopic: Release notes
title: WinRT for Windows 8
topic: Developer and implementation
uuid: cec19d63-114c-4ef6-a55e-db6aad4e948b
---

# WinRT for Windows 8{#winrt-for-windows}

>[!NOTE]
>
>To find the current library version, turn on debug logging.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL WinRT] for [!DNL Windows] 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK. No further development will occur on this SDK.

## Version 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Release Date: **June 17, 2014**

New version with new features including geo-location, lifetime value, timed actions, and opt-in support.

## Version 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Release Date: **May 22, 2014**

Bug fixes and performance improvements.

## Version 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Release Date: **October 17, 2013**

* [!DNL Windows] 8.1 compatibility

## Version 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Release Date: **April 18, 2013**

* Fixed an issue that was causing previous session length to sometimes be calculated incorrectly.

## Version 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Release Date: **March 21, 2013**

* `ADMS_Measurement.visitorID` now gets pre-populated with the default value.
* Fixed an issue with retrieving device info.

## Version 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Release Date: **February 21, 2013**

* Deprecated `offlineThrottleDelay` as the setting is no longer necessary due to thread optimization. The setting still exists to preserve backwards compatibility, but no longer has any effect.
* `DayOfWeek` is now 1-based starting on Sunday to match the values collected on other platforms.
* Added auto-subscribing to event listeners in the TrackingHelper.js to streamline lifecycle tracking.

## Version 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Release Date: **November 2012**

* Screen resolution is now accurately being collected for C#, C++, and HTML5/WinJS platforms.
* `ADMS_Churn` class is now internal. To use best practices for application lifecycle tracking, use the following calls:

  ```
  public void ADMS_Measurement.StartSession(); 
  public void ADMS_Measurement.StopSession();
  ```

* Added `public double maxSessionLength` variable to `ADMS_Measurement` to allow you to set a maximum session length for the previous user session. If the registered session length exceeds the max, your max session length will be sent. Default `maxSessionLength` is 3600 (seconds).
* Added a `lifecycleSessionTimeout` configuration variable that lets you specify the length of time, in seconds, that must elapse between app launches before the launch is considered a new session.
* Added new Previous Session Length metric to the lifecycle metrics.
* Updated TrackingHelper for clarity.
* Fixed media module bug.

## Version 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**October 2012**

Initial release.
