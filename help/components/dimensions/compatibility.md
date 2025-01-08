---
title: Analytics Dimensions Compatibility
description: Reference for Analytics dimensions and reports.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
---
# Analytics Dimensions Compatibility

This page lists [dimensions](overview.md) supported in their respective Analytics capabilities.

>[!NOTE]
>
>Custom variable names, classifications, and visitor attributes are omitted from this list. These dimension items are specific to individual report suites.

## Dimensions supported in Analysis Workspace

|Dimension Name (visible in Analytics UI)|Dimension ID (used in API requests)|
|---|---|
|Analytics for Target|`targetraw`|
|Audiences ID|`mcaudiences`|
|[Browser](browser.md)|`browser`|
|[Browser Type](browser-type.md)|`browsertype`|
|[Category](category.md)|`category`|
|[Cities](cities.md)|`geocity`|
|[Color Depth](color-depth.md)|`colordepth`|
|[Connection Type](connection-type.md)|`connectiontype`|
|[Cookie Support](cookie-support.md)|`cookie`|
|[Countries](countries.md)|`geocountry`|
|[Customer Loyalty](customer-loyalty.md)|`customerloyalty`|
|[Custom Conversion Vars](evar.md)|`evar1`, `evar2`, etc.|
|[Custom Insight Vars](prop.md)|`prop1`, `prop2`, etc.|
|[Custom Link](custom-link.md)|`customlink`|
|[Days Before First Purchase](days-before-first-purchase.md)|`daysbeforefirstpurchase`|
|[Days Since Last Purchase](days-since-last-purchase.md)|`dayssincelastpurchase`|
|[Domain](domain.md)|`filtereddomain`|
|[Download Link](download-link.md)|`downloadlink`|
|[Entry Page](entry-dimensions.md)|`entrypage`|
|[Entry Page Original](entry-dimensions.md)|`entrypageoriginal`|
|[Exit Link](exit-link.md)|`exitlink`|
|[First Touch Channel](first-touch-channel.md)|`firsttouchchannel`|
|[First Touch Channel Detail](first-touch-detail.md)|`firsttouchchanneldetail`|
|[Java enabled](java-enabled.md)|`javaenabled`|
|[Language](language.md)|`language`|
|[Last Touch Channel](last-touch-channel.md)|`lasttouchchannel`|
|[Last Touch Channel Detail](last-touch-detail.md)|`lasttouchchanneldetail`|
|List Variables|`listvariables`|
|[Marketing Channel](marketing-channel.md)|`marketingchannel`|
|[Mobile Audio Support](mobile-dimensions.md)|`mobileaudiosupport`|
|[Mobile Carrier](mobile-dimensions.md)|`mobilecarrier`|
|[Mobile Color Depth](mobile-dimensions.md)|`mobilecolordepth`|
|[Mobile Cookie Support](mobile-dimensions.md)|`mobilecookiesupport`|
|[Mobile Device](mobile-dimensions.md)|`mobiledevicename`|
|[Mobile Device Type](mobile-dimensions.md)|`mobiledevicetype`|
|[Mobile Max Email Length](mobile-dimensions.md)|`mobileemaillength`|
|[Mobile Image Support](mobile-dimensions.md)|`mobileimagesupport`|
|[Mobile Manufacturer](mobile-dimensions.md)|`mobilemanufacturer`|
|[Mobile Operating System (deprecated)](mobile-dimensions.md)|`mobileos`|
|[Mobile Screen Height](mobile-dimensions.md)|`mobilescreenheight`|
|[Mobile Screen Size](mobile-dimensions.md)|`mobilescreensize`|
|[Mobile Screen Width](mobile-dimensions.md)|`mobilescreenwidth`|
|[Mobile Max Browser URL Length](mobile-dimensions.md)|`mobileurllength`|
|[Mobile Video Support](mobile-dimensions.md)|`mobilevideosupport`|
|[Monitor Resolution](monitor-resolution.md)|`monitorresolution`|
|[Operating Systems](operating-systems.md)|`operatingsystem`|
|[Original Referring Domain](original-referring-domain.md)|`referringdomainoriginal`|
|[Page](page.md)|`page`|
|[Pages Not Found](pages-not-found.md)|`pagesnotfound`|
|[Product](product.md)|`product`|
|[Referrer](referrer.md)|`referrer`|
|[Referrer Type](referrer-type.md)|`referrertype`|
|[Referring Domain](referring-domain.md)|`referringdomain`|
|[Regions](regions.md)|`georegion`|
|[Return Frequency](return-frequency.md)|`returnfrequency`|
|SC-TnT|`tntbase`|
|[Search Engine](search-engine.md)|`searchengine`|
|[Search Keyword](search-keyword.md)|`searchenginekeyword`|
|[Search Engine - Natural](search-engine.md)|`searchenginenatural`|
|[Search Engine - Paid](search-engine.md)|`searchenginepaid`|
|[Search Keyword - Natural](search-keyword.md)|`searchenginenaturalkeyword`|
|[Search Keyword - Paid](search-keyword.md)|`searchenginepaidkeyword`|
|[All Search Page Rank](all-search-page-rank.md)|`searchenginepagerank`|
|[Server](server.md)|`server`|
|[Single Page Visits](single-page-visits.md)|`singlepagevisits`|
|[Site Section](site-section.md)|`sitesections`|
|[Time Spent per Visit - Granular](time-spent-per-visit.md)|`sitetime`|
|[Tracking Code](tracking-code.md)|`campaign`|
|[US DMA](us-dma.md)|`geodma`|
|[US States](us-states.md)|`state`|
|[Time Prior to Event](time-prior-to-event.md)|`timeprior`|
|[Time Spent per Visit - Bucketed](time-spent-per-visit.md)|`timespent`|
|[Visit Depth](visit-depth.md)|`pathlength`|
|[Visit Number](visit-number.md)|`visitnumber`|
|[Zip Code](zip-code.md)|`zip`|
|[AM / PM](am-pm.md)|`timepartampm`|
|[Browser Height - Bucketed](browser-height.md)|`browserheightbucketed`|
|[Browser Width - Bucketed](browser-width.md)|`browserwidthbucketed`|
|[Day](day.md)|`daterangeday`|
|[Day of Month](day-of-month.md)|`timepartdayofmonth`|
|[Day of Week](day-of-week.md)|`dayofweek`|
|[Day of Week](day-of-week.md)|`timepartdayofweek`|
|[Day of Year](day-of-year.md)|`timepartdayofyear`|
|[Days Since Last Visit](days-since-last-visit.md)|`dayssincelastvisit`|
|[Entry Custom Insights](entry-dimensions.md)|`entryprops`|
|[Entry List Variables](entry-dimensions.md)|`entrylistvariables`|
|[Entry Server](entry-dimensions.md)|`entryserver`|
|[Entry Site Section](entry-dimensions.md)|`entrysitesections`|
|[Exit Custom Insights](exit-dimensions.md)|`exitprops`|
|[Exit List Variables](exit-dimensions.md)|`exitlistvariables`|
|[Exit Page](exit-dimensions.md)|`exitpage`|
|[Exit Server](exit-dimensions.md)|`exitserver`|
|[Exit Site Section](exit-dimensions.md)|`exitsitesections`|
|[Hit Depth](hit-depth.md)|`hitdepth`|
|[Hit Type](hit-type.md)|`hittype`|
|[Hour](hour.md)|`daterangehour`|
|[Hour of Day](hour-of-day.md)|`timeparthourofday`|
|[Marketing Channel Detail](marketing-detail.md)|`marketingchanneldetail`|
|[Minute](minute.md)|`daterangeminute`|
|[Mobile Max Bookmark Length](mobile-dimensions.md)|`mobilebookmarklength`|
|[Mobile Device Number](mobile-dimensions.md)|`mobiledevicenumber`|
|[Mobile DRM](mobile-dimensions.md)|`mobiledrm`|
|[Mobile Information Services](mobile-dimensions.md)|`mobileinformationservices`|
|[Mobile Java VM](mobile-dimensions.md)|`mobilejavavm`|
|[Mobile Mail Decoration](mobile-dimensions.md)|`mobilemaildecoration`|
|[Mobile Net Protocols](mobile-dimensions.md)|`mobilenetprotocols`|
|[Mobile Push To Talk](mobile-dimensions.md)|`mobilepushtotalk`|
|[Month](month.md)|`daterangemonth`|
|[Month of Year](month-of-year.md)|`timepartmonthofyear`|
|[Operating System Types](operating-system-types.md)|`operatingsystemgroup`|
|[Paid Search](paid-search.md)|`paidsearch`|
|[Persistent Cookie Support](persistent-cookie-support.md)|`persistentcookie`|
|[Quarter](quarter.md)|`daterangequarter`|
|[Quarter of Year](quarter-of-year.md)|`timepartquarterofyear`|
|Survey|`surveybase`|
|[Time Spent on Page - Bucketed](time-spent-on-page.md)|`averagepagetime`|
|[Time Spent on Page - Granular](time-spent-on-page.md)|`pagetimeseconds`|
|[Tracking Opt-out Reason](tracking-opt-out-reason.md)|`optoutreason`|
|[Weekday / Weekend](weekday-weekend.md)|`timepartweekdayweekend`|
|[Week](week.md)|`daterangeweek`|
|[Year](year.md)|`daterangeyear`|

