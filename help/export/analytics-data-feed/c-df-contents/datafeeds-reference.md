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
index: y
internal: n
snippet: y
---

# Data column reference

Table data describing the columns in the data feed.

>[!NOTE]
>
>For any given column (for instance, one that is defined as 255 characters), a data feed may send additional characters due to the addition of characters escaping values in a string.

<!-- 

<p> See email from matt on 4/14. [Luby] For visitors that visited prior to the implementation of the Experience Cloud ID Service and haven't cleared cookies the pre and post visid_high/low will be based on the legacy Analytics Visitor ID/s_vi the visitor already had assigned. </p> 
<p> 
 <ul id="ul_F6E0659F239E4501B6D1AFD70786CDAB"> 
  <li id="li_60C5CB97A561485891505709209D65F2"> <p>Assume a customer is using visitor ID service and a grace period is set. What will be in the pre visid_high/low columns? I assume it will be the AID based on the s_vi cookie (assuming a cookie was set.) </p> </li> 
 </ul> </p> 
<p> [Luby] For a new visitor if the grace period is enabled and there wasn't a timeout requesting a legacy Analytics Visitor ID the pre/post visid_high/low columns will be set based on that legacy Analytics Visitor ID/s_vi cookie. If there was a timeout the pre visid_high/low columns will be zero and the post_visid_high/low will be based on the Experience Cloud ID. </p> 
<p> 
 <ul id="ul_DAE2C7AB642C4DC98F4C769350B9A44E"> 
  <li id="li_CC5871BFD0364C239F623050E9D802B4"> <p>Assume a customer is using visitor ID service and <u>no</u> grace period is set. What will be in the pre visid_high/low columns? I assume it will be a transformation of Experience Cloud ID. Will it basically be the same values that are in post_visid_high/low? </p> </li> 
 </ul> </p> 
<p> [Luby] For a new visitor if the grace period is NOT enabled no legacy Analytics Visitor ID will be generated and the pre visid_high/low columns will be zero and the post_visid_high/low will be based on the Experience Cloud ID. </p> 
<p> 
 <ul id="ul_67F8EDE33C3D4754A4B47D7492BCE43E"> 
  <li id="li_E81E06977F52418A89F2ECA88D1F159C"> <p>Generally, can customer care/consulting identify from the data in debug logs (the raw export files in DW) or data feeds which hits are based on s.visitorID, AID, and MID? Is the answer to look at the post_visid_type column? Is the information about post_visid_type on this page correct? https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html </p> </li> 
 </ul> </p> 
<p> [Luby] They should use the post_visid_type column and that page looks correct. </p>

 -->

## Columns, Descriptions, and Data Types {#section_A8C63FCDA046483DA3B2082856D11839}

>[!NOTE]
>
>Most columns contain a similar column with a prefix of `post_`. Post columns contain values after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases.

