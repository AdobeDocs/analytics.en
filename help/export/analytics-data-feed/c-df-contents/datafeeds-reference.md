---
description: Table data describing the columns in the data feed.
keywords: Data Feed;columns
subtopic: data feeds
title: Data column reference
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
---
# Data column reference

Use this page to learn what data is contained in each column. Most implementations don't use every column, so this page can be referenced when determining which columns to include in a data feed export.

>[!IMPORTANT]
>
>For any given column (for instance, one that is defined as 255 characters), a data feed can send additional characters due to the addition of characters escaping values in a string. Keep these potential extra characters in mind if your implementation regularly sends values that exceed character limits.

## Columns, Descriptions, and Data Types

>[!NOTE]
>
>Most columns contain a similar column with a prefix of `post_`. Post columns contain values after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases. See [Data feeds FAQ](../df-faq.md) for more information.

Previous updates to this table can be found on this page's [commit history on GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |
| **`aemassetsource`** | Identifies the source of the asset event. Used in Adobe Experience Manager.| varchar(255) |
| **`aemclickedassetid`** | Asset ID of an Adobe Experience Manager asset. Increments Click Events.| varchar(255) |
| **`browser`** | A numeric ID that represents the browser. References the `browser.tsv` lookup table. | int unsigned |
| **`browser_height`** | The [Browser Height](/help/components/dimensions/browser-height.md) dimension. | smallint unsigned |
| **`browser_width`** | The [Browser Width](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`c_color`** | Bit depth of the color palette. Used as part of calculating the [Color depth](/help/components/dimensions/color-depth.md) dimension. AppMeasurement uses the JavaScript function `screen.colorDepth()`. | char(20) |
| **`campaign`** | The [Tracking Code](/help/components/dimensions/tracking-code.md) dimension.| varchar(255) |
| **`carrier`** | Adobe Advertising integration variable. Specifies the mobile carrier. The key value for `carrier.tsv` [Dynamic lookup](dynamic-lookups.md). | varchar(100) |
| **`ch_hdr`** | Client hints collected through the HTTP request header. | text |
| **`ch_js`** | Client hints collected through the User-Agent Client Hints JavaScript API. | text |
| **`channel`** | The [Site sections](/help/components/dimensions/site-section.md) dimension.| varchar(100) |
| **`clickmaplink`** | Activity Map link | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map link by region | varchar(255) |
| **`clickmappage`** | Activity Map page | varchar(255) |
| **`clickmapregion`** | Activity Map region | varchar(255) |
| **`code_ver`** | API or client SDK version used to compile and send the image request. | char(16) |
| **`color`** | Color depth ID based on the value of the `c_color` column. References the `color_depth.tsv` lookup table.| smallint unsigned |
| **`connection_type`** | A numeric ID that represents the connection type. The [Connection type](/help/components/dimensions/connection-type.md) dimension. References the `connection_type.tsv` lookup table. | tinyint unsigned |
| **`cookies`** | The [Cookie support](/help/components/dimensions/cookie-support.md) dimension.<br>Y: Enabled<br>N: Disabled<br>U: Unknown| char(1)|
| **`country`** | A numeric ID that represents the country of the visitor. References the `country.tsv` lookup table. | smallint unsigned|
| **`ct_connect_type`** | Related to the `connection_type` column. The most common values are LAN/Wifi, Mobile Carrier, and Modem. | char(20) |
| **`curr_factor`** | Determines the currency decimal place, and is used for currency conversion. For example, USD uses two decimal places, so this column value would be `2`. | tinyint |
| **`curr_rate`** | The exchange rate when the transaction occurred. Adobe partners with XE to determine the current day's exchange rate. | decimal(24,12) |
| **`currency`** | The currency code that was used during the transaction. Set using [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8)|
| **`cust_hit_time_gmt`** | Timestamp-enabled report suites only. The timestamp sent with the hit, based in UNIX&reg; time. | int|
| **`cust_visid`** | The custom visitor ID, if set using [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | varchar(255) |
| **`daily_visitor`** | A flag that determines if the hit is a new daily visitor. | tinyint unsigned |
| **`dataprivacyconsentoptin`** | The [Consent management opt-in](/help/components/dimensions/cm-opt-in.md) dimension. Multiple values can be present per hit, separated by a pipe (`\|`). Valid values include `DMP` and `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | The [Consent management opt-out](/help/components/dimensions/cm-opt-out.md) dimension. Multiple values can be present per hit, separated by a pipe (`\|`). Valid values include `SSF`, `DMP`, and `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | A value that identifies if consent is acquired for sending data from Adobe Analytics through Adobe Advertising to third-party advertising providers (like Google). See [Ad Consent](/help/components/dimensions/ad-consent.md) for more information. | varchar(100) | 
| **`date_time`** | The time of the hit in readable format, based on the report suite's time zone. | datetime |
| **`domain`** | The [Domain](/help/components/dimensions/domain.md) dimension. Based on the visitor's Internet access point. | varchar(100) |
| **`duplicate_events`** | Lists each event that was counted as a duplicate. | varchar(255) |
| **`duplicate_purchase`** | A flag that determines if the purchase event for this hit is ignored because it is a duplicate. | tinyint unsigned |
| **`duplicated_from`** | Only used in report suites containing hit copy VISTA rules. Indicates which report suite that the hit was copied from. | varchar(40)|
| **`ef_id`** | The `ef_id` used in Adobe Advertising integrations. | varchar(255) |
| **`evar1 - evar250`** | Custom variables 1-250. Used in [eVar](/help/components/dimensions/evar.md) dimensions. Each organization uses eVars differently. The best place for more information on how your organization populates respective eVars would be a [solution design document](/help/implement/prepare/solution-design.md) specific to your organization. | varchar(255) |
| **`event_list`** | Comma-separated list of numeric IDs that represent events triggered on the hit. Includes both default events and [custom events 1-1000](/help/components/metrics/custom-events.md). Uses `event.tsv` lookup. | text |
| **`exclude_hit`** | A flag that determines if the hit is excluded from reporting. The `visit_num` column is not incremented for excluded hits.<br>1: Not used. Part of a scrapped feature.<br>2: Not used. Part of a scrapped feature.<br>3: No longer used. User agent exclusion<br>4: Exclusion based on IP address<br>5: Vital hit info missing, such as `page_url`, `pagename`, `page_event`, or `event_list`<br>6: JavaScript did not correctly process hit<br>7: Account-specific exclusion, such as in a VISTA rules<br>8: Not used. Alternate account-specific exclusion.<br>9: Not used. Part of a scrapped feature.<br>10: Invalid currency code<br>11: Hit missing a timestamp on a timestamp-only report suite, or a hit contained a timestamp on a non-timestamp report suite<br>12: Not used. Part of a scrapped feature.<br>13: Not used. Part of a scrapped feature.<br>14: Target hit that did not match up with an Analytics hit<br>15: Not currently used.<br>16: Advertising Cloud hit that did not match up to an Analytics hit | tinyint unsigned |
| **`first_hit_page_url`** | The very first URL of the visitor. | varchar(255) |
| **`first_hit_pagename`** | The [Entry page original](/help/components/dimensions/entry-dimensions.md) dimension. The original entry page name of the visitor. | varchar(100) |
| **`first_hit_ref_domain`** | The [Original referring domain](/help/components/dimensions/original-referring-domain.md) dimension. Based on `first_hit_referrer`. The very first referring domain of the visitor. | varchar(100) |
| **`first_hit_ref_type`** | A numeric ID that represents the referrer type of the very first referrer of the visitor. References the `referrer_type.tsv` lookup table. | tinyint unsigned |
| **`first_hit_referrer`** | The very first referring URL of the visitor. | varchar(255) |
| **`first_hit_time_gmt`** | Timestamp of the very first hit of the visitor in UNIX&reg; time. | int |
| **`geo_city`** | The name of the city that the hit came from, based on IP. Used in the [Cities](/help/components/dimensions/cities.md) dimension. | char(32) |
| **`geo_country`** | The abbreviation of the country that the hit came from, based on IP. Used in the [Countries](/help/components/dimensions/countries.md) dimension. | char(4) |
| **`geo_dma`** | A numeric ID of the demographic area that the hit came from, based on IP. Used in the [US DMA](/help/components/dimensions/us-dma.md) dimension. | int unsigned |
| **`geo_region`** | The name of the state or region that the hit came from, based on IP. Used in the [Regions](/help/components/dimensions/regions.md) dimension. | char(32) |
| **`geo_zip`** | The zip code that the hit came from, based on IP. Helps populate the [Zip code](/help/components/dimensions/zip-code.md) dimension. See also `zip`. | varchar(16) |
| **`hit_source`** | The source that the hit came from. Hit sources 1, 2, and 6 are billed. <br>1: Standard image request without timestamp <br>2: Standard image request with timestamp <br>3: Live data source upload with timestamps <br>4: Not used <br>5: Generic data source upload <br>6: Full processing data source upload <br>7: TransactionID data source upload <br>8: No longer used; Previous versions of Adobe Advertising Cloud data sources <br>9: No longer used; Adobe Social summary metrics <br>10: Audience Manager server-side forwarding used | tinyint unsigned |
| **`hit_time_gmt`** | The timestamp of the hit Adobe data collection servers received the hit, based in UNIX&reg; time. | int |
| **`hitid_high`** | Used with `hitid_low` to identify a hit. | bigint unsigned |
| **`hitid_low`** | Used with `hitid_high` to identify a hit. | bigint unsigned |
| **`hourly_visitor`** | A flag that determines if the hit is a new hourly visitor. | tinyint unsigned |
| **`ip`** | The IPv4 address, based on the HTTP header of the image request. Mutually exclusive to `ipv6`; if this column contains a non-obfuscated IP address, `ipv6` is blank. | char(20) |
| **`ipv6`** | The compressed IPv6 address, if available. Mutually exclusive to `ip`; if this column contains a non-obfuscated IP address, `ip` is blank. | varchar(40) |
| **`j_jscript`** | Version of JavaScript supported by the browser. | char(5) |
| **`java_enabled`** | The [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). <br>Y: Enabled <br>N: Disabled <br>U: Unknown | char(1)|
| **`javascript`** | A lookup ID of JavaScript version, based on `j_jscript`. References the `javascript_version` lookup table. | tinyint unsigned |
| **`language`** | A numeric ID that represents the visitor's language. References the `languages.tsv` lookup table. | smallint unsigned |
| **`last_hit_time_gmt`** | Timestamp (in UNIX&reg; time) of the prior hit. Used to calculate the [[!UICONTROL Days since last visit]](/help/components/dimensions/days-since-last-visit.md) dimension. | int |
| **`last_purchase_num`** | The [Customer loyalty](/help/components/dimensions/customer-loyalty.md) dimension. The number of previous purchases the visitor has made. <br>0: No prior purchases (not a customer) <br>1: 1 prior purchase (new customer) <br>2: 2 prior purchases (return customer) <br>3: 3 or more prior purchases (loyal customer) | int unsigned |
| **`last_purchase_time_gmt`** | Used in the [[!UICONTROL Days since last purchase]](/help/components/dimensions/days-since-last-purchase.md) dimension. Timestamp (in UNIX&reg; time) of the last purchase made. For first-time purchases and visitors that have not made a purchase before, this value is `0`. | int |
| **`latlon1`** | Location (down to 10 km) | varchar(255) |
| **`latlon23`** | Location (down to 100 m) | varchar(255) |
| **`latlon45`** | Location (down to 1 m) | varchar(255) |
| **`mc_audiences`** | List of Audience Manager segment IDs that the visitor belongs to. The `post_mc_audiences` column changes the delimiter to `--**--`. | text |
| **`mcvisid`** | Experience Cloud Visitor ID. 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits. | varchar(255) |
| **`mobile_id`** | If the user is using a mobile device, the numeric ID of the device. The key value for `mobile_attributes.tsv` [Dynamic lookup](dynamic-lookups.md). | int |
| **`mobileaction`** | Mobile action. Automatically collected when `trackAction` is called in mobile implementations. Allows for automatic action pathing in the app. | varchar(100) |
| **`mobileappid`** | Mobile app ID. Stores the application name and version in the following format: `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Used in the Apteligent data connector. The App ID used in Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Used in the Apteligent data connector. The crash ID used in Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Used in the [!DNL Appfigures] data connector. App store object ID. | varchar(255) |
| **`mobilebeaconmajor`** | Mobile Services beacon major | varchar(100) |
| **`mobilebeaconminor`** | Mobile Services beacon minor | varchar(100) |
| **`mobilebeaconproximity`** | Mobile Services beacon proximity | varchar(255) |
| **`mobilebeaconuuid`** | Mobile Services beacon UUID | varchar(100) |
| **`mobilecampaigncontent`** | The name or ID of the content that displayed the link. Populated by Mobile App Acquisition.| varchar(255) |
| **`mobilecampaignmedium`** | Marketing medium, such as banner or email. Populated by Mobile App Acquisition.| varchar(255) |
| **`mobilecampaignname`** | The name of the campaign, also stored in the campaign variable. Populated by Mobile App Acquisition. | varchar(255) |
| **`mobilecampaignsource`** | Original referrer, such as newsletter or social media network. Populated by Mobile App Acquisition.| varchar(255) |
| **`mobilecampaignterm`** | Paid keywords or other terms you want to track with this acquisition. Populated by Mobile App Acquisition. | varchar(255) |
| **`mobiledayofweek`** | Number of the weekday that the app was launched on.| varchar(255) |
| **`mobiledayssincefirstuse`** | Number of days since the app was run for the first time. | varchar(255) |
| **`mobiledayssincelastuse`** | Number of days since the app was last run. | varchar(255) |
| **`mobiledeeplinkid`** | Collected from the context data variable `a.deeplink.id`. Used in acquisition reports as an identifier for mobile acquisition link.| varchar(255) |
| **`mobiledevice`** | Mobile device name. On iOS, it is stored as a comma-separated 2-digit string. The first number represents the device generation, and the second number represents the device family. | varchar(255) |
| **`mobilehourofday`** | Defines the hour of the day that the app was launched. Follows 24-hour numerical format. | varchar(255) |
| **`mobileinstalldate`** | Mobile install date. Provides the date of the first time that a user opens the mobile app.| varchar(255) |
| **`mobilelaunchnumber`** | Increments by one each time the mobile app is launched.| varchar(255) |
| **`mobilemessagebuttonname`** | Collected from the context data variable `a.message.button.id`. Used for in-app messaging to identify the button that closed the message.| varchar(100) |
| **`mobilemessageid`** | In-app Message ID | varchar(255) |
| **`mobilemessageonline`** | In-app Message Online | varchar(255) |
| **`mobilemessagepushoptin`** | Collected from the context data variable `a.push.optin`. Set to "true" when the user opts in to push messaging; otherwise the value is "false".| varchar(255) |
| **`mobilemessagepushpayloadid`** | Collected from the context data variable `a.push.payloadid`. Used in push messaging as the payload identifier. | varchar(255) |
| **`mobileosversion`** | Mobile Services operating system version | varchar(255) |
| **`mobileplaceaccuracy`** | Collected from the context data variable `a.loc.acc`. Indicates the accuracy of the GPS in meters at time of collection. | varchar(255) |
| **`mobileplacecategory`** | Collected from the context data variable `a.loc.category`. Describes the category of a specific place. | varchar(255) |
| **`mobileplaceid`** | Collected from the context data variable `a.loc.id`. Identifier for a given point of interest. | varchar(255) |
| **`mobilepushoptin`** | Mobile Services Push opt-in | varchar(255) |
| **`mobilepushpayloadid`** | Mobile Services Push payload ID | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Mobile Services launch content | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Mobile Services launch medium | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Mobile Services launch source | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Mobile Services launch term | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Collected from the context data variable `a.launch.campaign.trackingcode`. Used in acquisition as the tracking code for launch campaign. | varchar(255) |
| **`mobileresolution`** | Resolution of the mobile device. `[Width] x [Height]` in pixels. | varchar(255) |
| **`monthly_visitor`** | A flag that determines if the visitor is unique to the current month. | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | [List variable](/help/implement/vars/page-vars/list.md) values. Contains a delimited list of custom values depending on implementation. The `post_mvvar1` - `post_mvvar3` columns replace the original delimiter with `--**--`. | text |
| **`mvvar1_instances`** - `mvvar3_instances` | The list variable values that were set on the current hit. Replaces the original delimiter with `--**--`. `post` column is not expected to receive any data for these variables. | text |
| **`new_visit`** | A flag that determines if the current hit is a new visit. Set by Adobe after 30 minutes of visit inactivity. | tinyint unsigned |
| **`os`** | A numeric ID that represents the operating system of the visitor. Based on the `user_agent` column. The key value for `operating_system.tsv` standard lookup and `operating_system_type.tsv` [Dynamic lookup](dynamic-lookups.md). | int unsigned |
| **`page_event`** | The type of hit that is sent in the image request (standard hit, download link, custom link, exit link). See [Page event lookup](datafeeds-page-event.md). | tinyint unsigned |
| **`page_event_var1`** | Only used in link tracking image requests. The URL of the download link, exit link, or custom link clicked.| text |
| **`page_event_var2`** | Only used in link tracking image requests. The custom name (if specified) of the link. Sets the [Custom link](/help/components/dimensions/custom-link.md), [Download link](/help/components/dimensions/download-link.md), or [Exit link](/help/components/dimensions/exit-link.md) depending on the value in `page_event`. | varchar(100) |
| **`page_type`** | The [Pages not found](/help/components/dimensions/pages-not-found.md) dimension, which is typically used for 404 pages. | char(20) |
| **`page_url`** | The URL of the hit. Note that `post_page_url` is stripped for link tracking image requests ([`tl()`](/help/implement/vars/functions/tl-method.md)) and uses a data type of varchar(255). | text |
| **`pagename`** | The [Page](/help/components/dimensions/page.md) dimension. If the [`pagename`](/help/implement/vars/page-vars/pagename.md) variable is empty, Analytics uses `page_url` instead. | varchar(100) |
| **`pagename_no_url`** | Similar to `pagename`, except it does not fall back to `page_url`. Only the `post` column is available. | varchar(100) |
| **`paid_search`** | A flag that determines if the hit matches paid search detection. | tinyint unsigned |
| **`persistent_cookie`** | Used in the [Persistent cookie support](/help/components/dimensions/persistent-cookie-support.md) dimension. Indicates if the visitor supports cookies that are not discarded after each hit. | char(1) |
| **`pointofinterest`** | Mobile Services point of interest name | varchar(255) |
| **`pointofinterestdistance`** | Mobile Services distance to point of interest center | varchar(255) |
| **`post_`** columns | Contains the value ultimately used in reports. Each post column is populated after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases. | See respective non-post column |
| **`product_list`** | The [`products`](/help/implement/vars/page-vars/products.md) page variable. Helps populate several dimensions and metrics, including [Category](/help/components/dimensions/category.md), [Product](/help/components/dimensions/product.md), [Units](/help/components/metrics/units.md), and [Revenue](/help/components/metrics/revenue.md). | text |
| **`prop1`** - `prop75`| Custom traffic variables 1-75. Used in [Prop](/help/components/dimensions/prop.md) dimensions. | varchar(100) |
| **`purchaseid`**| Unique identifier for a purchase, as set using the [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) variable. Used by the `duplicate_purchase` column. | char(20) |
| **`quarterly_visitor`** | A flag that determines if the hit is a new quarterly visitor. | tinyint unsigned |
| **`ref_domain`** | The [Referring domain](/help/components/dimensions/referring-domain.md) dimension. Based on the `referrer` column. | varchar(100) |
| **`ref_type`** | A numeric ID that represents the type of referral for the hit. Used in the [Referrer type](/help/components/dimensions/referrer-type.md) dimension. <br>1: Inside your site<br>2: Other web sites <br>3: Search engines <br>4: Hard drive <br>5: USENET <br>6: Typed/Bookmarked (no referrer) <br>7: Email <br>8: No JavaScript <br>9: Social Networks | tinyint unsigned |
| **`referrer`** | The [Referrer](/help/components/dimensions/referrer.md) dimension. Note that while `referrer` uses a data type of varchar(255), `post_referrer` uses a data type of varchar(244). | varchar(255) |
| **`resolution`** | A numeric ID that represents the resolution of the monitor. Used in the [Monitor resolution](/help/components/dimensions/monitor-resolution.md) dimension. Uses `resolution.tsv` lookup table. | smallint unsigned |
| **`s_kwcid`** | Keyword ID used in Adobe Advertising integrations. | varchar(255) |
| **`s_resolution`** | Raw screen resolution value. Gathered using the JavaScript function `screen.width x screen.height`. | char(20) |
| **`search_engine`** | A numeric ID that represents the search engine that referred the visitor to your site. Used in [Search Engine](/help/components/dimensions/search-engine.md) dimensions. References the `search_engines.tsv` lookup table. | smallint unsigned|
| **`search_page_num`** | Used by the [All Search Page Rank](/help/components/dimensions/all-search-page-rank.md) dimension. Indicates which page of search results that your site appeared on before the user clicked through to your site. | smallint unsigned |
| **`secondary_hit`** | A flag that determines if the hit is a secondary hit. This flag typically originates from multi-suite tagging and VISTA rules that copy hits. | tinyint unsigned |
| **`sourceid`** | Source ID | int unsigned |
| **`state`** | State variable. | varchar(50) |
| **`stats_server`** | Not of use. Adobe internal server that processed the hit. | char(30) |
| **`t_time_info`** | Local time for the visitor. Format is: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Used in Adobe Target integrations. Represents all tests currently qualified for. Format is: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | text |
| **`tnt_action`** | Used in Adobe Target integrations. Represents all tests the hit qualified for. | text |
| **`tnt_instances`** | Used in Adobe Target integrations. Target instances variable. | text |
| **`transactionid`** | A unique identifier where various data points can be uploaded later via data sources. Collected using the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable. | text |
| **`truncated_hit`** | A flag that indicates that the image request was truncated. Indicates that a partial hit was received. <br>Y: Hit was truncated; partial hit received <br>N: Hit was not truncated; full hit received | char(1)|
| **`user_agent`** | The user agent string sent in the HTTP header of the image request. | text |
| **`user_hash`** | Not of use. Hash on the report suite ID. Use `username` instead. | int unsigned |
| **`user_server`** | Used in the [Server](/help/components/dimensions/server.md) dimension. | varchar(100) |
| **`userid`** | Not of use. The numeric ID for the report suite ID. Use `username` instead. | int unsigned |
| **`username`** | The report suite ID for the hit. | char(40) |
| **`va_closer_detail`** | The [Last touch detail](/help/components/dimensions/last-touch-detail.md) dimension. | varchar(255) |
| **`va_closer_id`** | A numeric ID that identifies the [Last touch channel](/help/components/dimensions/last-touch-channel.md) dimension. The lookup for this ID can be found in the Marketing Channel Manager. | tinyint unsigned |
| **`va_finder_detail`** | The [First touch detail](/help/components/dimensions/first-touch-detail.md) dimension. | varchar(255) |
| **`va_finder_id`** | A numeric ID that identifies the [First touch channel](/help/components/dimensions/first-touch-channel.md) dimension. The lookup for this ID can be found in the Marketing Channel Manager. | tinyint unsigned |
| **`va_instance_event`** | A flag that identifies Marketing Channel [Instances](/help/components/metrics/instances.md). | tinyint unsigned |
| **`va_new_engagement`** | A flag that identifies Marketing Channel [New engagements](/help/components/metrics/new-engagements.md). | tinyint unsigned |
| **`video`** | Video content | varchar(255) |
| **`videoad`** | Video ad name | varchar(255) |
| **`videoadinpod`** | Video ad in pod position | varchar(255) |
| **`videoadlength`** | Video ad length | integer |
| **`videoadload`** | Video ad loads | varchar(255) |
| **`videoadname`** | Video ad name | varchar(255) |
| **`videoadplayername`** | Video ad player name | varchar(255) |
| **`videoadpod`** | Video ad pod | varchar(255) |
| **`videoadvertiser`** | Video advertiser | varchar(255) |
| **`videoaudioalbum`** | Video audio album | varchar(255) |
| **`videoaudioartist`** | Video audio artist | varchar(255) |
| **`videoaudioauthor`** | Video audio author | varchar(255) |
| **`videoaudiolabel`** | Video audio label | varchar(255) |
| **`videoaudiopublisher`** | Video audio publisher | varchar(255) |
| **`videoaudiostation`** | Video audio station | varchar(255) |
| **`videocampaign`** | Video campaign | varchar(255) |
| **`videochannel`** | Video channel | varchar(255) |
| **`videochapter`** | Video chapter name | varchar(255) |
| **`videocontenttype`** | Video content type. Set to 'Video' automatically for all video views | varchar(255) |
| **`videodaypart`** | Video day part | varchar(255) |
| **`videoepisode`** | Video episode | varchar(255) |
| **`videofeedtype`** | Video feed type| varchar(255) |
| **`videogenre`** | Video genre | text |
| **`videolength`** | Video length | integer |
| **`videomvpd`** | Video MVPD | varchar(255) |
| **`videoname`** | Video name | varchar(255) |
| **`videonetwork`** | Video network | varchar(255) |
| **`videopath`** | Video path | varchar(100) |
| **`videoplayername`** | Video player name | varchar(255) |
| **`videotime`** | Video time | integer |
| **`videoqoebitrateaverageevar`** | Video quality average bit rate | varchar(255) |
| **`videoqoebitratechangecountevar`** | Video quality change count | varchar(255) |
| **`videoqoebuffercountevar`** | Video quality buffer count | varchar(255) |
| **`videoqoebuffertimeevar`** | Video quality buffer time | varchar(255) |
| **`videoqoedroppedframecountevar`** | Video quality dropped frame count | varchar(255) |
| **`videoqoeerrorcountevar`** | Video quality error count | varchar(255) |
| **`videoqoeextneralerrors`** | Video quality external errors | text |
| **`videoqoeplayersdkerrors`** | Video quality SDK errors | text |
| **`videoqoetimetostartevar`** | Video quality time to start | varchar(255) |
| **`videoseason`** | Video season | varchar(255) |
| **`videosegment`** | Video segment | varchar(255) |
| **`videoshow`** | Video show | varchar(255) |
| **`videoshowtype`** | Video show type | varchar(255) |
| **`videostreamtype`** | Video stream type | varchar(255) |
| **`visid_high`** | Used with `visid_low` to uniquely identify a visitor. | bigint unsigned |
| **`visid_low`** | Used with `visid_high` to uniquely identify a visitor. | bigint unsigned |
| **`visid_new`** | A flag that determines if the hit contains a newly generated visitor ID. | char(1) |
| **`visid_timestamp`** | If a visitor ID is newly generated, provides the timestamp in UNIX&reg; time of when the visitor ID was generated. | int |
| **`visid_type`** | Not for external use; internally used by Adobe for processing optimizations. A numeric ID that represents the method used to identify the visitor.<br>`0`: Custom visitor ID or Unknown/not applicable<br>`1`: IP and user agent fallback <br>`2`: HTTP Mobile Subscriber Header <br>`3`: Legacy cookie value (`s_vi`) <br>`4`: Fallback cookie value (`s_fid`) <br>`5`: Identity Service | tinyint unsigned |
| **`visit_keywords`** | The [Search keyword](/help/components/dimensions/search-keyword.md) dimension. This column uses a non-standard character limit of varchar(244) to accommodate back-end logic used by Adobe. | varchar(244) |
| **`visit_num`** | The [Visit number](/help/components/dimensions/visit-number.md) dimension. Starts at 1, and increments each time a new visit starts per visitor. | int unsigned |
| **`visit_page_num`** | The [Hit depth](/help/components/dimensions/hit-depth.md) dimension. Increases by 1 for each hit that the visitor generates. Resets each visit. | int unsigned |
| **`visit_ref_domain`** | Based on the `visit_referrer` column. The first referring domain of the visit. | varchar(100) |
| **`visit_ref_type`** | A numeric ID that represents the referrer type of the first referrer of the visit. References the `referrer_type.tsv` lookup table. | tinyint unsigned |
| **`visit_referrer`** | The first referrer of the visit. | varchar(255) |
| **`visit_search_engine`** | A numeric ID that represents the first search engine of the visit. References the `search_engines.tsv` lookup table. | smallint unsigned |
| **`visit_start_page_url`** | The first URL of the visit. | varchar(255) |
| **`visit_start_pagename`** | The Page Name value in the first hit of the visit. | varchar(100) |
| **`visit_start_time_gmt`** | Timestamp (in UNIX&reg; time) of the first hit of the visit. | int |
| **`weekly_visitor`** | A flag that determines if the hit is a new weekly visitor. | tinyint unsigned |
| **`yearly_visitor`** | A flag that determines if the hit is a new yearly visitor. | tinyint unsigned |
| **`zip`** | Helps populate the [Zip code](/help/components/dimensions/zip-code.md) dimension. See also `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Unused or retired columns

The following list of columns are unused and do not typically contain data. Columns that do contain data are not supported by current data collection libraries, and are not available dimensions in Analysis Workspace.

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`
