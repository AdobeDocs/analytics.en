---
description: Frequently asked questions about implementation, and links to more information.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
seo-description: Frequently asked questions about implementation, and links to more information.
seo-title: FAQs about Analytics implementation
solution: Analytics
title: FAQs about Analytics implementation
topic: Developer and implementation
uuid: 983d759a-c4f2-4021-84c8-0486dbb951b8
---

# FAQs about Analytics implementation

Frequently asked questions about implementation, and links to more information.

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>Question</b> </td> 
   <td> <b>Answer</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>How do I manage Analytics users and groups? </p> </td> 
   <td colname="col3"> <p>For information about managing users and groups, refer to <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html"> User and Product Management </a> in the Adobe Experience Cloud help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>eVar Expiration - Why are the eVars getting attributed to ‘None’ in the reports? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol"> Expire After </span> specifies a time period, or event, after which the eVar value expires (no longer receives credit for success events). If a success event occurs after eVar expiration, the None value receives credit for the event (no eVar was active). If you select an event as an expiration value, the variable expires only if the event occurs. If the event does not occur, the variable never expires. <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Custom Event Visibility - Why do Custom Events not appear in the reports menu? </p> </td> 
   <td colname="col3"> <p>In the Visibility column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder. This setting does not impact the data collection for that metric or event; it affects only its visibility in the user interface. <a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Timestamps - What do I need to consider before changing timestamp settings? </p> </td> 
   <td colname="col3"> <p>Using the Timestamps Optional feature, you can combine non-timestamped data with timestamped data without incurring data loss. Offline data with timestamps generated from a mobile device can be combined with live, non-timestamped data from a web page—or integrated with data from any platform using a client-side timestamp call. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visitor ID - How does the Visitor ID grace period work and how is it enabled? </p> </td> 
   <td colname="col3"> <p>If you have multiple JavaScript files that are sending data to the same report suite, or if you are using other technologies on your site such as Flash video measurement, we recommend configuring a grace period. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visitor ID - What is the difference between the Experience Cloud Visitor ID and the Analytics Visitor ID? </p> </td> 
   <td colname="col3"> <p>The Identity Service assigns a unique, persistent identifier to all your site visitors. With this ID, visitors and their data can be shared among other solutions in the Experience Cloud. Also, this ID can replace or work with solution-specific IDs such as the Analytics Visitor ID. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visitor ID - How is the Visitor ID set if cookies are blocked? </p> </td> 
   <td colname="col3"> <p>If the standard s_vi cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named s_fid, is set with a 2-year expiration and is used as the fallback identification method going forward. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management - Why does my DTM rule not fire? </p> </td> 
   <td colname="col3"> <p>If your event-based rule does not fire, then there is likely an issue with the selector or condition of the rule. Locate the element on your site where the desired event action occurs, right click and select Inspect element. Inspect the highlighted script in the box that opens and ensure you are targeting the correct element. <a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>How do I implement Heartbeat Video Tracking? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/"> This section </a> contains instructions on downloading the video heartbeat SDKs and developer guides for your platform. Make sure you also download the developer guide that is in the docs folder when you download the SDK as it contains the specific implementation instructions for video heartbeat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>How do I add cookies to the right subdomain? </p> </td> 
   <td colname="col3"> The <span class="varname"> cookieDomainPeriods </span> variable determines the domain on which the Analytics cookies s_cc and s_sq are set by determining the number of periods in the domain of the page URL. This variable is also used by some plug-ins in determining the correct domain to set the plug-in's cookie. See [Configuration Variables](/help/implement/js-implementation/c-variables/configuration-variables.md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Tracking Server - How do I correctly populate my tracking server? </p> </td> 
   <td colname="col3"> <p>When you configure an implementation to send data to Adobe Analytics servers, you must send it to the correct location. Failure to do so causes inflated visitor counting or data loss. <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html"> [More...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performance - Can a failure to load the external Adobe JavaScript, whether due to internet connection, proxy, firewall, or service interruption at Adobe, affect performance? </p> </td> 
   <td colname="col3"> <p>No. The JavaScript file is not hosted on Adobe servers, so an Adobe outage will not affect the JavaScript execution. If dynamic tag management is employed, the JavaScript file is hosted by Akamai, or on a server location determined by customers. </p> <p>See <i>Will Dynamic Tag Management reduce my website's performance?</i> at the <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html"> Dynamic Tag Management FAQ </a>. </p> <p>Additionally, you can host your own core dynamic tag management file if you are not comfortable relying on Akamai's CDN. See <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html"> Embed Code and Hosting Options </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performance - Can the loading of the external Adobe JavaScript cause a reduction in performance? </p> </td> 
   <td colname="col3"> <p> The JavaScript file is cached in the visitor's browser after it is initially loaded, and is typically downloaded no more than once per session. The file is not downloaded on each page, even though it is used by every page on the site. On most web sites, users average more than a few page views per session, so transferring JavaScript that is used multiple times into this file can result in less overall downloaded data. </p> <p> JavaScript for AppMeasurement Compression: If you are concerned about the page weight (size) of Adobe's JavaScript client, Adobe recommends that you consider compressing the file using GZIP. GZIP is supported by all major browsers and offers better performance than JavaScript compression to compress and decompress the core <span class="filepath"> s_code.js </span> JavaScript file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performance - Can the sending of data from the browser to Adobe services reduce performance? </p> </td> 
   <td colname="col3"> <p> The Adobe JavaScript file creates an image object within the HTML page, and the browser then requests the image object from Adobe servers. If the Adobe servers were to be slow or unresponsive, the thread handling that request would be delayed until the image returns or a timeout occurs. Because browsers handle images with multiple threads, an Adobe outage would have a minimal impact on the page load time, tying up one thread while the others continue to function. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performance - Can a JavaScript event from Adobe impact system behavior or functionality? </p> </td> 
   <td colname="col3"> <p>No. See preceding performance answers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> How can I change collected data, based on defined conditions of my own? </td> 
   <td colname="col3"> Use processing rules to simplify data collection and manage content as it is sent to reporting. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> Which is the latest version of s_code file? </td> 
   <td> This section contains a release history for [!DNL AppMeasurement] libraries across web and mobile platforms. The latest version of each library can be downloaded in Reports &amp; Analytics &gt; Admin Tools &gt; Code Manager. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/c_release_notes_javascript.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> How do I debug s_code file? </td> 
   <td> The Adobe Debugger (previously DigitalPulse Debugger) is a free tool provided by Adobe that lets you view the data being collected from your site on any given page. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> How do I track different link types? </td> 
   <td> File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> How do I track video ? </td> 
   <td> JavaScript can be used to track a wide variety of players. To track using JavaScript, you add code to the web page that contains your player and track the player using event handlers. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> How do I track a mobile App? </td> 
   <td> Acquisition links with unique tracking codes can be generated in Adobe Mobile services. When a user downloads and runs an app from the Apple App Store after clicking on the generated link, the SDK automatically collects and sends the acquisition data to Adobe Mobile services. <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/acquisition.html"> iOS </a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/acquisition.html"> Android </a> </td> 
  </tr> 
  <tr> 
   <td> How do I implement video tracking? </td> 
   <td> You can track media players by creating functions attached to the video player event handlers This lets you call Media.open, Media.play, Media.stop, and Media.close at the appropriate times. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js_events.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> How do I set up the First Party Cookie? </td> 
   <td> Analytics uses cookies to provide information on variables and components that do not persist between image requests and browser sessions. These harmless cookies originate from a domain hosted by Adobe, known as third-party cookies. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> How do I get an SSL certificate? </td> 
   <td> Determine whether your site uses https:// protocol. If it does, requesting a CSR and purchasing an SSL certificate is required. Note: An SSL certificate is not required if you do not have any secure pages or content. This entire step may be skipped if you use only https:// protocol on your site. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> Where do I find information about the certification expiration notice? </td> 
   <td> SSL certificates expire each year, meaning that Adobe requires an updated certificate request each time this happens. The FPC specialist provides sufficient warning when this occurs, however, it is recommended to be proactive in monitoring the expiration and providing Adobe with this updated certificate. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_renewals.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> What are plugins? </td> 
   <td> AppMeasurement for JavaScript plug-ins are programs or functions that perform several advanced functions. These plug-ins extend the capabilities of your JavaScript file to give you more functionality that is not available with a basic implementation. Adobe offers a number of other plug-ins as part of advanced solutions. Contact your Account Manager if you want to capture data using JavaScript but are unsure how to proceed. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/impl_plugins.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> Information about data insertion API? </td> 
   <td> Adobe has created multiple ways to send data into Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/usecase_sending_data_to_sc.html"> [More...] </a> </td> 
  </tr> 
  <tr> 
   <td> What is a 500 error? </td> 
   <td> Information about the internal server error which caused a "500 Query Error" status. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html">See pageType variable </a> </td> 
  </tr> 
 </tbody> 
