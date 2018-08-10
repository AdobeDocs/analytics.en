---
description: Table data describing the columns in the data feed.
keywords: Data Feed;columns
seo-description: Table data describing the columns in the data feed.
seo-title: Data Column Reference
solution: Analytics
subtopic: data feeds
title: Data Column Reference
topic: Reports and analytics
uuid: 4ae91e47-2a1a-44fc-b54c-d016cd31db50
index: y
internal: n
snippet: y
translate: y
---

# Data Column Reference



>>[!NOTE]
>>
>>For any given column (for instance, one that is defined as 255 characters), a data feed may send additional characters due to the addition of characters escaping values in a string.
>

><!-- <p> See email from matt on 4/14. [Luby] For visitors that visited prior to the implementation of the Experience Cloud ID Service and haven't cleared cookies the pre and post visid_high/low will be based on the legacy Analytics Visitor ID/s_vi the visitor already had assigned. </p> 
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
<p> [Luby] They should use the post_visid_type column and that page looks correct. </p> -->

## Columns, Descriptions, and Data Types {#section_A8C63FCDA046483DA3B2082856D11839}


>[!NOTE]
>
>Most columns contain a similar column with a prefix of ` post_`. Post columns contain values after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases. 


<table id="table_DF8310EF8FF14D26844E789E4B31822A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Column name </th> 
   <th colname="col2" class="entry"> Column description </th> 
   <th colname="col3" class="entry"> Data type </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> accept_language </td> 
   <td> Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> aemassetid </td> 
   <td> A multi-value variable corresponding to Asset ID's (GUID's) of a set of Adobe Experience Manager Assets. Increments Impression Events. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> aemassetsource </td> 
   <td> Identifies the source of the asset event. Used in Adobe Experience Manager. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> aemclickedassetid </td> 
   <td> Asset ID of an Adobe Experience Manager asset. Increments Click Events. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> browser </td> 
   <td> Numeric ID of the browser. References the browser.tsv lookup table. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> browser_height </td> 
   <td> Height in pixels of the browser window. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> browser_width </td> 
   <td> Width in pixels of the browser window. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> c_color </td> 
   <td> Bit depth of the color palette. Used as part of calculating the Color Depth dimension. Uses the JavaScript function screen.colorDepth(). </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> campaign </td> 
   <td> Variable used in the Tracking Code dimension. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> carrier </td> 
   <td> Adobe Advertising Cloud integration variable. Specifies the mobile carrier. References the carrier lookup table. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> channel </td> 
   <td> Variable used in the Site Sections dimension. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> click_action </td> 
   <td> No longer used. Address of linked clicked in the legacy Clickmap tool. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> click_action_type </td> 
   <td> <p>No longer used. Link type of the legacy Clickmap tool.</p> <p>0: HREF URL</p> <p>1: Custom ID</p> <p>2: JavaScript onClick event</p> <p>3: Form element</p> </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> click_context </td> 
   <td> No longer used. Page name where the link click occurred. Part of the legacy Clickmap tool. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> click_context_type </td> 
   <td> <p>No longer used. Indicates if click_context had a page name or defaulted to page URL.</p> <p>0: Page URL</p> <p>1: Page Name</p> </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> click_sourceid </td> 
   <td> No longer used. Numeric ID for the location on the page of the clicked link. Part of the legacy Clickmap tool. </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> click_tag </td> 
   <td> No longer used. Type of HTML element that was clicked. </td> 
   <td> varchar(10) </td> 
  </tr> 
  <tr> 
   <td> code_ver </td> 
   <td> AppMeasurement Library version used to compile and send the image request. </td> 
   <td> varchar(16) </td> 
  </tr> 
  <tr> 
   <td> color </td> 
   <td> Color depth ID based on the value of the c_color column. References the color_depth.tsv lookup table. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> connection_type </td> 
   <td> Numeric ID representing the connection type. Variable used in the Connection Type dimension. References the connection_type.tsv lookup table. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> cookies </td> 
   <td> <p>Variable used in the Cookie Support dimension.</p> <p>Y: Enabled</p> <p>N: Disabled</p> <p>U: Unknown</p> </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> country </td> 
   <td> Numeric ID representing the country the hit came from. Adobe partners with Digital Envoy to match IP address to country. Uses country.tsv lookup. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> ct_connect_type </td> 
   <td> Related to the connection_type column. Most common values are LAN/Wifi, Mobile Carrier, and Modem. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> curr_factor </td> 
   <td> Determines the currency decimal place, and is used for currency conversion. For example, USD uses two decimal places, so this column value would be 2. </td> 
   <td> tinyint(4) </td> 
  </tr> 
  <tr> 
   <td> curr_rate </td> 
   <td> The exchange rate when the transaction occurred. Adobe partners with XE to determine the current day's exchange rate. </td> 
   <td> decimal(24,12) </td> 
  </tr> 
  <tr> 
   <td> currency </td> 
   <td> The currency code that was used during the transaction. </td> 
   <td> varchar(8) </td> 
  </tr> 
  <tr> 
   <td> cust_hit_time_gmt </td> 
   <td> Timestamp-enabled report suites only. The timestamp sent with the hit, based in Unix time. </td> 
   <td> int </td> 
  </tr> 
  <tr> 
   <td> cust_visid </td> 
   <td> If a custom visitor ID is set, it is populated in this column. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> daily_visitor </td> 
   <td> Flag to determine if the hit is a new daily visitor. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> date_time </td> 
   <td> The time of the hit in readable format, based on the report suite's time zone. </td> 
   <td> datetime() </td> 
  </tr> 
  <tr> 
   <td> domain </td> 
   <td> Variable used in the Domain dimension. Based on the user's internet service provider (ISP). </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> duplicate_events </td> 
   <td> Lists each event that was counted as a duplicate. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> duplicate_purchase </td> 
   <td> Flag indicating that the purchase event for this hit should be ignored because it is a duplicate. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> duplicated_from </td> 
   <td> Only used in report suites containing hit copy VISTA rules. Indicates which report suite the hit was copied from. </td> 
   <td> varchar(40) </td> 
  </tr> 
  <tr> 
   <td> ef_id </td> 
   <td> The ef_id used in Adobe Advertising Cloud integrations. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> evar1-evar250 </td> 
   <td> Custom variables 1-250. Each organization uses eVars differently. The best place for more information on how your organization populates respective eVars would be a solution design document specific to your organization. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> event_list </td> 
   <td> Comma-separated list of numeric IDs representing events triggered on the hit. Includes both default events and custom events 1-1000. Uses event.tsv lookup. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> exclude_hit </td> 
   <td> <p>Flag indicating the hit is excluded from reporting. The column visit_num is not incremented for excluded hits.</p> <p>1,3: Exclusion based on user agent</p> <p>2,4: Exclusion based on IP address</p> <p>5: Hit did not have a value for page_url, pagename, page_event, or event_list</p> <p>6: JavaScript escape value found in hit</p> <p>7,8: Account-specific exclusion (such as in a VISTA rule)</p> <p>9: Unused</p> <p>10: Invalid currency code</p> <p>11: Hit missing a timestamp on a timestamp-only report suite</p> </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> first_hit_page_url </td> 
   <td> The very first URL of the visitor. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> first_hit_pagename </td> 
   <td> Variable used in the Entry Page Original dimension. The original entry page name of the visitor. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> first_hit_ref_domain </td> 
   <td> Variable used in the Original Referring Domain dimension. Based on first_hit_referrer. The very first referring domain of the visitor. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> first_hit_ref_type </td> 
   <td> Numeric ID representing the referrer type of the very first referrer of the visitor. Uses referrer_type.tsv lookup. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> first_hit_referrer </td> 
   <td> The very first referring URL of the visitor. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> first_hit_time_gmt </td> 
   <td> Timestamp of the very first hit of the visitor in Unix time. </td> 
   <td> int(11) </td> 
  </tr> 
  <tr> 
   <td> geo_city </td> 
   <td> Name of the city the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to city. </td> 
   <td> varchar(32) </td> 
  </tr> 
  <tr> 
   <td> geo_country </td> 
   <td> Abbreviation of the country the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to country. </td> 
   <td> varchar(4) </td> 
  </tr> 
  <tr> 
   <td> geo_dma </td> 
   <td> Numeric ID of the demographic area the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to demographic area. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> geo_region </td> 
   <td> Name of the state or region the hit came from, based on IP. Adobe partners with Digital Envoy to match IP address to state/region. </td> 
   <td> varchar(32) </td> 
  </tr> 
  <tr> 
   <td> geo_zip </td> 
   <td> The zip code the came came from, based on IP. Adobe partners with Digital Envoy to match IP address to zip code. </td> 
   <td> varchar(16) </td> 
  </tr> 
  <tr> 
   <td> hier1-hier5 </td> 
   <td> Used by hierarchy variables. Contains a delimited list of values. The delimiter is chosen under report suite settings. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> hit_source </td> 
   <td> <p>Indicates what source the hit came from.</p> <p>1: Standard image request without timestamp</p> <p>2: Standard image request with timestamp</p> <p>3: Live data source upload with timestamps</p> <p>4: Not used</p> <p>5: Generic data source upload</p> <p>6: Full processing data source upload</p> <p>7: TransactionID data source upload</p> <p>8: No longer used; Previous versions of Adobe Advertising Cloud data sources</p> <p>9: No longer used; Adobe Social summary metrics</p> </td> 
   <td> tinyint </td> 
  </tr> 
  <tr> 
   <td> hit_time_gmt </td> 
   <td> The timestamp of the hit based in Unix time. </td> 
   <td> int(11) </td> 
  </tr> 
  <tr> 
   <td> hitid_high </td> 
   <td> Used in combination with hitid_low to uniquely identify a hit. </td> 
   <td> bigint(20) unsigned </td> 
  </tr> 
  <tr> 
   <td> hitid_low </td> 
   <td> Used in combination with hitid_high to uniquely identify a hit. </td> 
   <td> bigint(20) unsigned </td> 
  </tr> 
  <tr> 
   <td> homepage </td> 
   <td> No longer used. Indicated if the current URL is the browser's homepage. </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> hourly_visitor </td> 
   <td> Flag to determine if the hit is a new hourly visitor. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> ip </td> 
   <td> IP Address, based on the HTTP header of the image request. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> ip2 </td> 
   <td> Not used. Backend reference variable for report suites containing VISTA rules based on IP address. </td> 
   <td> char(20) </td> 
  </tr> 
  <tr> 
   <td> j_jscript </td> 
   <td> Version of JavaScript supported by the browser. </td> 
   <td> varchar(5) </td> 
  </tr> 
  <tr> 
   <td> java_enabled </td> 
   <td> <p>Flag indicating whether Java is enabled.</p> <p>Y: Enabled </p> <p>N: Disabled</p> <p>U: Unknown</p> </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> javascript </td> 
   <td> Lookup ID of JavaScript version, based on j_jscript. Uses lookup table. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> language </td> 
   <td> Numeric ID of language. Uses languages.tsv lookup table. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> last_hit_time_gmt </td> 
   <td> Timestamp (in Unix time) of the prior hit. Used to calculate the Days Since Last Visit dimension. </td> 
   <td> int(11) </td> 
  </tr> 
  <tr> 
   <td> last_purchase_num </td> 
   <td> <p>Variable used in the Customer Loyalty dimension. Indicates the number of previous purchases the visitor has made.</p> <p>0: No prior purchases (not a customer)</p> <p>1: 1 prior purchase (new customer)</p> <p>2: 2 prior purchases (return customer)</p> <p>3: 3 or more prior purchases (loyal customer)</p> </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> last_purchase_time_gmt </td> 
   <td> Used in the Days Since Last Purchase dimension. Timestamp (in Unix time) of the last purchase made. For first-time purchases and visitors that have not made a purchase before, this value is 0. </td> 
   <td> int(11) </td> 
  </tr> 
  <tr> 
   <td> mc_audiences </td> 
   <td> List of Audience Manager segment IDs that the visitor belongs to. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> mcvisid </td> 
   <td> Experience Cloud Visitor ID. 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> mobile_id </td> 
   <td> If the visitor is using a mobile device, the numeric ID of the device. </td> 
   <td> int(15) </td> 
  </tr> 
  <tr> 
   <td> mobileaction </td> 
   <td> Mobile action. Automatically passed in when trackAction is called in the Mobile Services SDK. Allows for automatic action pathing in the app. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> mobileappid </td> 
   <td> <p>Mobile app ID. Stores the application name and version in the following format:</p> <p>[AppName] [BundleVersion]</p> </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> mobilecampaigncontent </td> 
   <td> Mobile campaign content </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilecampaignmedium </td> 
   <td> Mobile campaign medium </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilecampaignname </td> 
   <td> Mobile campaign name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilecampaignsource </td> 
   <td> Mobile campaign source </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilecampaignterm </td> 
   <td> Mobile campaign term </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobiledayofweek </td> 
   <td> Number of the weekday that the app was launched on. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobiledayssincefirstuse </td> 
   <td> Number of days since the app was run for the first time. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobiledayssincelastuse </td> 
   <td> Number of days since the app was last run. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobiledevice </td> 
   <td> Mobile device name. On iOS, it is stored as a comma-separated 2-digit string. The first number represents the device generation, and the second number represents the device family. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilehourofday </td> 
   <td> Defines the hour of the day the app was launched. Follows 24-hour numerical format. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobileinstalldate </td> 
   <td> Mobile install date. Provides the date of the first time a user opens the mobile app. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilelaunchnumber </td> 
   <td> Increments by one each time the mobile app is launched. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobileltv </td> 
   <td> Mobile lifetime value </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilemessageid </td> 
   <td> Mobile message ID </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilemessageonline </td> 
   <td> Mobile message online </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobileosversion </td> 
   <td> Mobile operating system version </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilepushoptin </td> 
   <td> Indicates if a user has opted in for push messaging on the mobile app </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobilepushpayloadid </td> 
   <td> Identifier for a push message that has been clicked through by the user </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> mobileresolution </td> 
   <td> Resolution of the mobile device. Width x height in pixels. </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> monthly_visitor </td> 
   <td> Flag indicating the visitor is unique to the current month. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> mvvar1-3 </td> 
   <td> List variable values. Contains a delimited list of custom values depending on implementation. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> namespace </td> 
   <td> Not used. Part of a scrapped feature many years ago. </td> 
   <td> varchar(50) </td> 
  </tr> 
  <tr> 
   <td> new_visit </td> 
   <td> Flag that determines if the current hit is a new visit. Set by Adobe servers after 30 minutes of visit inactivity. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> os </td> 
   <td> Numeric ID representing the operating system of the visitor. Based on the user_agent column. Uses os lookup. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> p_plugins </td> 
   <td> No longer used. List of plugins available to the browser. Used the JavaScript function navigator.plugins(). </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> page_event </td> 
   <td> The type of hit that is sent in the image request (standard hit, download link, custom link, exit link). </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> page_event_var1 </td> 
   <td> Only used in link tracking image requests. The URL of the download link, exit link, or custom link clicked. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> page_event_var2 </td> 
   <td> Only used in link tracking image requests. The custom name (if specified) of the link. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> page_event_var3 </td> 
   <td> No longer used. Contained Survey and Media module data. Populated legacy video reports in previous versions of Adobe Analytics. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> page_type </td> 
   <td> Used to populate the Pages Not Found dimension, used exclusively for 404 pages. This variable should either be empty or contain "ErrorPage". </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> page_url </td> 
   <td> The URL of the hit. Not used in link tracking image requests. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> pagename </td> 
   <td> Used to populate the Pages dimension. If the pagename variable is empty, Analytics uses page_url instead. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> paid_search </td> 
   <td> Flag that is set if the hit matches paid search detection. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> partner_plugins </td> 
   <td> Not used. Part of a scrapped feature many years ago. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> persistent_cookie </td> 
   <td> Used by the Persistent Cookie Support dimension. Indicates if the visitor supports cookies that are not discarded after each hit. </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> plugins </td> 
   <td> No longer used. List of numeric ID's that correspond to plugins available within the browser. Uses plugins.tsv lookup. </td> 
   <td> varchar(180) </td> 
  </tr> 
  <tr> 
   <td> pointofinterest </td> 
   <td> Mobile services Point of interest </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> pointofinterestdistance </td> 
   <td> Mobile services Point of interest distance </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> post_ columns </td> 
   <td> Contains the value ultimately used in reports. Each post column is populated after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases. </td> 
   <td> See respective non-post column </td> 
  </tr> 
  <tr> 
   <td> prev_page </td> 
   <td> Not used. Adobe proprietary identifier of the previous page. </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> product_list </td> 
   <td> Product list as passed in through the products variable. Products are delimited by commas while individual product properties are delimited by semicolons. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> product_merchandising </td> 
   <td> Not used. Use product_list instead. </td> 
   <td> None </td> 
  </tr> 
  <tr> 
   <td> prop1-prop75 </td> 
   <td> Custom traffic variables 1-75. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> purchaseid </td> 
   <td> Unique identifier for a purchase, as set using the s_purchaseID variable. Used by the duplicate_purchase column. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> quarterly_visitor </td> 
   <td> Flag to determine if the hit is a new quarterly visitor. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> ref_domain </td> 
   <td> Based on the referrer column. The referring domain of the hit. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> ref_type </td> 
   <td> <p>A numeric ID representing the type of referral for the hit.</p> <p>1: Inside your site</p> <p>2: Other web sites</p> <p>3: Search engines</p> <p>4: Hard drive</p> <p>5: USENET</p> <p>6: Typed/Bookmarked (no referrer)</p> <p>7: Email</p> <p>8: No JavaScript</p> <p>9: Social Networks</p> </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> referrer </td> 
   <td> Page URL of the previous page. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> resolution </td> 
   <td> Numeric ID representing the resolution of the monitor. Populates the Monitor Resolution dimension. Uses resolution.tsv lookup table. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> s_kwcid </td> 
   <td> Used in Adobe Advertising Cloud integrations. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> s_resolution </td> 
   <td> Raw screen resolution value. Gathered using the JavaScript function screen.width x screen.height. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> sampled_hit </td> 
   <td> No longer used. Was formerly used for sampling in Ad Hoc Analysis. </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> search_engine </td> 
   <td> Numeric ID representing the Search Engine that referred the visitor to your site. Uses search_engines.tsv lookup. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> search_page_num </td> 
   <td> Used by the All Search Page Rank dimension. Indicates which page of search results your site appeared on before the user clicked through to your site. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> secondary_hit </td> 
   <td> Flag that tracks secondary hits. Normally originates from multi-suite tagging and VISTA rules that copy hits. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> service </td> 
   <td> Not used. Use page_event instead. </td> 
   <td> char(2) </td> 
  </tr> 
  <tr> 
   <td> socialaccountandappids </td> 
   <td> No longer used. Social account and app ID's </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialassettrackingcode </td> 
   <td> No longer used. Social campaign variable </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialauthor </td> 
   <td> No longer used. Social Authors variable </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialaveragesentiment </td> 
   <td> No longer used. Social average sentiment </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialcontentprovider </td> 
   <td> No longer used. Social Platforms/Properties </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialfbstories </td> 
   <td> No longer used. Facebook interactions </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialfbstorytellers </td> 
   <td> No longer used. People talking about this </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialinteractioncount </td> 
   <td> No longer used. Social interaction count </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialinteractiontype </td> 
   <td> No longer used. Social interaction type </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> sociallanguage </td> 
   <td> No longer used. Social language </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> sociallatlong </td> 
   <td> No longer used. Social Latitude/Longitude </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> sociallikeadds </td> 
   <td> No longer used. Social Like adds </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> sociallink </td> 
   <td> No longer used. Social links </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialmentions </td> 
   <td> No longer used. Social mentions </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialowneddefinitioninsighttype </td> 
   <td> No longer used. Social owned definition insight type </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialowneddefinitioninsightvalue </td> 
   <td> No longer used. Social owned definition insight value </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialowneddefinitionmetric </td> 
   <td> No longer used. Social owned definition metric </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialowneddefinitionpropertyvspost </td> 
   <td> No longer used. Social owned definition property vs. post </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialownedpostids </td> 
   <td> No longer used. Social owned post ID's </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialownedpropertyid </td> 
   <td> No longer used. Social owned property ID </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialownedpropertyname </td> 
   <td> No longer used. Social owned property name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialownedpropertypropertyvsapp </td> 
   <td> No longer used. Social owned property vs app </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialpageviews </td> 
   <td> No longer used. Social property views </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialpostviews </td> 
   <td> No longer used. Social post views </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialproperty </td> 
   <td> No longer used. Social property </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialpubcomments </td> 
   <td> No longer used. Social public comments </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialpubposts </td> 
   <td> No longer used. Social public posts </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialpubrecommends </td> 
   <td> No longer used. Social public recommends </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialpubsubscribers </td> 
   <td> No longer used. Social public subscribers </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialterm </td> 
   <td> No longer used. Hashed value of the social listening query </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialtermslist </td> 
   <td> No longer used. Social list of terms </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> socialtotalsentiment </td> 
   <td> No longer used. Social total sentiment </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> sourceid </td> 
   <td> Not used. Adobe proprietary column info </td> 
   <td> int </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> State variable. </td> 
   <td> varchar(50) </td> 
  </tr> 
  <tr> 
   <td> stats_server </td> 
   <td> Not of use. Adobe internal server that processed the hit. </td> 
   <td> varchar(30) </td> 
  </tr> 
  <tr> 
   <td> t_time_info </td> 
   <td> <p>Local time for the visitor. Format is as follows:</p> <p>M/D/YYYY</p> <p>HH:MM:SS</p> <p>Month (0-11, 0=January)</p> <p>Timezone offset (in minutes)</p> </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> tnt </td> 
   <td> Used in Adobe Target integrations. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> tnt_action </td> 
   <td> Used in Adobe Target integrations. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> tnt_post_vista </td> 
   <td> No longer used. Use post_tnt instead. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> transactionid </td> 
   <td> A unique identifier where various data points can be uploaded later via data sources. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> truncated_hit </td> 
   <td> <p>A flag indicating that the image request was truncated. Indicates that a partial hit was received.</p> <p>Y: Hit was truncated; partial hit received</p> <p>N: Hit was not truncated; full hit received</p> </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> ua_color </td> 
   <td> No longer used. Formerly used as a fallback for color depth. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> ua_os </td> 
   <td> No longer used. Formerly used as a fallback for operating system. </td> 
   <td> varchar(80) </td> 
  </tr> 
  <tr> 
   <td> ua_pixels </td> 
   <td> No longer used. Formerly used as a fallback for browser height and width. </td> 
   <td> varchar(20) </td> 
  </tr> 
  <tr> 
   <td> user_agent </td> 
   <td> User agent string sent in the HTTP header of the image request. </td> 
   <td> text </td> 
  </tr> 
  <tr> 
   <td> user_hash </td> 
   <td> Not of use. Hash on the report suite ID. Use username instead. </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> user_server </td> 
   <td> Variable used in the Server dimension. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> userid </td> 
   <td> Not of use. The numeric ID for the report suite ID. Use username instead. </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> username </td> 
   <td> The report suite ID for the hit. </td> 
   <td> varchar(40) </td> 
  </tr> 
  <tr> 
   <td> va_closer_detail </td> 
   <td> Variable used in the Last Touch Detail dimension. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> va_closer_id </td> 
   <td> Numeric ID that identifies the Last Touch Channel dimension. Lookup for this ID can be found in the Marketing Channel Manager. </td> 
   <td> tinyint unsigned </td> 
  </tr> 
  <tr> 
   <td> va_finder_detail </td> 
   <td> Variable used in the First Touch Detail dimension. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> va_finder_id </td> 
   <td> Numeric ID that identifies the First Touch Channel dimension. Lookup for this ID can be found in the Marketing Channel Manager. </td> 
   <td> tinyint unsigned </td> 
  </tr> 
  <tr> 
   <td> va_instance_event </td> 
   <td> Flag to identify Marketing Channel instances. Used by the Marketing Channel Last Touch Instances metric. </td> 
   <td> tinyint unsigned </td> 
  </tr> 
  <tr> 
   <td> va_new_engagement </td> 
   <td> Flag to identify Marketing Channel new engagements. Used by the New Engagements metric. </td> 
   <td> tinyint unsigned </td> 
  </tr> 
  <tr> 
   <td> video </td> 
   <td> Video name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoad </td> 
   <td> Video Ad name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoadinpod </td> 
   <td> Video Ad in pod position </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoadlength </td> 
   <td> Video Ad length </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoadname </td> 
   <td> Video Ad name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoadplayername </td> 
   <td> Video Ad player name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoadpod </td> 
   <td> Video Ad pod </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videochannel </td> 
   <td> Video Channel </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videochapter </td> 
   <td> Video Chapter name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videocontenttype </td> 
   <td> Video Content type. Set to 'Video' automatically for all video views </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videolength </td> 
   <td> Video length </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoname </td> 
   <td> Video name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videopath </td> 
   <td> Video path </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoplayername </td> 
   <td> Video player name </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoebitrateaverageevar </td> 
   <td> Video quality average bit rate </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoebitratechangecountevar </td> 
   <td> Video quality change count </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoebuffercountevar </td> 
   <td> Video quality buffer count </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoebuffertimeevar </td> 
   <td> Video quality buff time </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoedroppedframecountevar </td> 
   <td> Video quality dropped frame count </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoeerrorcountevar </td> 
   <td> Video quality error count </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videoqoetimetostartevar </td> 
   <td> Video quality time to start </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> videosegment </td> 
   <td> Video segment </td> 
   <td> - </td> 
  </tr> 
  <tr> 
   <td> visid_high </td> 
   <td> Used in combination with visid_low to uniquely identify a visit. </td> 
   <td> bigint(20) unsigned </td> 
  </tr> 
  <tr> 
   <td> visid_low </td> 
   <td> Used in combination with visid_high to uniquely identify a visit. </td> 
   <td> bigint(20) unsigned </td> 
  </tr> 
  <tr> 
   <td> visid_new </td> 
   <td> Flag to identify if the hit contains a newly generated visitor ID. </td> 
   <td> char(1) </td> 
  </tr> 
  <tr> 
   <td> visid_timestamp </td> 
   <td> If visitor ID was newly generated, provides the timestamp (in Unix time) of when the visitor ID was generated. </td> 
   <td> int(11) </td> 
  </tr> 
  <tr> 
   <td> visid_type </td> 
   <td> <p>Numeric ID representing what method was used to identify the visitor.</p> <p>0: Custom visitorID</p> <p>1: IP and user agent fallback</p> <p>2: HTTP Mobile Subscriber Header</p> <p>3: Legacy cookie value (s_vi)</p> <p>4: Fallback cookie value (s_fid)</p> <p>5: Experience Cloud ID Service</p> </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> visit_keywords </td> 
   <td> Variable used in the Search Keyword dimension. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> visit_num </td> 
   <td> Variable used in the Visit Number dimension. Starts at 1, and increments each time a new visit starts per visitor. </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> visit_page_num </td> 
   <td> Variable used in the Hit Depth dimension. Increases by 1 for each hit the user generates. Resets each visit. </td> 
   <td> int(10) unsigned </td> 
  </tr> 
  <tr> 
   <td> visit_ref_domain </td> 
   <td> Based on the visit_referrer column. The first referring domain of the visit. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> visit_ref_type </td> 
   <td> Numeric ID representing the referrer type of the first referrer of the visit. Uses the referrer_type.tsv lookup table. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> visit_referrer </td> 
   <td> The first referrer of the visit. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> visit_search_engine </td> 
   <td> Numeric ID of the first search engine of the visit. Uses the search_engines.tsv lookup table. </td> 
   <td> smallint(5) unsigned </td> 
  </tr> 
  <tr> 
   <td> visit_start_page_url </td> 
   <td> The first URL of the visit. </td> 
   <td> varchar(255) </td> 
  </tr> 
  <tr> 
   <td> visit_start_pagename </td> 
   <td> The first Page Name of the visit. </td> 
   <td> varchar(100) </td> 
  </tr> 
  <tr> 
   <td> visit_start_time_gmt </td> 
   <td> Timestamp (in Unix time) of the first hit of the visit. </td> 
   <td> int(11) </td> 
  </tr> 
  <tr> 
   <td> weekly_visitor </td> 
   <td> Flag to determine if the hit is a new weekly visitor. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> yearly_visitor </td> 
   <td> Flag to determine if the hit is a new yearly visitor. </td> 
   <td> tinyint(3) unsigned </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> Used to populate the Zip Code dimension. </td> 
   <td> varchar(50) </td> 
  </tr> 
 </tbody> 
</table>