| Column name | Column description | Data type |
|--- |--- |--- |
|accept_language|Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request.|varchar(20)|
|aemassetid|A multi-value variable corresponding to Asset ID's (GUID's) of a set of Adobe Experience Manager Assets. Increments Impression Events.|text|
|aemassetsource|Identifies the source of the asset event. Used in Adobe Experience Manager.|varchar(255)|
|aemclickedassetid|Asset ID of an Adobe Experience Manager asset. Increments Click Events.|varchar(255)|
|browser|Numeric ID of the browser. References the browser.tsv lookup table.|smallint(5) unsigned|
|browser_height|Height in pixels of the browser window.|smallint(5) unsigned|
|browser_width|Width in pixels of the browser window.|smallint(5) unsigned|
|c_color|Bit depth of the color palette. Used as part of calculating the Color Depth dimension. Uses the JavaScript function screen.colorDepth().|varchar(20)|
|campaign|Variable used in the Tracking Code dimension.|varchar(255)|
|carrier|Adobe Advertising Cloud integration variable. Specifies the mobile carrier. References the carrier lookup table.|varchar(100)|
|channel|Variable used in the Site Sections dimension.|varchar(100)|
|click_action|No longer used. Address of linked clicked in the legacy Clickmap tool.|varchar(100)|
|click_action_type|No longer used. Link type of the legacy Clickmap tool.  0: HREF URL  1: Custom ID  2: JavaScript onClick event  3: Form element|tinyint(3) unsigned|
|click_context|No longer used. Page name where the link click occurred. Part of the legacy Clickmap tool.|varchar(255)|
|click_context_type|No longer used. Indicates if click_context had a page name or defaulted to page URL.  0: Page URL  1: Page Name|tinyint(3) unsigned|
|click_sourceid|No longer used. Numeric ID for the location on the page of the clicked link. Part of the legacy Clickmap tool.|int(10) unsigned|
|click_tag|No longer used. Type of HTML element that was clicked.|varchar(10)|
|code_ver|AppMeasurement Library version used to compile and send the image request.|varchar(16)|
|color|Color depth ID based on the value of the c_color column. References the color_depth.tsv lookup table.|smallint(5) unsigned|
|connection_type|Numeric ID representing the connection type. Variable used in the Connection Type dimension. References the connection_type.tsv lookup table.|tinyint(3) unsigned|
|cookies|Variable used in the Cookie Support dimension.  Y: Enabled  N: Disabled  U: Unknown|char(1)|
|country|Numeric ID representing the country the hit came from. Adobe partners with Digital Envoy to match IP address to country. Uses country.tsv lookup.|smallint(5) unsigned|
|ct_connect_type|Related to the connection_type column. Most common values are LAN/Wifi, Mobile Carrier, and Modem.|varchar(20)|
|curr_factor|Determines the currency decimal place, and is used for currency conversion. For example, USD uses two decimal places, so this column value would be 2.|tinyint(4)|
|curr_rate|The exchange rate when the transaction occurred. Adobe partners with XE to determine the current day's exchange rate.|decimal(24,12)|
|currency|The currency code that was used during the transaction.|varchar(8)|
|cust_hit_time_gmt|Timestamp-enabled report suites only. The timestamp sent with the hit, based in Unix time.|int|
|cust_visid|If a custom visitor ID is set, it is populated in this column.|varchar(255)|
|daily_visitor|Flag to determine if the hit is a new daily visitor.|tinyint(3) unsigned|
|date_time|The time of the hit in readable format, based on the report suite's time zone.|datetime()|
|domain|Variable used in the Domain dimension. Based on the user's internet service provider (ISP).|varchar(100)|
|duplicate_events|Lists each event that was counted as a duplicate.|varchar(255)|
|duplicate_purchase|Flag indicating that the purchase event for this hit should be ignored because it is a duplicate.|tinyint(3) unsigned|
|duplicated_from|Only used in report suites containing hit copy VISTA rules. Indicates which report suite the hit was copied from.|varchar(40)|
|ef_id|The ef_id used in Adobe Advertising Cloud integrations.|varchar(255)|
|evar1-evar250|Custom variables 1-250. Each organization uses eVars differently. The best place for more information on how your organization populates respective eVars would be a solution design document specific to your organization.|varchar(255)|
|event_list|Comma-separated list of numeric IDs representing events triggered on the hit. Includes both default events and custom events 1-1000. Uses event.tsv lookup.|text|
|exclude_hit|Flag indicating the hit is excluded from reporting. The column visit_num is not incremented for excluded hits.  1,3: Exclusion based on user agent  2,4: Exclusion based on IP address  5: Hit did not have a value for page_url, pagename, page_event, or event_list  6: JavaScript escape value found in hit  7,8: Account-specific exclusion (such as in a VISTA rule)  9: Unused  10: Invalid currency code  11: Hit missing a timestamp on a timestamp-only report suite|tinyint(3) unsigned|
|first_hit_page_url|The very first URL of the visitor.|varchar(255)|
|first_hit_pagename|Variable used in the Entry Page Original dimension. The original entry page name of the visitor.|varchar(100)|
|first_hit_ref_domain|Variable used in the Original Referring Domain dimension. Based on first_hit_referrer. The very first referring domain of the visitor.|varchar(255)|
|first_hit_ref_type|Numeric ID representing the referrer type of the very first referrer of the visitor. Uses referrer_type.tsv lookup.|tinyint(3) unsigned|
|first_hit_referrer|The very first referring URL of the visitor.|varchar(255)|
|first_hit_time_gmt|Timestamp of the very first hit of the visitor in Unix time.|int(11)|
|geo_city|Name of the city the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to city.|varchar(32)|
|geo_country|Abbreviation of the country the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to country.|varchar(4)|
|geo_dma|Numeric ID of the demographic area the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to demographic area.|smallint(5) unsigned|
|geo_region|Name of the state or region the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to state/region.|varchar(32)|
|geo_zip|The zip code the came came from, based on IP. Adobe partners with Digital Envoy to match IP address to zip code.|varchar(16)|
|hier1-hier5|Used by hierarchy variables. Contains a delimited list of values. The delimiter is chosen under report suite settings.|varchar(255)|
|hit_source|Indicates what source the hit came from. <br>1: Standard image request without timestamp <br>2: Standard image request with timestamp <br>3: Live data source upload with timestamps <br>4: Not used <br>5: Generic data source upload <br>6: Full processing data source upload <br>7: TransactionID data source upload <br>8: No longer used; Previous versions of Adobe Advertising Cloud data sources <br>9: No longer used; Adobe Social summary metrics|tinyint|
|hit_time_gmt|The timestamp of the hit based in Unix time.|int(11)|
|hitid_high|Used in combination with hitid_low to uniquely identify a hit.|bigint(20) unsigned|
|hitid_low|Used in combination with hitid_high to uniquely identify a hit.|bigint(20) unsigned|
|homepage|No longer used. Indicated if the current URL is the browser's homepage.|char(1)|
|hourly_visitor|Flag to determine if the hit is a new hourly visitor.|tinyint(3) unsigned|
|ip|IP Address, based on the HTTP header of the image request.|varchar(20)|
|ip2|Not used. Backend reference variable for report suites containing VISTA rules based on IP address.|char(20)|
|j_jscript|Version of JavaScript supported by the browser.|varchar(5)|
|java_enabled|Flag indicating whether Java is enabled.  Y: Enabled  N: Disabled  U: Unknown|char(1)|
|javascript|Lookup ID of JavaScript version, based on j_jscript. Uses lookup table.|tinyint(3) unsigned|
|language|Numeric ID of language. Uses languages.tsv lookup table.|smallint(5) unsigned|
|last_hit_time_gmt|Timestamp (in Unix time) of the prior hit. Used to calculate the Days Since Last Visit dimension.|int(11)|
|last_purchase_num|Variable used in the Customer Loyalty dimension. Indicates the number of previous purchases the visitor has made.  0: No prior purchases (not a customer)  1: 1 prior purchase (new customer)  2: 2 prior purchases (return customer)  3: 3 or more prior purchases (loyal customer)|int(10) unsigned|
|last_purchase_time_gmt|Used in the Days Since Last Purchase dimension. Timestamp (in Unix time) of the last purchase made. For first-time purchases and visitors that have not made a purchase before, this value is 0.|int(11)|
|mc_audiences|List of Audience Manager segment IDs that the visitor belongs to.|text|
|mcvisid|Experience Cloud Visitor ID. 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits.|varchar(255)|
|mobile_id|If the visitor is using a mobile device, the numeric ID of the device.|int(15)|
|mobileaction|Mobile action. Automatically passed in when trackAction is called in the Mobile Services SDK. Allows for automatic action pathing in the app.|varchar(255)|
|mobileappid|Mobile app ID. Stores the application name and version in the following format:  [AppName] [BundleVersion]|varchar(255)|
|mobilecampaigncontent|Mobile campaign content|-|
|mobilecampaignmedium|Mobile campaign medium|-|
|mobilecampaignname|Mobile campaign name|-|
|mobilecampaignsource|Mobile campaign source|-|
|mobilecampaignterm|Mobile campaign term|-|
|mobiledayofweek|Number of the weekday that the app was launched on.|-|
|mobiledayssincefirstuse|Number of days since the app was run for the first time.|-|
|mobiledayssincelastuse|Number of days since the app was last run.|-|
|mobiledevice|Mobile device name. On iOS, it is stored as a comma-separated 2-digit string. The first number represents the device generation, and the second number represents the device family.|-|
|mobilehourofday|Defines the hour of the day the app was launched. Follows 24-hour numerical format.|-|
|mobileinstalldate|Mobile install date. Provides the date of the first time a user opens the mobile app.|-|
|mobilelaunchnumber|Increments by one each time the mobile app is launched.|-|
|mobileltv|Mobile lifetime value|-|
|mobilemessageid|Mobile message ID|-|
|mobilemessageonline|Mobile message online|-|
|mobileosversion|Mobile operating system version|-|
|mobilepushoptin|Indicates if a user has opted in for push messaging on the mobile app|-|
|mobilepushpayloadid|Identifier for a push message that has been clicked through by the user|-|
|mobileresolution|Resolution of the mobile device. Width x height in pixels.|-|
|monthly_visitor|Flag indicating the visitor is unique to the current month.|tinyint(3) unsigned|
|mvvar1-3|List variable values. Contains a delimited list of custom values depending on implementation.|text|
|namespace|Not used. Part of a scrapped feature many years ago.|varchar(50)|
|new_visit|Flag that determines if the current hit is a new visit. Set by Adobe servers after 30 minutes of visit inactivity.|tinyint(3) unsigned|
|os|Numeric ID representing the operating system of the visitor. Based on the user_agent column. Uses os lookup.|smallint(5) unsigned|
|p_plugins|No longer used. List of plugins available to the browser. Used the JavaScript function navigator.plugins().|text|
|page_event|The type of hit that is sent in the image request (standard hit, download link, custom link, exit link).|tinyint(3) unsigned|
|page_event_var1|Only used in link tracking image requests. The URL of the download link, exit link, or custom link clicked.|varchar(255)|
|page_event_var2|Only used in link tracking image requests. The custom name (if specified) of the link.|varchar(100)|
|page_event_var3|No longer used. Contained Survey and Media module data. Populated legacy video reports in previous versions of Adobe Analytics.|text|
|page_type|Used to populate the Pages Not Found dimension, used exclusively for 404 pages. This variable should either be empty or contain "ErrorPage".|varchar(20)|
|page_url|The URL of the hit. Not used in link tracking image requests.|varchar(255)|
|pagename|Used to populate the Pages dimension. If the pagename variable is empty, Analytics uses page_url instead.|varchar(100)|
|paid_search|Flag that is set if the hit matches paid search detection.|tinyint(3) unsigned|
|partner_plugins|Not used. Part of a scrapped feature many years ago.|varchar(255)|
|persistent_cookie|Used by the Persistent Cookie Support dimension. Indicates if the visitor supports cookies that are not discarded after each hit.|char(1)|
|plugins|No longer used. List of numeric ID's that correspond to plugins available within the browser. Uses plugins.tsv lookup.|varchar(180)|
|pointofinterest|Mobile services Point of interest|-|
|pointofinterestdistance|Mobile services Point of interest distance|-|
|post_ columns|Contains the value ultimately used in reports. Each post column is populated after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases.|See respective non-post column|
|prev_page|Not used. Adobe proprietary identifier of the previous page.|int(10) unsigned|
|product_list|Product list as passed in through the products variable. Products are delimited by commas while individual product properties are delimited by semicolons.|text|
|post_product_list|Product list as passed in through the products variable. Products are delimited by commas while individual product properties are delimited by semicolons.|mediumtext (16MB). Note: This field type (currently 'text') takes effect on January 7th, 2019.|
|product_merchandising|Not used. Use product_list instead.|None|
|prop1-prop75|Custom traffic variables 1-75.|varchar(100)|
|purchaseid|Unique identifier for a purchase, as set using the s_purchaseID variable. Used by the duplicate_purchase column.|varchar(20)|
|quarterly_visitor|Flag to determine if the hit is a new quarterly visitor.|tinyint(3) unsigned|
|ref_domain|Based on the referrer column. The referring domain of the hit.|varchar(100)|
|ref_type|A numeric ID representing the type of referral for the hit.<br>1: Inside your site<br>2: Other web sites <br>3: Search engines <br>4: Hard drive  <br>5: USENET <br>6: Typed/Bookmarked (no referrer) <br>7: Email <br>8: No JavaScript <br>9: Social Networks|tinyint(3) unsigned|
|referrer|Page URL of the previous page.|varchar(255)|
|resolution|Numeric ID representing the resolution of the monitor. Populates the Monitor Resolution dimension. Uses resolution.tsv lookup table.|smallint(5) unsigned|
|s_kwcid|Used in Adobe Advertising Cloud integrations.|varchar(255)|
|s_resolution|Raw screen resolution value. Gathered using the JavaScript function screen.width x screen.height.|varchar(20)|
|sampled_hit|No longer used. Was formerly used for sampling in Ad Hoc Analysis.|char(1)|
|search_engine|Numeric ID representing the Search Engine that referred the visitor to your site. Uses search_engines.tsv lookup.|smallint(5) unsigned|
|search_page_num|Used by the All Search Page Rank dimension. Indicates which page of search results your site appeared on before the user clicked through to your site.|smallint(5) unsigned|
|secondary_hit|Flag that tracks secondary hits. Normally originates from multi-suite tagging and VISTA rules that copy hits.|tinyint(3) unsigned|
|service|Not used. Use page_event instead.|char(2)|
|socialaccountandappids|No longer used. Social account and app ID's|-|
|socialassettrackingcode|No longer used. Social campaign variable|-|
|socialauthor|No longer used. Social Authors variable|-|
|socialaveragesentiment|No longer used. Social average sentiment|-|
|socialcontentprovider|No longer used. Social Platforms/Properties|-|
|socialfbstories|No longer used. Facebook interactions|-|
|socialfbstorytellers|No longer used. People talking about this|-|
|socialinteractioncount|No longer used. Social interaction count|-|
|socialinteractiontype|No longer used. Social interaction type|-|
|sociallanguage|No longer used. Social language|-|
|sociallatlong|No longer used. Social Latitude/Longitude|-|
|sociallikeadds|No longer used. Social Like adds|-|
|sociallink|No longer used. Social links|-|
|socialmentions|No longer used. Social mentions|-|
|socialowneddefinitioninsighttype|No longer used. Social owned definition insight type|-|
|socialowneddefinitioninsightvalue|No longer used. Social owned definition insight value|-|
|socialowneddefinitionmetric|No longer used. Social owned definition metric|-|
|socialowneddefinitionpropertyvspost|No longer used. Social owned definition property vs. post|-|
|socialownedpostids|No longer used. Social owned post ID's|-|
|socialownedpropertyid|No longer used. Social owned property ID|-|
|socialownedpropertyname|No longer used. Social owned property name|-|
|socialownedpropertypropertyvsapp|No longer used. Social owned property vs app|-|
|socialpageviews|No longer used. Social property views|-|
|socialpostviews|No longer used. Social post views|-|
|socialproperty|No longer used. Social property|-|
|socialpubcomments|No longer used. Social public comments|-|
|socialpubposts|No longer used. Social public posts|-|
|socialpubrecommends|No longer used. Social public recommends|-|
|socialpubsubscribers|No longer used. Social public subscribers|-|
|socialterm|No longer used. Hashed value of the social listening query|-|
|socialtermslist|No longer used. Social list of terms|-|
|socialtotalsentiment|No longer used. Social total sentiment|-|
|sourceid|Not used. Adobe proprietary column info|int|
|state|State variable.|varchar(50)|
|stats_server|Not of use. Adobe internal server that processed the hit.|varchar(30)|
|t_time_info|Local time for the visitor. Format is as follows:  M/D/YYYY  HH:MM:SS  Month (0-11, 0=January)  Timezone offset (in minutes)|varchar(100)|
|tnt|Used in Adobe Target integrations.|text|
|tnt_action|Used in Adobe Target integrations.|text|
|tnt_post_vista|No longer used. Use post_tnt instead.|text|
|transactionid|A unique identifier where various data points can be uploaded later via data sources.|varchar(100)|
|truncated_hit|A flag indicating that the image request was truncated. Indicates that a partial hit was received.  Y: Hit was truncated; partial hit received  N: Hit was not truncated; full hit received|char(1)|
|ua_color|No longer used. Formerly used as a fallback for color depth.|varchar(20)|
|ua_os|No longer used. Formerly used as a fallback for operating system.|varchar(80)|
|ua_pixels|No longer used. Formerly used as a fallback for browser height and width.|varchar(20)|
|user_agent|User agent string sent in the HTTP header of the image request.|text|
|user_hash|Not of use. Hash on the report suite ID. Use username instead.|int(10) unsigned|
|user_server|Variable used in the Server dimension.|varchar(100)|
|userid|Not of use. The numeric ID for the report suite ID. Use username instead.|int(10) unsigned|
|username|The report suite ID for the hit.|varchar(40)|
|va_closer_detail|Variable used in the Last Touch Detail dimension.|varchar(255)|
|va_closer_id|Numeric ID that identifies the Last Touch Channel dimension. Lookup for this ID can be found in the Marketing Channel Manager.|tinyint unsigned|
|va_finder_detail|Variable used in the First Touch Detail dimension.|varchar(255)|
|va_finder_id|Numeric ID that identifies the First Touch Channel dimension. Lookup for this ID can be found in the Marketing Channel Manager.|tinyint unsigned|
|va_instance_event|Flag to identify Marketing Channel instances. Used by the Marketing Channel Last Touch Instances metric.|tinyint unsigned|
|va_new_engagement|Flag to identify Marketing Channel new engagements. Used by the New Engagements metric.|tinyint unsigned|
|video|Video name|-|
|videoad|Video Ad name|-|
|videoadinpod|Video Ad in pod position|-|
|videoadlength|Video Ad length|-|
|videoadname|Video Ad name|-|
|videoadplayername|Video Ad player name|-|
|videoadpod|Video Ad pod|-|
|videochannel|Video Channel|-|
|videochapter|Video Chapter name|-|
|videocontenttype|Video Content type. Set to 'Video' automatically for all video views|-|
|videolength|Video length|-|
|videoname|Video name|-|
|videopath|Video path|-|
|videoplayername|Video player name|-|
|videoqoebitrateaverageevar|Video quality average bit rate|-|
|videoqoebitratechangecountevar|Video quality change count|-|
|videoqoebuffercountevar|Video quality buffer count|-|
|videoqoebuffertimeevar|Video quality buff time|-|
|videoqoedroppedframecountevar|Video quality dropped frame count|-|
|videoqoeerrorcountevar|Video quality error count|-|
|videoqoetimetostartevar|Video quality time to start|-|
|videosegment|Video segment|-|
|visid_high|Used in combination with visid_low to uniquely identify a visit.|bigint(20) unsigned|
|visid_low|Used in combination with visid_high to uniquely identify a visit.|bigint(20) unsigned|
|visid_new|Flag to identify if the hit contains a newly generated visitor ID.|char(1)|
|visid_timestamp|If visitor ID was newly generated, provides the timestamp (in Unix time) of when the visitor ID was generated.|int(11)|
|visid_type|Numeric ID representing what method was used to identify the visitor.  0: Custom visitorID  1: IP and user agent fallback  2: HTTP Mobile Subscriber Header  3: Legacy cookie value (s_vi)  4: Fallback cookie value (s_fid)  5: Experience Cloud ID Service|tinyint(3) unsigned|
|visit_keywords|Variable used in the Search Keyword dimension.|varchar(255)|
|visit_num|Variable used in the Visit Number dimension. Starts at 1, and increments each time a new visit starts per visitor.|int(10) unsigned|
|visit_page_num|Variable used in the Hit Depth dimension. Increases by 1 for each hit the user generates. Resets each visit.|int(10) unsigned|
|visit_ref_domain|Based on the visit_referrer column. The first referring domain of the visit.|varchar(100)|
|visit_ref_type|Numeric ID representing the referrer type of the first referrer of the visit. Uses the referrer_type.tsv lookup table.|tinyint(3) unsigned|
|visit_referrer|The first referrer of the visit.|varchar(255)|
|visit_search_engine|Numeric ID of the first search engine of the visit. Uses the search_engines.tsv lookup table.|smallint(5) unsigned|
|visit_start_page_url|The first URL of the visit.|varchar(255)|
|visit_start_pagename|The first Page Name of the visit.|varchar(100)|
|visit_start_time_gmt|Timestamp (in Unix time) of the first hit of the visit.|int(11)|
|weekly_visitor|Flag to determine if the hit is a new weekly visitor.|tinyint(3) unsigned|
|yearly_visitor|Flag to determine if the hit is a new yearly visitor.|tinyint(3) unsigned|
|zip|Used to populate the Zip Code dimension.|varchar(50)|
