---
description: null
subtopic: Release notes
title: Windows Silverlight, NET, IIS, XBOX
topic: Developer and implementation
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
---

# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>These SDKs have been sunset and are no longer supported or distributed by Adobe.

> [!NOTE] To find the current library version, turn on debug logging.

## Version 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Release Date: **August 2014**

* Removed support for the [!DNL Microsoft Silverlight Analytics Framework]. Adobe is no longer supporting or distributing the [!DNL Microsoft Silverlight Analytics Framework] integration for [!DNL AppMeasurement].

* Internal changes to support upcoming functionality.

## Version 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Release Date: **March 2013**

* Fixed exception with getting default referrer in [!DNL Silverlight] outside of a browser context and properly exposed SSL property in the [!DNL Microsoft Silverlight Analytics Framework] component.

## Version 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Release Date: **February 2013**

* Added support to send URLs longer than 255 bytes to support the expansion of the Page URL field in Adobe Data Collection servers. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. This helps prevent long URLs from taking precedence over other data in the case of browser truncation, but still enables capturing of long URLs.

* Added a new fallback visitor identification method. See [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Added a new `abort` flag that can be set inside `doPlugins`. Setting this flag to true causes the [!DNL AppMeasurement] library to not continue with that tracking call. The abort flag is reset with every tracking call, so if a subsequent tracking call also needs to be aborted the flag will need to be set again inside `doPlugins`.

  ```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
  ```

  This lets you centralize the logic you use to identify activity that you do not want to track, such as some custom links or external links in display ads.

## Version 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

Release Date: **September 2012**

* Fixed an issue that might cause the video complete event to not be sent when using a custom `media.monitor` method that tracks the media close event: 

  ```
  If(media.event=="CLOSE") { 
  … 
  } 
  
  ```

## Version 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

Release Date: **April 2012**

* Added support for [!DNL XBOX].

## Version 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

Release Date: **February 2012**

* [!DNL iOS] Phone 7: Fixed an issue that caused the offlineThrottleDelay to not apply correctly.
* Added time stamp to variables used with light tracking calls (trackLight).

## Version 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

Release Date: **January 2012**

* Updated video tracking with a new method to track complete video views. See [Measuring Video in Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html).

## Version 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* New support and build for [!DNL iOS] Phone platform including offline tracking.
* Support for doRequest delegate to override how requests are sent out for tracking data.
* Support for contextData that drives server-side processing rules (v15 only).
* Support for light server calls (currently in beta).
* Support for assigning a value other than 1 to a counter event in the events list.
* Support for new method of tracking video using conversion eVars and events (currently in beta).

