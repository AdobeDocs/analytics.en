---
title: Analytics Dimensions Compatibility
description: Reference for Analytics dimensions and reports.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
---
# Analytics Dimensions Compatibility

This page lists dimensions supported in their respective Analytics capabilities.

>[!NOTE]
>
>Custom variable names, classifications, and visitor attributes are omitted from this list. These dimension items are specific to individual report suites.

>[!NOTE]
>
>There are some overlaps where Analytics tools use different terms for similar dimensions. For example, Reports & Analytics uses `browserwidth` while Analysis Workspace uses `browserwidthbucketed`.

## Dimensions supported in both Reports & Analytics and Analysis Workspace

|Dimension Name (visible in Analytics UI)|Dimension ID (used in API requests)|
|---|---|
|Analytics for Target|`targetraw`|
|Audiences ID|`mcaudiences`|
|Browser|`browser`|
|Browser Type|`browsertype`|
|Category|`category`|
|Cities|`geocity`|
|Color Depth|`colordepth`|
|Connection Type|`connectiontype`|
|Cookie Support|`cookie`|
|Countries|`geocountry`|
|Customer Loyalty|`customerloyalty`|
|Custom Conversion Vars|`evar1`, `evar2`, etc.|
|Custom Insight Vars|`prop1`, `prop2`, etc.|
|Custom Link|`customlink`|
|Days Before First Purchase|`daysbeforefirstpurchase`|
|Days Since Last Purchase|`dayssincelastpurchase`|
|Domain|`filtereddomain`|
|Download Link|`downloadlink`|
|Entry Page|`entrypage`|
|Entry Page Original|`entrypageoriginal`|
|Exit Link|`exitlink`|
|First Touch Channel|`firsttouchchannel`|
|First Touch Channel Detail|`firsttouchchanneldetail`|
|Java enabled|`javaenabled`|
|Language|`language`|
|Last Touch Channel|`lasttouchchannel`|
|Last Touch Channel Detail|`lasttouchchanneldetail`|
|List Variables|`listvariables`|
|Marketing Channel|`marketingchannel`|
|Mobile Audio Support|`mobileaudiosupport`|
|Mobile Carrier|`mobilecarrier`|
|Mobile Color Depth|`mobilecolordepth`|
|Mobile Cookie Support|`mobilecookiesupport`|
|Mobile Device|`mobiledevicename`|
|Mobile Device Type|`mobiledevicetype`|
|Mobile Max Email Length|`mobileemaillength`|
|Mobile Image Support|`mobileimagesupport`|
|Mobile Manufacturer|`mobilemanufacturer`|
|Mobile Operating System (deprecated)|`mobileos`|
|Mobile Screen Height|`mobilescreenheight`|
|Mobile Screen Size|`mobilescreensize`|
|Mobile Screen Width|`mobilescreenwidth`|
|Mobile Max Browser URL Length|`mobileurllength`|
|Mobile Video Support|`mobilevideosupport`|
|Monitor Resolution|`monitorresolution`|
|Operating Systems|`operatingsystem`|
|Original Referring Domain|`referringdomainoriginal`|
|Page|`page`|
|Pages Not Found|`pagesnotfound`|
|Product|`product`|
|Referrer|`referrer`|
|Referrer Type|`referrertype`|
|Referring Domain|`referringdomain`|
|Regions|`georegion`|
|Return Frequency|`returnfrequency`|
|SC-TnT|`tntbase`|
|Search Engine|`searchengine`|
|Search Keyword|`searchenginekeyword`|
|Search Engine - Natural|`searchenginenatural`|
|Search Engine - Paid|`searchenginepaid`|
|Search Keyword - Natural|`searchenginenaturalkeyword`|
|Search Keyword - Paid|`searchenginepaidkeyword`|
|All Search Page Rank|`searchenginepagerank`|
|Server|`server`|
|Single Page Visits|`singlepagevisits`|
|Site Section|`sitesections`|
|Time Spent per Visit - Granular|`sitetime`|
|Tracking Code|`campaign`|
|US DMA|`geodma`|
|US States|`state`|
|Time Prior to Event|`timeprior`|
|Time Spent per Visit - Bucketed|`timespent`|
|Visit Depth|`pathlength`|
|Visit Number|`visitnumber`|
|Zip Code|`zip`|

