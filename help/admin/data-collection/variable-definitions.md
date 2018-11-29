---
description: Descriptions of variables and how each is used in reporting.
seo-description: Descriptions of variables and how each is used in reporting.
seo-title: Variables - how they are used in reporting
solution: Analytics
subtopic: Variables
title: Variables - how they are used in reporting
topic: Developer and implementation,Reports
uuid: bd6b697a-c11a-434c-9d75-d46ecfec49ef
index: y
internal: n
snippet: y
---

# Variables - how they are used in reporting

Descriptions of variables and how each is used in reporting.

## Variables {#section_193C396A80F944E4A5D44ABA75046383}

Analytics variables are usually populated in the HTML code, on each page or template of the site. Additionally, plug-ins and global code may be added to the [!DNL .js] file that also populates the variables, or overrides the values set in the HTML pages. The variables that are populated include the following.

**NOTE:** &#42; Denotes a conversion variable. These variables require that the conversion module be enabled. 

|Implementation Variable|Description|Reports Populated|
|[pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/pageName.html)|The name of the page. Uniquely identifies the page and URL in plain English. For example:    "homepage"|[Pages Report](/help/components/c-variables/dimensionslist/reports-pages.md)<br></br>[Paths Reports](/help/components/c-variables/dimensionslist/reports-paths.md)|
|[channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/channel.html)|The section of the site, or channel. For example:    "electronics",  "news"|[Site Sections Report](/help/components/c-variables/dimensionslist/reports-site-sections.md)|
|[contextData](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html)|Available with version 15 and [processing rules](../../admin/admin/c-processing-rules/processing-rules.md).<br></br>contextData variables require no knowledge of the various types of variables Analytics offers (props, eVars, etc).<br></br>An analyst can request a variable name be implemented, and apply processing rules to assign that context data to a variable.|None. Context Data must be mapped to variables for reporting.|
|[server](https://marketing.adobe.com/resources/help/en_US/sc/implement/server.html)|The server name or vanity domain to be tracked.|[Servers Report](/help/components/c-variables/dimensionslist/reports-servers.md)|
|[propN](https://marketing.adobe.com/resources/help/en_US/sc/implement/propN.html) (prop1 - prop75)|Custom values. The specific meaning of each variable is defined uniquely for each web site.|Multiple|
|[hierN](https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html) (hier1 - hier5)|Hierarchy variables, used to record visits and visitors for a hierarchically structured site.|[Hierarchy Report](/help/components/c-variables/dimensionslist/reports-hierarchy.md)|
|[campaign](https://marketing.adobe.com/resources/help/en_US/sc/implement/campaign.html)\*|Tracks advertising or email click-throughs to the site. Campaigns are also correlated to many values throughout the system, such as to conversion and custom events, referring domains, and search engines.|[Tracking Codes Report](/help/components/c-variables/dimensionslist/reports-tracking-codes.md)|
|[eVarN](https://marketing.adobe.com/resources/help/en_US/sc/implement/eVarN.html) (eVar1 - eVar75*)|Custom variables that are tracked and correlated to any events. The specific meaning of each variable is defined uniquely for each web site.  s.eVar values are stored and correlated to events that happen afterward.|Multiple|
|[products](https://marketing.adobe.com/resources/help/en_US/sc/implement/products.html)\*|List of products, used in conjunction with the  s.events variable|All Product reports|
|[events](https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html)\*|The list of events that occurred on the current page. Examples include:  scOpen,  scAdd,  scCheckout,  prodView, purchase, or any custom event from event1 to event20.|All Event reports|
|[purchaseID](https://marketing.adobe.com/resources/help/en_US/sc/implement/purchaseID.html)\*|Up to 20 character code to uniquely identify the purchase, in conjunction with the purchase event|[Revenue](/help/components/c-variables/dimensionslist/reports-revenue.md)|
|[state](https://marketing.adobe.com/resources/help/en_US/sc/implement/state.html)\*|State name or ID, to be used on the order confirmation (Thank You) page, in conjunction with the purchase event|[U.S. State](/help/components/c-variables/dimensionslist/reports-state.md)|
|[zip](https://marketing.adobe.com/resources/help/en_US/sc/implement/zip.html)\*|Zip code, to be used on the order confirmation (Thank You) page, in conjunction with the purchase or other event|[Visitor Zip and Postal Codes Report](/help/components/c-variables/dimensionslist/reports-zip.md)|
|[linkName](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkName.html)|Optionally used to identify the name of a link when sending in custom, download, or exit link data.|[File Downloads Report](/help/components/c-variables/dimensionslist/reports-file-downloads.md)<br></br>[Custom Links Report](/help/components/c-variables/dimensionslist/reports-custom-links.md)<br></br>[Exit Links Report](reports_exit_links.md)|
|[linkType](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkType.html)|Used to identify the type of link: Custom, Download, or Exit|[File Downloads Report](/help/components/c-variables/dimensionslist/reports-file-downloads.md)<br></br>[Custom Links Report](/help/components/c-variables/dimensionslist/reports-custom-links.md)<br></br>[Exit Links Report](reports_exit_links.md)|
|[List Props](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_props.html)|List variables are a delimited list of values that are passed into a variable, and then reported as individual line items for reporting.|Multiple|
|[List Variable](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html) (list var)|Similar to how List Props function, List Vars allow multiple values within the same image request.  Version 15 only.|Multiple|
|[s\_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html)|A ClickMap variable used to uniquely identify links on a page|ClickMap|
|[pageType](https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html)|Used on 404-Page Not Found error pages|[Pages Not Found Report](/help/components/c-variables/dimensionslist/reports-pages-not-found.md)|
|[pageURL](https://marketing.adobe.com/resources/help/en_US/sc/implement/pageURL.html)|Optionally used to override the URL of the page as recorded in Analyitcs|[Pages Report](/help/components/c-variables/dimensionslist/reports-pages.md)<br>/br>[Paths Reports](reports_paths.md)|
|[referrer](https://marketing.adobe.com/resources/help/en_US/sc/implement/referrer.html)|Optionally used to override a page's referrer as recorded in Analyitcs|[Finding Methods Report](/help/components/c-variables/dimensionslist/reports-finding-methods.md)|
|[transactionID](https://marketing.adobe.com/resources/help/en_US/sc/implement/transactionID.html)|Integration Data Sources utilize a transaction ID to tie offline data to an online transaction (like a lead or purchase generated online)|N/A|
|[visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visitorID.html)|Visitors may be identified by the visitorID variable, or by IP address/User Agent|N/A|

## Configuration Variables {#section_C6A32064666248AFBCB5FFA39FE66179}

Configuration variables, which control data collection, are contained in the [!DNL .js] file, but they are not considered data collection elements. Configuration variables are not included in marketing reports, but they may affect the data, or the appearance of the reports. Configuration variables include the following. 

|Implementation Variable|Description|Reports Populated|
|[s\_account](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_account.html)|Report suite IDs. The account(s) that the page view is reported in.|N/A|
|[charSet](https://marketing.adobe.com/resources/help/en_US/sc/implement/charset.html)|The character set used on the page. The default is assumed to be ISO-8859-1. A list of available character sets is available from Adobe.|N/A|
|[currencyCode](https://marketing.adobe.com/resources/help/en_US/sc/implement/currencycode.html)|The currency code used in the  s.products and  s.events variables. The default is assumed to be USD (U.S. dollars). A list of supported currency codes is available from Adobe.|[Revenue](/help/components/c-variables/dimensionslist/reports-revenue.md)<br>All conversion reports showing revenue or monetary values|
|[cookieDomainPeriods](https://marketing.adobe.com/resources/help/en_US/sc/implement/cookiedomainperiods.html)|The number of sections in a domain on which the visitor ID cookie is set.|Affects multiple reports as it controls how the visitor ID is stored and handled.|
|[fpCookieDomainPeriods](https://marketing.adobe.com/resources/help/en_US/sc/implement/fpCookieDomainPeriods.html)|The number of sections in a domain on which cookies are set by the JavaScript file. This overrides the value of  cookieDomainPeriods for JavaScript cookies.|N/A|
|[cookieLifetime](https://marketing.adobe.com/resources/help/en_US/sc/implement/cookielifetime.html)|Establishes the lifetime of the visitor cookie (s.vixxxx). Configuration of this variable is completed by Adobe and should not be modified by clients.|See [Implementing First-Party Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)|
|[doPlugins](https://marketing.adobe.com/resources/help/en_US/sc/implement/doPlugins.html)|The function that should be called before data is sent to Analytics.|The doPlugins variable is a reference to the s\_doPlugins function, and allows the  s\_doPlugins function to be called at the appropriate location within the JavaScript file.|
|[dynamicAccountSelection](https://marketing.adobe.com/resources/help/en_US/sc/implement/dynamicAccountSelection.html)|Set to  "true" if  "s.dynamicAccountList" contains a list of domain/report suite ID pairs to be used to dynamically select the report suite ID based on domain, host, or directory name.|N/A|
|[dynamicAccountList](https://marketing.adobe.com/resources/help/en_US/sc/implement/dynamicAccountList.html)|A list of domains and which report suite ID should be used for each (such as  "abc.com=reportabc").|N/A|
|[dynamicAccountMatch](https://marketing.adobe.com/resources/help/en_US/sc/implement/dynamicAccountMatch.html)|The section of the URL that all filters in  dynamicAccountList are applied to|N/A|
|[trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/trackDownloadLinks.html)|Set to  "true" to track clicks on links that have extension names listed in  s.linkDownloadFileTypes.|N/A|
|[trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/trackExternalLinks.html)|Set to  "true" to track clicks on links that are external. External links are domains not listed in  s.linkInternalFilters.|N/A|
|[trackInlineStats](https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html)|Set to  "true" to capture data for ClickMap reporting.|ClickMap|
|[linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkDownloadFileTypes.html)|The list of download file types.|[File Downloads Report](/help/components/c-variables/dimensionslist/reports-file-downloads.md)|
|[linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkInternalFilters.html)|Determines which links on your site are exit links, which is any link that takes a visitor away from your site. It is a comma-separated list of filters that represent the links that are part of the site.|Exit Links Report|
|[linkExternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkExternalFilters.html)|The list of all domains which should be considered external. This is used to limit the number of external links that will be used, not to specify specific links as external.|[Exit Links Report](/help/components/c-variables/dimensionslist/reports-exit-links.md)|
|[linkLeaveQueryString](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkLeaveQueryString.html)|Whether or not the query string of exit links and download links should be included for tracking purposes.|[File Downloads Report](/help/components/c-variables/dimensionslist/reports-file-downloads.md)<br></br>[Exit Links Report](/help/components/c-variables/dimensionslist/reports-exit-links.md)|
|[linkTrackVars](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkTrackVars.html)|The variables that should be sent on custom links, download links, and external links. By default, this variable is set to "None" so that variables set on the page are not recounted by link clicks.|Any|
|[linkTrackEvents](https://marketing.adobe.com/resources/help/en_US/sc/implement/linkTrackEvents.html)|The events to be sent on custom links, download links, and external links. By default, this variable is set to "None" that variables set on the page are not recounted by link clicks.|Conversion|
|[usePlugins](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_usePlugins.html)|If set to  "true",  s\_doPlugins() will be called by the  .JS code prior to creating the image request.|N/A|

## Automatic Variables {#section_2264E57132144263BFEEC40F63AB85F3}

Automatic variables are obtained by the [!DNL .JS] code either automatically, or they are populated in the [!DNL .JS] file as a result of the control variables explained above. The names of these variables are defined only within the query string of the image request. There is no equivalent HTML-based variable. The automatic variables include the following. 

|Automatic Variable|Description|
|r (Referring URL)|The referring URL as defined by the browser. This value includes all query string parameters for the referring URL, including search strings and other information.|
|g (Current URL)|The current page's URL. This value may include all query string parameters, depending upon the account settings and configuration.|
|ClickMap data (various)|Various information about the page ID, link clicked, including destination URL, link number, etc.|
|t|The time and date that the event request occurred, in local time.|
|v|Whether Java is enabled (Y/N).|
|j|The version of JavaScript supported by the browser.|
|bw, bh|The width and height of the browser window.|
|s|The width and height of the screen (the physical monitor).|
|c|Monitor depth (number of available colors).|
|ct|Connection type, including LAN, modem, etc.|
|p|Netscape plug-ins (if running Netscape, the list of plug-ins installed in the browser)|
|k|Cookies enabled (whether or not cookies are enabled in the browser based on a test cookie)|
|hp|Whether the current page is set as the browser's Home page|

## Direct Variables {#section_73B40376C5D847DC82CB9863F26D086F}

Direct variables are those set directly by the browser in the HTTP header of the image request sent to Analytics. These variables are set in each request that is made for any content on the Internet and include some of the most basic user information. The variables are reported directly or indirectly in a number of marketing reports. Direct variables include the following. 

|Direct Variable|Description|
|IP address|The IP address is the Internet Protocol address of the user's browser or machine. That IP addresses may be pooled among multiple users, and that a single user may also use more than one IP address from page to page.  The user's IP address is resolved to geographic location based on data provided by Digital Envoy through a partnership with Adobe.|
|domain|The domain from which the user is requesting data. In many cases, this is a company or an Internet Service Provider (ISP) such as AOL.|
|user agent string|The user agent string indicates the browser and version, and the Operating System used. In some cases, it may also contain major plug-in or customization features (i.e., .NET). The  Browser,  Browser Version, and  Operating System reports are based on the user agent string.|
|language|The preferred language setting of the browser.|
|cookies|The names and values of all cookies that have been set.|
