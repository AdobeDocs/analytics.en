---
description: null
seo-description: null
seo-title: Mac OS X
solution: Analytics,Experience Cloud
subtopic: Release notes
title: Mac OS X
topic: Developer and implementation
uuid: d5e46c86-2d00-4a18-8eee-dcaf082761af
---

# Mac OS X{#mac-os-x}

>[!IMPORTANT]
>
>These SDKs have been sunset and are no longer supported or distributed by Adobe.

> [!NOTE] To find the current library version, turn on debug logging.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

## Version 3.2.2 {#section_90CCB6A33C5041FA9CBAF6E8B7F3915F}

Release Date: **30 January, 2014**

* Resolved issue that could cause large session length averages if a device had incorrect time settings.

## Version 3.2.1 {#section_0354BDA5B77242058740CE7B6AEF2FEE}

Release Date: **16 August, 2013**

* Optimized by removing unused code.
* Fixed potential crash that could occur when clearVars was used in a threaded scenario.

## Version 3.2 {#section_B85E2904C769461BA8B062AAA0534F9B}

Release Date: **5 Aug, 2013**

* Added support for Adobe Audience Manager.
* Lifecycle data will now be sent with [!DNL Target] Mbox requests.

## Version 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

Release Date: **23 May, 2013**

* Added code to prevent excessive lifecycle hits from being sent via location notifications and Newsstand notifications that launch an app.

## Version 3.1.6 {#section_DAEB9DDF3A1242CEBF21F4E5AF742D68}

Release Date: **18 April, 2013**

* Fixed an issue that was causing previous session length to sometimes be calculated incorrectly.

## Version 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

Release Date: **21 March, 2013**

* `ADMS_Measurement.visitorID` now gets pre-populated with the default value.

## Version 3.1.4 {#section_23E5968C1EC748F7A266D6A5682A1B5F}

Release Date: **February 2013**

Initial release. This version is based on the [!DNL iOS] 3.1.4 codebase, so the initial version number was set to match [!DNL iOS].