## Content-aware dimensions supported only in Analysis Workspace

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Activity Map XY|`clickmapxy`|
|Media Session ID|`videosessionid`|
|Nielsen Access Method|`nielsenaccmethod`|
|Nielsen App ID|`nielsenappid`|
|Nielsen Channel Asset|`nielsenchannelasset`|
|Nielsen Content Type|`nielsencontenttype`|

## Content-aware dimensions supported by Analysis Workspace

### Video (the Streaming Media Collection)

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|[Content](sm-core.md)|`video`|
|[Content Segment](sm-core.md)|`videosegment`|
|[Content Type](sm-core.md)|`videocontenttype`|
|[Ad Player Name](sm-ads.md)|`videoadplayername`|
|[Ad in Pod Position](sm-ads.md)|`videoadinpod`|
|[Dropped Frames](sm-quality.md)|`videoqoedroppedframecountevar`|
|[Errors](sm-quality.md)|`videoqoeerrorcountevar`|
|[Average Bitrate](sm-quality.md)|`videoqoebitrateaverageevar`|
|[Bitrate Changes](sm-quality.md)|`videoqoebitratechangecountevar`|
|[Total Buffer Duration](sm-quality.md)|`videoqoebuffertimeevar`|
|[Buffer Events](sm-quality.md)|`videoqoebuffercountevar`|
|[Time to Start](sm-quality.md)|`videoqoetimetostartevar`|
|[Ad Pod](sm-ads.md)|`videoadpod`|
|[Media Path](sm-core.md)|`videopath`|
|[Ad](sm-ads.md)|`videoad`|
|[Content Player Name](sm-core.md)|`videoplayername`|
|[Content Channel](sm-core.md)|`videochannel`|
|[Chapter](sm-chapters.md)|`videochapter`|
|[Content Name (variable)](sm-core.md)|`videoname`|
|[Content Length (variable)](sm-core.md)|`videolength`|
|[Ad Name (variable)](sm-ads.md)|`videoadname`|
|[Ad Length (variable)](sm-ads.md)|`videoadlength`|
|[Show](sm-video-metadata.md)|`videoshow`|
|[Season](sm-video-metadata.md)|`videoseason`|
|[Episode](sm-video-metadata.md)|`videoepisode`|
|[Network](sm-video-metadata.md)|`videonetwork`|
|[Show Type](sm-video-metadata.md)|`videoshowtype`|
|[Ad Loads](sm-ads.md)|`videoadload`|
|[MVPD](sm-video-metadata.md)|`videomvpd`|
|[Day Part](sm-video-metadata.md)|`videodaypart`|
|[Advertiser](sm-ads.md)|`videoadadvertiser`|
|[Campaign ID](sm-ads.md)|`videoadcampaign`|
|[Genre](sm-video-metadata.md)|`videogenre`|
|[Stream Type](sm-core.md)|`videostreamtype`|
|[Player SDK Error IDs](sm-quality.md)|`videoqoeplayersdkerrors`|
|[External Error IDs](sm-quality.md)|`videoqoeextneralerrors`|
|[Media Feed Type](sm-video-metadata.md)|`videofeedtype`|
|[Entry Media Path](entry-dimensions.md)|`entryvideopath`|
|[Exit Media Path](exit-dimensions.md)|`exitvideopath`|
|[Entry Genre](entry-dimensions.md)|`entryvideogenre`|
|[Exit Genre](exit-dimensions.md)|`exitvideogenre`|
|[Entry Player SDK Error IDs](entry-dimensions.md)|`entryvideoqoeplayersdkerrors`|
|[Exit Player SDK Error IDs](exit-dimensions.md)|`exitvideoqoeplayersdkerrors`|
|[Entry External Error IDs](entry-dimensions.md)|`entryvideoqoeextneralerrors`|
|[Exit External Error IDs](exit-dimensions.md)|`exitvideoqoeextneralerrors`|

