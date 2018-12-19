---
description: Cumulative release notes for Flash. Flash apps using ActionScript can be measured on the desktop and on the web.
seo-description: Cumulative release notes for Flash. Flash apps using ActionScript can be measured on the desktop and on the web.
seo-title: Flash-Flex
solution: Analytics
subtopic: Release notes
title: Flash-Flex
topic: Developer and implementation
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
index: y
internal: n
snippet: y
---

# Flash-Flex{#flash-flex}

Cumulative release notes for Flash. Flash apps using ActionScript can be measured on the desktop and on the web.

>[!NOTE]
>
>To find the current library version, turn on debug logging.

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## April 20, 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**Version 4.0.3 **

* Inclusion of Visitor API 1.6.1.

## August 18, 2016 {#section_D72EF20672174249B864997905D7552A}

** 4.0.2 - Update**

Inclusion of Visitor API 1.6.0.

## May 19, 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

** 4.0.1 - Update**

Inclusion of Visitor API 1.5.6

## April 21, 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

Adobe has released a [security update APSB16-13](https://helpx.adobe.com/security/products/analytics/apsb16-13.html) for the [!DNL AppMeasurement] for Flash library. This update resolves an important vulnerability in the library, applicable only when `debugTracking` is enabled, that could be abused to conduct [DOM-based XSS attacks](https://www.owasp.org/index.php/DOM_Based_XSS).

>[!IMPORTANT]
>
>This issue affects [!DNL AppMeasurement] for Flash only when `debugTracking` has been enabled ( `debugTracking` is disabled in the default configuration). **If affected, we strongly advise you to disable `debugTracking` immediately.** Here is some sample code:

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled” behavior 

```

Affected versions are [!DNL AppMeasurement] for Flash version 4.0 and earlier on all platforms.

>[!NOTE]
>
>Due to security reasons, we will no longer be distributing an AS2 version of [!DNL AppMeasurement] for Flash. We will continue to support data collection from existing AS2-based projects. However, we highly recommend that customers upgrade their implementations to AS3 and incorporate the latest security features of [!DNL AppMeasurement] for Flash.

[!DNL AppMeasurement] for Flash customers affected by this issue must rebuild projects with the updated library available for download from the [!DNL Analytics] Console [More…](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

Version 4.0 - Update:

* Inclusion of Visitor API 1.5.3.

## September 17, 2015 {#section_319911C0F080452981F8C8BEA2880463}

Version 4.0 - Update:

* Inclusion of Visitor API 1.5.2.

## August 20, 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

Version 4.0 - Update:

* Inclusion of Visitor API 1.5.1.

## June 18, 2015 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

Version 4.0 - Update

* Inclusion of Visitor API 1.5. 
* Use Visitor API 1.5+ getCustomerIDs method to gather Customer IDs and Authenticated State, and send them in with data collection requests (AN-102131)

## May 21, 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

Version 3.9.2 - Update:

* Inclusion of Visitor API 1.4

## February 19, 2015 {#section_95ADF1725CE7415D956944A28182E69B}

Version 3.9.2:

* Inclusion of Visitor API 1.3.5. 
* Changed to not perform automatic referrer tracking after first tracking call, so the 2nd, 3rd, etc., tracking call (usually link tracking) will not double count the referrer when *`s.referrer`* was manually set before the first tracking call. (AN-92647) 
* Removal of deprecated [!UICONTROL Heartbeat] video tracking embedded in the Media module. The supported [!UICONTROL Heartbeat] video tracking has been moved to a separate Video [!DNL Analytics] library.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

Version 3.9.1:

* Added cookie support testing to Flash (k = Y/N query-string variable) and pf=1 to query-string when cookie support test is possible (browser with [!DNL JavaScript] access). 
* Support for new features in visitor ID service 1.3.2.

## August 21, 2014 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

Version 3.9:

* Added latitude and longitude variables. 
* Support for new features in visitor ID service 1.3.1.

## Version 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

Release Date: **June 19, 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors. 
* Support for new features in visitor ID service 1.3.

## Version 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

Release Date: **April 17, 2014**

* Support for the [Marketing Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Version 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

Release Date: **March 13, 2014**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Version 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

Release Date: **February 6, 2014**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Version 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

Release Date: **November 14, 2013**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Version 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

Release Date: **October 17, 2013**

* Support for [heartbeat video tracking](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/). 
* VisitorAPI.swc was included to support [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#). 
* Dropped support for Flash player 9 with ActionScript 3. The minimum Flash Player version for ActionScript 3 is 10.

## Version 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

Release Date: **September 18, 2013**

* Internal changes to support an upcoming beta release.

## Version 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

Release Date: **August 15, 2013**

* Disabled re-queuing of failed requests when offline tracking is disabled.

## Version 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

Release Date: **February 21, 2013**

* Fixed an issue with URL encoding/decoding in ActionScript 2.

## Version 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

Release Date: **January 31, 2013**

* Added support to send URLs longer than 255 bytes to support the expansion of the Page URL field in Adobe Data Collection servers. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. This helps prevent long URLs from taking precedence over other data in the case of browser truncation, but still enables capturing of long URLs. 

* Added a new fallback visitor identification method. See [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors). 
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

## Version 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

Release Date: **November 8, 2012**

* Internal updates for [!DNL Audience Manager] integration.

## Version 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

Release Date: **October 22, 2012**

* Changed ActionScript 3 builds to ignore any setting of `s.charSet` because we always use UTF-8

## Version 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Release Date: **September 13, 2012** 
**Important change to variable binding**: In version 3.5, an option to disable variable binding was added for customers who need to start and end literal string values with curly braces. Variable binding using curly braces is used primarily when configuring OSMF video players using XML tags: 

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

A new attribute, called `autoBind`, is available to override the default behavior in XML tags:

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

Setting `autoBind` to `false` causes the value to be considered a literal string and variable binding is not used. When this attribute is not set to `false` the behavior in XML tags remains the same.

**Impact on ActionScript Code**

Though not commonly used, this syntax is also available to bind [!DNL AppMeasurement] variables in your ActionScript code. If you are unsure whether or not you are using variable binding, search your code for [!DNL AppMeasurement] variable values that start and end with curly braces. For example:

```
s.eVar1 = "{source}";
```

If you are using variable binding, you should change this code to use the new `bindVariable` method:

```
s.bindVariable("eVar1","source");
```

Optionally, instead of changing each location, you can revert to the pre-version 3.5 behavior by setting `autoBindVariablesByValue` to true:

```
s.autoBindVariablesByValue = true;
```

**Additional Fixes:**

* Fixed an issue that might cause the video complete event to not be sent when using a custom `media.monitor` method that tracks the media close event: 

  ```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
  ```

## Version 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

Release Date: **July 19, 2012**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## Version 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

Release Date: **June 21, 2012**

* Changed to always use UTF-8 in AS3 builds. This prevents issues with strings for some multibyte languages.

## Version 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

Release Date: **April 26, 2012**

Video measurement: Added handling of inconsistent complete offset reported by Brightcove player API. Now if the offset is reported as zero, on complete we use the length as the offset. This fixes issues with the new method of tracking completes using an offset value.

## Version 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

Release Date: **January 19, 2012**

* Updated video tracking with a new method to track complete video views.

## Version 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

Release Date: **September 8, 2011**

* Enabled props to contain a literal zero value "0". Previously props with a literal zero value were not sent.

## Version 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

Release Date: **May 2011**

* In OSMF, fixed issues when using proxy plugins when tracking OSMF video players. This fix enabled OSMF ProxyElements to be tracked when the element they are proxying is not being tracked. 
* Fixed an issue that caused an error measuring video on Flash Player 9.0.16.