## Dimensions supported only in Analysis Workspace

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|AM/PM|`timepartampm`|
|Browser Height - Bucketed|`browserheightbucketed`|
|Browser Width - Bucketed|`browserwidthbucketed`|
|Day|`daterangeday`|
|Day of Month|`timepartdayofmonth`|
|Day of Week|`dayofweek`|
|Day of Week|`timepartdayofweek`|
|Day of Year|`timepartdayofyear`|
|Days Since Last Visit|`dayssincelastvisit`|
|Entry Custom Insights|`entryprops`|
|Entry List Variables|`entrylistvariables`|
|Entry Server|`entryserver`|
|Entry Site Section|`entrysitesections`|
|Exit Custom Insights|`exitprops`|
|Exit List Variables|`exitlistvariables`|
|Exit Page|`exitpage`|
|Exit Server|`exitserver`|
|Exit Site Section|`exitsitesections`|
|Hit Depth|`hitdepth`|
|Hit Type|`hittype`|
|Hour|`daterangehour`|
|Hour of Day|`timeparthourofday`|
|Marketing Channel Detail|`marketingchanneldetail`|
|Minute|`daterangeminute`|
|Mobile Max Bookmark Length|`mobilebookmarklength`|
|Mobile Device Number|`mobiledevicenumber`|
|Mobile DRM|`mobiledrm`|
|Mobile Information Services|`mobileinformationservices`|
|Mobile Java VM|`mobilejavavm`|
|Mobile Mail Decoration|`mobilemaildecoration`|
|Mobile Net Protocols|`mobilenetprotocols`|
|Mobile Push To Talk|`mobilepushtotalk`|
|Month|`daterangemonth`|
|Month of Year|`timepartmonthofyear`|
|Operating System Types|`operatingsystemgroup`|
|Paid Search|`paidsearch`|
|Persistent Cookie Support|`persistentcookie`|
|Quarter|`daterangequarter`|
|Quarter of Year|`timepartquarterofyear`|
|Survey|`surveybase`|
|Time Spent on Page - Bucketed|`averagepagetime`|
|Time Spent on Page - Granular|`pagetimeseconds`|
|Tracking Opt-out Reason|`optoutreason`|
|Weekday/Weekend|`timepartweekdayweekend`|
|Week|`daterangeweek`|
|Year|`daterangeyear`|

## Content-aware dimensions supported only in Analysis Workspace

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Activity Map XY|`clickmapxy`|
|Media Session ID|`videosessionid`|
|Nielsen Access Method|`nielsenaccmethod`|
|Nielsen App ID|`nielsenappid`|
|Nielsen Channel Asset|`nielsenchannelasset`|
|Nielsen Content Type|`nielsencontenttype`|

## Dimensions supported only in Reports & Analytics

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Browser Height|`browserheight`|
|Browser Width|`browserwidth`|
|Daily Unique Customers|`dailyuniquecustomers`|
|JavaScript|`javascriptsupport`|
|JavaScript Version|`javascriptversion`|
|Monthly Unique Customers|`monthlyuniquecustomers`|
|Quarterly Unique Customers|`quarterlyuniquecustomers`|
|Time Zones|`timezone`|
|Top Level Domains|`topleveldomain`|
|Visitor State|`legacystate`|
|Weekly Unique Customers|`weeklyuniquecustomers`|
|Yearly Unique Customers|`yearlyuniquecustomers`|

## Content-aware dimensions supported by both Reports & Analytics and Analysis Workspace