### Adobe Social

Adobe Social is retired.

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Terms|`socialterm`|
|Social Platforms / Properties|`socialcontentprovider`|
|Authors|`socialauthor`|
|Language|`sociallanguage`|
|Latitude / Longitude|`sociallatlong`|
|Asset Tracking Codes|`socialassettrackingcode`|
|Owned Social Properties|`socialaccountandappids`|
|Owned Post IDs|`socialownedpostids`|
|Owned Social Definitions|`socialinteractiontype`|
|Owned Property IDs|`socialownedpropertyid`|
|Owned Property vs Application|`socialownedpropertypropertyvsapp`|
|Owned Property Name|`socialownedpropertyname`|
|Owned Definition Property vs Post|`socialowneddefinitionpropertyvspost`|
|Owned Definition Insight Type|`socialowneddefinitioninsighttype`|
|Owned Definition Insight Value|`socialowneddefinitioninsightvalue`|
|Owned Definition Metric|`socialowneddefinitionmetric`|
|Asset|`socialmediaid`|

### Mobile SDK

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|[First Launch Date](lifecycle-dimensions.md)|`mobileinstalldate`|
|[App Id](lifecycle-dimensions.md)|`mobileappid`|
|[Launch Number](lifecycle-dimensions.md)|`mobilelaunchnumber`|
|[Days Since First Use](lifecycle-dimensions.md)|`mobiledayssincefirstuse`|
|[Days Since Last Use](lifecycle-dimensions.md)|`mobiledayssincelastuse`|
|[Hour of Day (SDK)](lifecycle-dimensions.md)|`mobilehourofday`|
|[Day of Week (SDK)](lifecycle-dimensions.md)|`mobiledayofweek`|
|[Operating System (SDK)](lifecycle-dimensions.md)|`mobileosenvironment`|
|[Days Since Last Upgrade](lifecycle-dimensions.md)|`mobiledayssincelastupgrade`|
|[Launches Since Last Upgrade](lifecycle-dimensions.md)|`mobilelaunchessincelastupgrade`|
|[Device Name (SDK)](lifecycle-dimensions.md)|`mobiledevice`|
|[Operating System Version (SDK)](lifecycle-dimensions.md)|`mobileosversion`|
|[Beacon Major](lifecycle-dimensions.md)|`mobilebeaconmajor`|
|[Beacon Minor](lifecycle-dimensions.md)|`mobilebeaconminor`|
|[Beacon UUID](lifecycle-dimensions.md)|`mobilebeaconuuid`|
|[Beacon Proximity](lifecycle-dimensions.md)|`mobilebeaconproximity`|
|[Location (down to 10 km)](lifecycle-dimensions.md)|`latlon1`|
|[Location (down to 100 m)](lifecycle-dimensions.md)|`latlon23`|
|[Location (down to 1 m)](lifecycle-dimensions.md)|`latlon45`|
|[Point of Interest Name](lifecycle-dimensions.md)|`pointofinterest`|
|[Distance to Point of Interest Center](lifecycle-dimensions.md)|`pointofinterestdistance`|
|[Location Accuracy](lifecycle-dimensions.md)|`mobileplaceaccuracy`|
|[Place Category](lifecycle-dimensions.md)|`mobileplacecategory`|
|[Place ID](lifecycle-dimensions.md)|`mobileplaceid`|
|[Entry Beacon Major](lifecycle-dimensions.md)|`entrymobilebeaconmajor`|
|[Exit Beacon Major](lifecycle-dimensions.md)|`exitmobilebeaconmajor`|
|[Entry Beacon Minor](lifecycle-dimensions.md)|`entrymobilebeaconminor`|
|[Exit Beacon Minor](lifecycle-dimensions.md)|`exitmobilebeaconminor`|
|[Entry Beacon UUID](lifecycle-dimensions.md)|`entrymobilebeaconuuid`|
|[Exit Beacon UUID](lifecycle-dimensions.md)|`exitmobilebeaconuuid`|
|[Entry Beacon Proximity](lifecycle-dimensions.md)|`entrymobilebeaconproximity`|
|[Exit Beacon Proximity](lifecycle-dimensions.md)|`exitmobilebeaconproximity`|