</table>

|Question|Answer|
|---|---|
|How do I manage Analytics users and groups?|For information about managing users and groups, refer to [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) in the Adobe Experience Cloud Core Services help.|
|eVar Expiration - Why are the eVars getting attributed to ‘None’ in the reports?|`Expire After` specifies a time period, or event, after which the eVar value expires (no longer receives credit for success events). If a success event occurs after eVar expiration, the None value receives credit for the event (no eVar was active). If you select an event as an expiration value, the variable expires only if the event occurs. If the event does not occur, the variable never expires. [[More...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)|
|Custom Event Visibility - Why do Custom Events not appear in the reports menu?|In the Visibility column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder. This setting does not impact the data collection for that metric or event; it affects only its visibility in the user interface. [[More...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/metric-visibility.html)|
|Timestamps - What do I need to consider before changing timestamp settings?|Using the Timestamps Optional feature, you can combine non-timestamped data with timestamped data without incurring data loss. Offline data with timestamps generated from a mobile device can be combined with live, non-timestamped data from a web page—or integrated with data from any platform using a client-side timestamp call. [[More...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/timestamps-overview.html)|
|Visitor ID - How does the Visitor ID grace period work and how is it enabled?|If you have multiple JavaScript files that are sending data to the same report suite, or if you are using other technologies on your site such as Flash video measurement, we recommend configuring a grace period.  [More...](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)|
|Visitor ID - What is the difference between the Experience Cloud Visitor ID and the Analytics Visitor ID?|The Identity Service assigns a unique, persistent identifier to all your site visitors. With this ID, visitors and their data can be shared among other solutions in the Experience Cloud. Also, this ID can replace or work with solution-specific IDs such as the Analytics Visitor ID.  [More...](https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html)|
|Visitor ID - How is the Visitor ID set if cookies are blocked?|If the standard s_vi cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named s_fid, is set with a 2-year expiration and is used as the fallback identification method going forward.  [More...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html)|
|Dynamic Tag Management - Why does my DTM rule not fire?|If your event-based rule does not fire, then there is likely an issue with the selector or condition of the rule. Locate the element on your site where the desired event action occurs, right click and select Inspect element. Inspect the highlighted script in the box that opens and ensure you are targeting the correct element.  [More...](https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html)|
|How do I implement Heartbeat Video Tracking?|[This section](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) contains instructions on downloading the video heartbeat SDKs and developer guides for your platform. Make sure you also download the developer guide that is in the docs folder when you download the SDK as it contains the specific implementation instructions for video heartbeat.|
|How do I add cookies to the right subdomain?|The  cookieDomainPeriods  variable determines the domain on which the Analytics cookies s_cc and s_sq are set by determining the number of periods in the domain of the page URL. This variable is also used by some plug-ins in determining the correct domain to set the plug-in's cookie. See [Configuration Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html)|
|Tracking Server - How do I correctly populate my tracking server?|When you configure an implementation to send data to Adobe Analytics servers, you must send it to the correct location. Failure to do so causes inflated visitor counting or data loss. [More...](https://helpx.adobe.com/analytics/kb/determining-data-center.html)|
|Performance - Can a failure to load the external Adobe JavaScript, whether due to internet connection, proxy, firewall, or service interruption at Adobe, affect performance?|No. The JavaScript file is not hosted on Adobe servers, so an Adobe outage will not affect the JavaScript execution.|
|Performance - Can the loading of the external Adobe JavaScript cause a reduction in performance?|The JavaScript file is cached in the visitor's browser after it is initially loaded, and is typically downloaded no more than once per session. The file is not downloaded on each page, even though it is used by every page on the site. On most web sites, users average more than a few page views per session, so transferring JavaScript that is used multiple times into this file can result in less overall downloaded data. <br>JavaScript for AppMeasurement Compression: If you are concerned about the page weight (size) of Adobe's JavaScript client, Adobe recommends that you consider compressing the file using GZIP. GZIP is supported by all major browsers and offers better performance than JavaScript compression to compress and decompress the core `s_code.js` JavaScript file.|
|Performance - Can the sending of data from the browser to Adobe services reduce performance?|The Adobe JavaScript file creates an image object within the HTML page, and the browser then requests the image object from Adobe servers. If the Adobe servers were to be slow or unresponsive, the thread handling that request would be delayed until the image returns or a timeout occurs. Because browsers handle images with multiple threads, an Adobe outage would have a minimal impact on the page load time, tying up one thread while the others continue to function.|
|Performance - Can a JavaScript event from Adobe impact system behavior or functionality?|No. See preceding performance answers.|
|How can I change collected data, based on defined conditions of my own?|Use processing rules to simplify data collection and manage content as it is sent to reporting.  ([More...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html)|
|Which is the latest version of s_code file?|This section contains a release history for AppMeasurement libraries across web and mobile platforms. The latest version of each library can be downloaded in Analytics > Admin > Code Manager. [More...](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md)|
|How do I debug s_code file?|The Experience Cloud Debugger is a free tool provided by Adobe that lets you view the data being collected from your site on any given page. [More...](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html)|
|How do I track different link types?|File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file. [More...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/function-tl.html)|
|How do I track video ?|JavaScript can be used to track a wide variety of players. To track using JavaScript, you add code to the web page that contains your player and track the player using event handlers. [More...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html)|
|How do I track a mobile App?|Acquisition links with unique tracking codes can be generated in Adobe Mobile services. When a user downloads and runs an app from the Apple App Store after clicking on the generated link, the SDK automatically collects and sends the acquisition data to Adobe Mobile services. [iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html), [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html)|
|How do I implement video tracking?|You can track media players by creating functions attached to the video player event handlers This lets you call Media.open, Media.play, Media.stop, and Media.close at the appropriate times. [More...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html)|
|How do I set up the First Party Cookie?|Analytics uses cookies to provide information on variables and components that do not persist between image requests and browser sessions. These harmless cookies originate from a domain hosted by Adobe, known as third-party cookies. [More...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html)|
|How do I get an SSL certificate?|Determine whether your site uses the `https://` protocol. If it does, requesting a CSR and purchasing an SSL certificate is required. Note: An SSL certificate is not required if you do not have any secure pages or content. This entire step may be skipped if you use only `https://` protocol on your site.  [More...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html)|
|Where do I find information about the certification expiration notice?|SSL certificates expire each year, meaning that Adobe requires an updated certificate request each time this happens. The FPC specialist provides sufficient warning when this occurs, however, it is recommended to be proactive in monitoring the expiration and providing Adobe with this updated certificate. [More...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)|
|What are plugins?|AppMeasurement for JavaScript plug-ins are programs or functions that perform several advanced functions. These plug-ins extend the capabilities of your JavaScript file to give you more functionality that is not available with a basic implementation. Adobe offers a number of other plug-ins as part of advanced solutions. Contact your Account Manager if you want to capture data using JavaScript but are unsure how to proceed. [More...](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)|
|How do I find information about Data Insertion API?|Adobe has created multiple ways to send data into Analytics. [More...](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)|
|What is a 500 error?|Information about the internal server error which caused a "500 Query Error" status can be found at [pageType variable](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985).|
