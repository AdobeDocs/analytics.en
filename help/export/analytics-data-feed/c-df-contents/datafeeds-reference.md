---
description: Table data describing the columns in the data feed.
keywords: Data Feed;columns
seo-description: Table data describing the columns in the data feed.
seo-title: Data column reference
solution: Analytics
subtopic: data feeds
title: Data column reference
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
---

# Data column reference

Use this page to learn what data is contained in each column. Most implementations don't use every column, so this page can be referenced when determining which columns to include in a data feed export.

> [!IMPORTANT] For any given column (for instance, one that is defined as 255 characters), a data feed can send additional characters due to the addition of characters escaping values in a string. Keep this topic in mind if your implementation regularly sends values that exceed character limits.

## Columns, Descriptions, and Data Types

> [!NOTE] Most columns contain a similar column with a prefix of `post_`. Post columns contain values after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases.

| Column name | Column description | Data type |
| --- | --- | --- |
| accept_language | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| aemassetid| A multi-value variable corresponding to Asset ID's (GUID's) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |
| aemassetsource| Identifies the source of the asset event. Used in Adobe Experience Manager.| varchar(255) |
| aemclickedassetid | Asset ID of an Adobe Experience Manager asset. Increments Click Events.| varchar(255) |
| browser | Numeric ID of the browser. References the browser.tsv lookup table.| int unsigned |
| browser_height| Height in pixels of the browser window.| smallint unsigned |
| browser_width | Width in pixels of the browser window. | smallint unsigned |
| c_color | Bit depth of the color palette. Used as part of calculating the Color Depth dimension. Uses the JavaScript function screen.colorDepth(). | char(20) |
| campaign| Variable used in the Tracking Code dimension.| varchar(255) |
| carrier | Adobe Advertising Cloud integration variable. Specifies the mobile carrier. References the carrier lookup table. | varchar(100) |
| channel | Variable used in the Site Sections dimension.| varchar(100) |
| click_action| No longer used. Address of linked clicked in the legacy Clickmap tool. | varchar(100) |
| click_action_type | No longer used. Link type of the legacy Clickmap tool.<br>0: HREF URL<br>1: Custom ID<br>2: JavaScript onClick event<br>3: Form element| tinyint unsigned |
| click_context | No longer used. Page name where the link click occurred. Part of the legacy Clickmap tool. | varchar(255) |
| click_context_type| No longer used. Indicates if click_context had a page name or defaulted to page URL.<br>0: Page URL<br>1: Page Name| tinyint unsigned |
| click_sourceid| No longer used. Numeric ID for the location on the page of the clicked link. Part of the legacy Clickmap tool. | int unsigned |
| click_tag | No longer used. Type of HTML element that was clicked. | char(10) |
| clickmaplink| Activity Map link| varchar(255) |
| clickmaplinkbyregion| Activity Map link by region| varchar(255) |
| clickmappage| Activity Map page| varchar(255) |
| clickmapregion| Activity Map region| varchar(255) |
| code_ver| AppMeasurement Library version used to compile and send the image request. | char(16) |
| color | Color depth ID based on the value of the c_color column. References the color_depth.tsv lookup table.| smallint unsigned|
| connection_type | Numeric ID representing the connection type. Variable used in the Connection Type dimension. References the connection_type.tsv lookup table.| tinyint unsigned |
| cookies | Variable used in the Cookie Support dimension.<br>Y: Enabled<br>N: Disabled<br>U: Unknown| char(1)|
| country | Numeric ID representing the country the hit came from. Adobe partners with Digital Envoy to match IP address to country. Uses country.tsv lookup.| smallint unsigned|
| ct_connect_type | Related to the connection_type column. Most common values are LAN/Wifi, Mobile Carrier, and Modem. | char(20) |
| curr_factor | Determines the currency decimal place, and is used for currency conversion. For example, USD uses two decimal places, so this column value would be 2. | tinyint|
| curr_rate | The exchange rate when the transaction occurred. Adobe partners with XE to determine the current day's exchange rate.| decimal(24,12) |
| currency| The currency code that was used during the transaction.| char(8)|
| cust_hit_time_gmt | Timestamp-enabled report suites only. The timestamp sent with the hit, based in Unix time. | int|
| cust_visid| If a custom visitor ID is set, it is populated in this column. | varchar(255) |
| daily_visitor | Flag to determine if the hit is a new daily visitor. | tinyint unsigned |
| date_time | The time of the hit in readable format, based on the report suite's time zone. | datetime |
| domain| Variable used in the Domain dimension. Based on the user's internet service provider (ISP).| varchar(100) |
| duplicate_events| Lists each event that was counted as a duplicate.| varchar(255) |
| duplicate_purchase| Flag indicating that the purchase event for this hit should be ignored because it is a duplicate.| tinyint unsigned |
| duplicated_from | Only used in report suites containing hit copy VISTA rules. Indicates which report suite the hit was copied from.| varchar(40)|
| ef_id | The ef_id used in Adobe Advertising Cloud integrations.| varchar(255) |
| evar1 - evar250 | Custom variables 1-250. Each organization uses eVars differently. The best place for more information on how your organization populates respective eVars would be a solution design document specific to your organization. | varchar(255) |
| event_list| Comma-separated list of numeric IDs representing events triggered on the hit. Includes both default events and custom events 1-1000. Uses event.tsv lookup.| text |
| exclude_hit | Flag indicating the hit is excluded from reporting. The visit_num column is not incremented for excluded hits.<br>1: Not used. Part of a scrapped feature.<br>2: Not used. Part of a scrapped feature.<br>3: No longer used. User agent exclusion<br>4: Exclusion based on IP address<br>5: Vital hit info missing, such as page_url, pagename, page_event, or event_list<br>6: JavaScript did not correctly process hit<br>7: Account-specific exclusion, such as in a VISTA rules<br>8: Not used. Alternate account-specific exclusion.<br>9: Not used. Part of a scrapped feature.<br>10: Invalid currency code<br>11: Hit missing a timestamp on a timestamp-only report suite, or a hit contained a timestamp on a non-timestamp report suite<br>12: Not used. Part of a scrapped feature.<br>13: Not used. Part of a scrapped feature.<br>14: Target hit that did not match up with an Analytics hit<br>15: Not currently used.<br>16: Advertising Cloud hit that did not match up to an Analytics hit | tinyint unsigned |
| first_hit_page_url| The very first URL of the visitor. | varchar(255) |
| first_hit_pagename| Variable used in the Entry Page Original dimension. The original entry page name of the visitor. | varchar(100) |
| first_hit_ref_domain| Variable used in the Original Referring Domain dimension. Based on first_hit_referrer. The very first referring domain of the visitor. | varchar(100) |
| first_hit_ref_type| Numeric ID representing the referrer type of the very first referrer of the visitor. Uses referrer_type.tsv lookup.| tinyint unsigned |
| first_hit_referrer| The very first referring URL of the visitor. | varchar(255) |
| first_hit_time_gmt| Timestamp of the very first hit of the visitor in Unix time. | int|
| geo_city| Name of the city the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to city.| char(32) |
| geo_country | Abbreviation of the country the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to country.| char(4)|
| geo_dma | Numeric ID of the demographic area the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to demographic area.| int unsigned |
| geo_region| Name of the state or region the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to state/region. | char(32) |
| geo_zip | The zip code the hit came came from, based on IP. Adobe partners with Digital Envoy to match IP address to zip code. | varchar(16)|
| hier1 - hier5 | Used by hierarchy variables. Contains a delimited list of values. The delimiter is chosen under report suite settings. | varchar(255) |
| hit_source| Indicates what source the hit came from. <br>1: Standard image request without timestamp <br>2: Standard image request with timestamp <br>3: Live data source upload with timestamps <br>4: Not used <br>5: Generic data source upload <br>6: Full processing data source upload <br>7: TransactionID data source upload <br>8: No longer used; Previous versions of Adobe Advertising Cloud data sources <br>9: No longer used; Adobe Social summary metrics | tinyint unsigned |
| hit_time_gmt| The timestamp of the hit Adobe data collection servers received the hit, based in Unix time. | int|
| hitid_high| Used in combination with hitid_low to uniquely identify a hit. | bigint unsigned|
| hitid_low | Used in combination with hitid_high to uniquely identify a hit.| bigint unsigned|
| homepage| No longer used. Indicated if the current URL is the browser's homepage.| char(1)|
| hourly_visitor| Flag to determine if the hit is a new hourly visitor.| tinyint unsigned |
| ip| IP Address, based on the HTTP header of the image request. | char(20) |
| ip2 | Not used. Backend reference variable for report suites containing VISTA rules based on IP address. | char(20) |
| j_jscript | Version of JavaScript supported by the browser.| char(5)|
| java_enabled| Flag indicating whether Java is enabled. <br>Y: Enabled <br>N: Disabled <br>U: Unknown | char(1)|
| javascript| Lookup ID of JavaScript version, based on j_jscript. Uses lookup table.| tinyint unsigned |
| language| Numeric ID of language. Uses languages.tsv lookup table. | smallint unsigned|
| last_hit_time_gmt | Timestamp (in Unix time) of the prior hit. Used to calculate the Days Since Last Visit dimension.| int|
| last_purchase_num | Variable used in the Customer Loyalty dimension. Indicates the number of previous purchases the visitor has made. <br>0: No prior purchases (not a customer) <br>1: 1 prior purchase (new customer) <br>2: 2 prior purchases (return customer) <br>3: 3 or more prior purchases (loyal customer) | int unsigned |
| last_purchase_time_gmt| Used in the Days Since Last Purchase dimension. Timestamp (in Unix time) of the last purchase made. For first-time purchases and visitors that have not made a purchase before, this value is 0. | int|
| latlon1 | Location (down to 10 km) | varchar(255) |
| latlon23| Location (down to 100 m) | varchar(255) |
| latlon45| Location (down to 1 m) | varchar(255) |
| mc_audiences| List of Audience Manager segment IDs that the visitor belongs to.| text |
| mcvisid | Experience Cloud Visitor ID. 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits. | varchar(255) |
| mobile_id | If the user is using a mobile device, the numeric ID of the device.| int|
| mobileaction| Mobile action. Automatically collected when trackAction is called in Mobile Services. Allows for automatic action pathing in the app.| varchar(100) |
| mobileappid | Mobile app ID. Stores the application name and version in the following format:[AppName] [BundleVersion] | varchar(255) |
| mobileappperformanceappid | Used in the Apteligent data connector. The App ID used in Apteligent.| varchar(255) |
| mobileappperformancecrashid | Used in the Apteligent data connector. The crash ID used in Apteligent.| varchar(255) |
| mobileappstoreobjectid| Used in the Appfigures data connector. App store object ID | varchar(255) |
| mobilebeaconmajor | Mobile Services beacon major | varchar(100) |
| mobilebeaconminor | Mobile Services beacon minor | varchar(100) |
| mobilebeaconproximity | Mobile Services beacon proximity | varchar(255) |
| mobilebeaconuuid| Mobile Services beacon UUID| varchar(100) |
| mobilecampaigncontent | The name or ID of the content that displayed the link. Populated by Mobile App Acquisition.| varchar(255) |
| mobilecampaignmedium| Marketing medium, such as banner or email. Populated by Mobile App Acquisition.| varchar(255) |
| mobilecampaignname| Name of the campaign, also stored in the campaign variable. Populated by Mobile App Acquisition. | varchar(255) |
| mobilecampaignsource| Original referrer, such as newsletter or social media network. Populated by Mobile App Acquisition.| varchar(255) |
| mobilecampaignterm| Paid keywords or other terms you want to track with this acquisition. Populated by Mobile App Acquisition. | varchar(255) |
| mobiledayofweek | Number of the weekday that the app was launched on.| varchar(255) |
| mobiledayssincefirstuse | Number of days since the app was run for the first time. | varchar(255) |
| mobiledayssincelastupgrade| Collected from the context data variable a.DaysSinceLastUpgrade. The number of days that have passed since the previous session. | varchar(255) |
| mobiledayssincelastuse| Number of days since the app was last run. | varchar(255) |
| mobiledeeplinkid| Collected from the context data variable a.<span>deeplink</span>.id. Used in acquisition reports as an identifier for mobile acquisition link.| varchar(255) |
| mobiledevice| Mobile device name. On iOS, it is stored as a comma-separated 2-digit string. The first number represents the device generation, and the second number represents the device family. | varchar(255) |
| mobilehourofday | Defines the hour of the day the app was launched. Follows 24-hour numerical format.| varchar(255) |
| mobileinstalldate | Mobile install date. Provides the date of the first time a user opens the mobile app.| varchar(255) |
| mobilelaunchessincelastupgrade| Collected from the context data variable a.LaunchesSinceUpgrade. Reports the number of launches since last upgrade.| varchar(255) |
| mobilelaunchnumber| Increments by one each time the mobile app is launched.| varchar(255) |
| mobileltv | No longer used. Populated by trackLifetimeValue methods. | varchar(255) |
| mobilemessagebuttonname | Collected from the context data variable a.<span>message</span>.button.id. Used for in-app messaging to identify the button that closed the message.| varchar(100) |
| mobilemessageid | In-app Message ID| varchar(255) |
| mobilemessageonline | In-app Message Online| varchar(255) |
| mobilemessagepushoptin| Collected from the context data variable a.push.optin. Set to "true" when the user opts in to push messaging; otherwise the value is "false".| varchar(255) |
| mobilemessagepushpayloadid| Collected from the context data variable a.push.payloadid. Used in push messaging as the payload identifier. | varchar(255) |
| mobileosenvironment | Collected from the context data variable a.OSEnvironment. States OS environment, such as Android or iOS. | varchar(255) |
| mobileosversion | Mobile Services operating system version | varchar(255) |
| mobileplaceaccuracy | Collected from the context data variable a.loc.acc. Indicates the accuracy of the GPS in meters at time of collection. | varchar(255) |
| mobileplacecategory | Collected from the context data variable a.loc.category. Describes the category of a specific place. | varchar(255) |
| mobileplaceid | Collected from the context data variable a.<span>loc</span>.id. Identifier for a given point of interest. | varchar(255) |
| mobilerelaunchcampaigncontent | Mobile Services launch content | varchar(255) |
| mobilerelaunchcampaignmedium| Mobile Services launch medium| varchar(255) |
| mobilerelaunchcampaignsource| Mobile Services launch source| varchar(255) |
| mobilerelaunchcampaignterm| Mobile Services launch term| varchar(255) |
| mobilerelaunchcampaigntrackingcode| Collected from the context data variable a.launch.campaign.trackingcode. Used in acquisition as the tracking code for launch campaign. | varchar(255) |
| mobileresolution| Resolution of the mobile device. Width x height in pixels. | varchar(255) |
| monthly_visitor | Flag indicating the visitor is unique to the current month.| tinyint unsigned |
| mvvar1 - mvvar3 | List variable values. Contains a delimited list of custom values depending on implementation.| text |
| namespace | Not used. Part of a scrapped feature many years ago. | varchar(50)|
| new_visit | Flag that determines if the current hit is a new visit. Set by Adobe servers after 30 minutes of visit inactivity. | tinyint unsigned |
| os| Numeric ID representing the operating system of the visitor. Based on the user_agent column. Uses os lookup. | int unsigned |
| p_plugins | No longer used. List of plugins available to the browser. Used the JavaScript function navigator.plugins().| text |
| page_event| The type of hit that is sent in the image request (standard hit, download link, custom link, exit link). | tinyint unsigned |
| page_event_var1 | Only used in link tracking image requests. The URL of the download link, exit link, or custom link clicked.| text |
| page_event_var2 | Only used in link tracking image requests. The custom name (if specified) of the link. | varchar(100) |
| page_event_var3 | No longer used. Contained Survey and Media module data. Populated legacy video reports in previous versions of Adobe Analytics.| text |
| page_type | Used to populate the Pages Not Found dimension, used exclusively for 404 pages. This variable should either be empty or contain "ErrorPage". | char(20) |
| page_url| The URL of the hit. Not used in link tracking image requests.| varchar(255) |
| pagename| Used to populate the Pages dimension. If the pagename variable is empty, Analytics uses page_url instead.| varchar(100) |
| paid_search | Flag that is set if the hit matches paid search detection. | tinyint unsigned |
| partner_plugins | Not used. Part of a scrapped feature many years ago. | varchar(255) |
| persistent_cookie | Used by the Persistent Cookie Support dimension. Indicates if the visitor supports cookies that are not discarded after each hit.| char(1)|
| plugins | No longer used. List of numeric ID's that correspond to plugins available within the browser. Uses plugins.tsv lookup. | varchar(180) |
| pointofinterest | Mobile Services point of interest name | varchar(255) |
| pointofinterestdistance | Mobile Services distance to point of interest center | varchar(255) |
| post_ columns | Contains the value ultimately used in reports. Each post column is populated after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases.| See respective non-post column |
| prev_page | Not used. Adobe proprietary identifier of the previous page. | int unsigned |
| product_list| Product list as passed in through the products variable. Products are delimited by commas while individual product properties are delimited by semicolons. | text |
| product_merchandising | Not used. Use product_list instead.| text |
| prop1 - prop75| Custom traffic variables 1-75. | varchar(100) |
| purchaseid| Unique identifier for a purchase, as set using the s_purchaseID variable. Used by the duplicate_purchase column. | char(20) |
| quarterly_visitor | Flag to determine if the hit is a new quarterly visitor. | tinyint unsigned |
| ref_domain| Based on the referrer column. The referring domain of the hit. | varchar(100) |
| ref_type| A numeric ID representing the type of referral for the hit.<br>1: Inside your site<br>2: Other web sites <br>3: Search engines <br>4: Hard drive <br>5: USENET <br>6: Typed/Bookmarked (no referrer) <br>7: Email <br>8: No JavaScript <br>9: Social Networks| tinyint unsigned |
| referrer| Page URL of the previous page. | varchar(255) |
| resolution| Numeric ID representing the resolution of the monitor. Populates the Monitor Resolution dimension. Uses resolution.tsv lookup table. | smallint unsigned|
| s_kwcid | Keyword ID used in Adobe Advertising Cloud integrations. | varchar(255) |
| s_resolution| Raw screen resolution value. Gathered using the JavaScript function screen.width x screen.height.| char(20) |
| sampled_hit | No longer used. Was formerly used for sampling in Ad Hoc Analysis. | char(1)|
| search_engine | Numeric ID representing the Search Engine that referred the visitor to your site. Uses search_engines.tsv lookup.| smallint unsigned|
| search_page_num | Used by the All Search Page Rank dimension. Indicates which page of search results your site appeared on before the user clicked through to your site. | smallint unsigned|
| secondary_hit | Flag that tracks secondary hits. Normally originates from multi-suite tagging and VISTA rules that copy hits.| tinyint unsigned |
| service | Not used. Use page_event instead.| char(2)|
| socialaccountandappids| No longer used. Social account and app ID's| varchar(255) |
| socialassettrackingcode | No longer used. Social campaign variable | varchar(255) |
| socialauthor| No longer used. Social Authors variable| varchar(255) |
| socialcontentprovider | No longer used. Social Platforms/Properties| varchar(255) |
| socialinteractiontype | No longer used. Social interaction type| varchar(255) |
| sociallanguage| No longer used. Social language| varchar(255) |
| sociallatlong | No longer used. Social Latitude/Longitude| varchar(255) |
| socialowneddefinitioninsighttype| No longer used. Social owned definition insight type | varchar(255) |
| socialowneddefinitioninsightvalue | No longer used. Social owned definition insight value| varchar(255) |
| socialowneddefinitionmetric | No longer used. Social owned definition metric | varchar(255) |
| socialowneddefinitionpropertyvspost | No longer used. Social owned definition property vs. post| varchar(255) |
| socialownedpostids| No longer used. Social owned post ID's | varchar(255) |
| socialownedpropertyid | No longer used. Social owned property ID | varchar(255) |
| socialownedpropertyname | No longer used. Social owned property name | varchar(255) |
| socialownedpropertypropertyvsapp| No longer used. Social owned property vs app | varchar(255) |
| state | State variable.| varchar(50)|
| stats_server| Not of use. Adobe internal server that processed the hit.| char(30) |
| t_time_info | Local time for the visitor. Format is as follows: M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes) | varchar(100) |
| tnt | Used in Adobe Target integrations. | text |
| tnt_action| Used in Adobe Target integrations. | text |
| tnt_post_vista| No longer used. Use post_tnt instead.| text |
| transactionid | A unique identifier where various data points can be uploaded later via data sources.| text |
| truncated_hit | A flag indicating that the image request was truncated. Indicates that a partial hit was received. <br>Y: Hit was truncated; partial hit received <br>N: Hit was not truncated; full hit received| char(1)|
| ua_color| No longer used. Formerly used as a fallback for color depth. | char(20) |
| ua_os | No longer used. Formerly used as a fallback for operating system.| char(80) |
| ua_pixels | No longer used. Formerly used as a fallback for browser height and width.| char(20) |
| user_agent| User agent string sent in the HTTP header of the image request.| text |
| user_hash | Not of use. Hash on the report suite ID. Use username instead. | int unsigned |
| user_server | Variable used in the Server dimension. | varchar(100) |
| userid| Not of use. The numeric ID for the report suite ID. Use username instead.| int unsigned |
| username| The report suite ID for the hit. | char(40) |
| va_closer_detail| Variable used in the Last Touch Detail dimension.| varchar(255) |
| va_closer_id| Numeric ID that identifies the Last Touch Channel dimension. Lookup for this ID can be found in the Marketing Channel Manager. | tinyint unsigned |
| va_finder_detail| Variable used in the First Touch Detail dimension. | varchar(255) |
| va_finder_id| Numeric ID that identifies the First Touch Channel dimension. Lookup for this ID can be found in the Marketing Channel Manager.| tinyint unsigned |
| va_instance_event | Flag to identify Marketing Channel instances. Used by the Marketing Channel Last Touch Instances metric. | tinyint unsigned |
| va_new_engagement | Flag to identify Marketing Channel new engagements. Used by the New Engagements metric.| tinyint unsigned |
| video | Video content| varchar(255) |
| videoad | Video ad name| varchar(255) |
| videoadinpod| Video ad in pod position | varchar(255) |
| videoadlength | Video ad length| varchar(255) |
| videoadload | Video ad loads | varchar(255) |
| videoadname | Video ad name| varchar(255) |
| videoadplayername | Video ad player name | varchar(255) |
| videoadpod| Video ad pod | varchar(255) |
| videoadvertiser | Video advertiser | varchar(255) |
| videoaudioalbum | Video audio album| varchar(255) |
| videoaudioartist| Video audio artist | varchar(255) |
| videoaudioauthor| Video audio author | varchar(255) |
| videoaudiolabel | Video audio label| varchar(255) |
| videoaudiopublisher | Video audio publisher| varchar(255) |
| videoaudiostation | Video audio station| varchar(255) |
| videocampaign | Video campaign | varchar(255) |
| videochannel| Video channel| varchar(255) |
| videochapter| Video chapter name | varchar(255) |
| videocontenttype| Video content type. Set to 'Video' automatically for all video views | varchar(255) |
| videodaypart| Video day part | varchar(255) |
| videoepisode| Video episode| varchar(255) |
| videofeedtype | Video feed type| varchar(255) |
| videogenre| Video genre| text |
| videolength | Video length | varchar(255) |
| videomvpd | Video MVPD | varchar(255) |
| videoname | Video name | varchar(255) |
| videonetwork| Video network| varchar(255) |
| videopath | Video path | varchar(100) |
| videoplayername | Video player name| varchar(255) |
| videoqoebitrateaverageevar| Video quality average bit rate | varchar(255) |
| videoqoebitratechangecountevar| Video quality change count | varchar(255) |
| videoqoebuffercountevar | Video quality buffer count | varchar(255) |
| videoqoebuffertimeevar| Video quality buffer time| varchar(255) |
| videoqoedroppedframecountevar | Video quality dropped frame count| varchar(255) |
| videoqoeerrorcountevar| Video quality error count| varchar(255) |
| videoqoeextneralerrors| Video quality external errors| text |
| videoqoeplayersdkerrors | Video quality SDK errors | text |
| videoqoetimetostartevar | Video quality time to start| varchar(255) |
| videoseason | Video season | varchar(255) |
| videosegment| Video segment| varchar(255) |
| videoshow | Video show | varchar(255) |
| videoshowtype | Video show type| varchar(255) |
| videostreamtype | Video stream type| varchar(255) |
| visid_high| Used in combination with visid_low to uniquely identify a visit. | bigint unsigned|
| visid_low | Used in combination with visid_high to uniquely identify a visit.| bigint unsigned|
| visid_new | Flag to identify if the hit contains a newly generated visitor ID. | char(1)|
| visid_timestamp | If visitor ID was newly generated, provides the timestamp (in Unix time) of when the visitor ID was generated. | int|
| visid_type| Numeric ID representing what method was used to identify the visitor. <br>0: Custom visitorID <br>1: IP and user agent fallback <br>2: HTTP Mobile Subscriber Header <br>3: Legacy cookie value (s_vi) <br>4: Fallback cookie value (s_fid) <br>5: Experience Cloud ID Service | tinyint unsigned |
| visit_keywords| Variable used in the Search Keyword dimension. This column uses a non-standard character limit to accommodate back-end logic used by Adobe.| varchar(244) |
| visit_num | Variable used in the Visit Number dimension. Starts at 1, and increments each time a new visit starts per visitor. | int unsigned |
| visit_page_num| Variable used in the Hit Depth dimension. Increases by 1 for each hit the user generates. Resets each visit. | int unsigned |
| visit_ref_domain| Based on the visit_referrer column. The first referring domain of the visit. | varchar(100) |
| visit_ref_type| Numeric ID representing the referrer type of the first referrer of the visit. Uses the referrer_type.tsv lookup table. | tinyint unsigned |
| visit_referrer| The first referrer of the visit. | varchar(255) |
| visit_search_engine | Numeric ID of the first search engine of the visit. Uses the search_engines.tsv lookup table.| smallint unsigned|
| visit_start_page_url| The first URL of the visit.| varchar(255) |
| visit_start_pagename| The first Page Name of the visit.| varchar(100) |
| visit_start_time_gmt| Timestamp (in Unix time) of the first hit of the visit.| int|
| weekly_visitor| Flag to determine if the hit is a new weekly visitor.| tinyint unsigned |
| yearly_visitor| Flag to determine if the hit is a new yearly visitor.| tinyint unsigned |
| zip | Used to populate the Zip Code dimension. | varchar(50)|