### Adobe Advertising Cloud (AMO)

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|AMO EF ID|`amo_ef_id`|
|AMO ID|`amo_cid`|

### Activity Map

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|[Activity Map Link By Region](activity-map-link-by-region.md)|`clickmaplinkbyregion`|
|[Activity Map Region](activity-map-region.md)|`clickmapregion`|
|[Activity Map Link](activity-map-link.md)|`clickmaplink`|
|[Activity Map Page](activity-map-page.md)|`clickmappage`|

### Nielsen Integration

For more information on how to implement this integration, see the [Nielsen Extension](https://exchange.adobe.com/apps/ec/101361) on the Adobe Exchange.

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Nielsen Ad Model|`nielsenadmodel`|
|Nielsen Segment C|`nielsensegmentc`|
|Nielsen Segment B|`nielsensegmentb`|
|Nielsen Segment A|`nielsensegmenta`|
|Nielsen Content ID|`nielsencontentid`|
|Nielsen Asset / Program|`nielsenasset`|
|Nielsen VCID|`nielsenvcid`|
|Nielsen Opt Out|`nielsenoptout`|
|Nielsen Client ID + VCID|`nielsenclientidvcid`|
|Nielsen Client ID|`nielsenclientid`|
|Entry Nielsen Opt Out|`entrynielsenoptout`|
|Exit Nielsen Opt Out|`exitnielsenoptout`|
|Entry Nielsen Client ID + VCID|`entrynielsenclientidvcid`|
|Exit Nielsen Client ID + VCID|`exitnielsenclientidvcid`|
|Entry Nielsen Client ID|`entrynielsenclientid`|
|Exit Nielsen Client ID|`exitnielsenclientid`|

### Adobe Experience Manager (AEM)

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Asset ID|`aemassetid`|
|Asset Source|`aemassetsource`|
|Clicked Asset ID|`aemclickedassetid`|
|Entry Asset ID|`entryaemassetid`|
|Exit Asset ID|`exitaemassetid`|

### Adobe Campaign

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Adobe Campaign Executed Delivery ID|`ac_delivery_internal_name`|