### Video (Media Analytics)

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Content|`video`|
|Content Segment|`videosegment`|
|Content Type|`videocontenttype`|
|Ad Player Name|`videoadplayername`|
|Ad in Pod Position|`videoadinpod`|
|Dropped Frames|`videoqoedroppedframecountevar`|
|Errors|`videoqoeerrorcountevar`|
|Average Bitrate|`videoqoebitrateaverageevar`|
|Bitrate Changes|`videoqoebitratechangecountevar`|
|Total Buffer Duration|`videoqoebuffertimeevar`|
|Buffer Events|`videoqoebuffercountevar`|
|Time to Start|`videoqoetimetostartevar`|
|Ad Pod|`videoadpod`|
|Media Path|`videopath`|
|Ad|`videoad`|
|Content Player Name|`videoplayername`|
|Content Channel|`videochannel`|
|Chapter|`videochapter`|
|Content Name (variable)|`videoname`|
|Content Length (variable)|`videolength`|
|Ad Name (variable)|`videoadname`|
|Ad Length (variable)|`videoadlength`|
|Show|`videoshow`|
|Season|`videoseason`|
|Episode|`videoepisode`|
|Network|`videonetwork`|
|Show Type|`videoshowtype`|
|Ad Loads|`videoadload`|
|MVPD|`videomvpd`|
|Day Part|`videodaypart`|
|Advertiser|`videoadadvertiser`|
|Campaign ID|`videoadcampaign`|
|Genre|`videogenre`|
|Stream Type|`videostreamtype`|
|Player SDK Error IDs|`videoqoeplayersdkerrors`|
|External Error IDs|`videoqoeextneralerrors`|
|Media Feed Type|`videofeedtype`|
|Entry Media Path|`entryvideopath`|
|Exit Media Path|`exitvideopath`|
|Entry Genre|`entryvideogenre`|
|Exit Genre|`exitvideogenre`|
|Entry Player SDK Error IDs|`entryvideoqoeplayersdkerrors`|
|Exit Player SDK Error IDs|`exitvideoqoeplayersdkerrors`|
|Entry External Error IDs|`entryvideoqoeextneralerrors`|
|Exit External Error IDs|`exitvideoqoeextneralerrors`|

### Adobe Social

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
|First Launch Date|`mobileinstalldate`|
|App Id|`mobileappid`|
|Launch Number|`mobilelaunchnumber`|
|Days Since First Use|`mobiledayssincefirstuse`|
|Days Since Last Use|`mobiledayssincelastuse`|
|Hour of Day (SDK)|`mobilehourofday`|
|Day of Week (SDK)|`mobiledayofweek`|
|Operating System (SDK)|`mobileosenvironment`|
|Days Since Last Upgrade|`mobiledayssincelastupgrade`|
|Launches Since Last Upgrade|`mobilelaunchessincelastupgrade`|
|Device Name (SDK)|`mobiledevice`|
|Operating System Version (SDK)|`mobileosversion`|
|Beacon Major|`mobilebeaconmajor`|
|Beacon Minor|`mobilebeaconminor`|
|Beacon UUID|`mobilebeaconuuid`|
|Beacon Proximity|`mobilebeaconproximity`|
|Location (down to 10 km)|`latlon1`|
|Location (down to 100 m)|`latlon23`|
|Location (down to 1 m)|`latlon45`|
|Point of Interest Name|`pointofinterest`|
|Distance to Point of Interest Center|`pointofinterestdistance`|
|Location Accuracy|`mobileplaceaccuracy`|
|Place Category|`mobileplacecategory`|
|Place ID|`mobileplaceid`|
|Entry Beacon Major|`entrymobilebeaconmajor`|
|Exit Beacon Major|`exitmobilebeaconmajor`|
|Entry Beacon Minor|`entrymobilebeaconminor`|
|Exit Beacon Minor|`exitmobilebeaconminor`|
|Entry Beacon UUID|`entrymobilebeaconuuid`|
|Exit Beacon UUID|`exitmobilebeaconuuid`|
|Entry Beacon Proximity|`entrymobilebeaconproximity`|
|Exit Beacon Proximity|`exitmobilebeaconproximity`|

### Adobe Advertising Cloud (AMO)

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|AMO EF ID|`amo_ef_id`|
|AMO ID|`amo_cid`|

### Activity Map

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Activity Map Link By Region|`clickmaplinkbyregion`|
|Activity Map Region|`clickmapregion`|
|Activity Map Link|`clickmaplink`|
|Activity Map Page|`clickmappage`|

### Nielsen Integration

For more information on how to implement this integration, see the [Nielsen Extension](https://exchange.adobe.com/experiencecloud.details.101361.html).

|Dimension name (visible in Analytics UI)|Dimension ID (used in API requests)|
|--- |--- |
|Nielsen Ad Model|`nielsenadmodel`|
|Nielsen Segment C|`nielsensegmentc`|
|Nielsen Segment B|`nielsensegmentb`|
|Nielsen Segment A|`nielsensegmenta`|
|Nielsen Content ID|`nielsencontentid`|
|Nielsen Asset/Program|`nielsenasset`|
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
