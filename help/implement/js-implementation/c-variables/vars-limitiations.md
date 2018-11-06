---
description: High-level look at variables and their limitations.
keywords: Analytics Implementation;variable;limitations;limits
seo-description: High-level look at variables and their limitations.
seo-title: Variables and limitations
solution: Analytics
subtopic: Variables
title: Variables and limitations
topic: Developer and implementation
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
index: y
internal: n
snippet: y
---

# Variables and limitations

High-level look at variables and their limitations.

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

The following table provides at-a-glance information about [!DNL Analytics] variables: 

|  Variable  | Description  |
|---|---|
|  s_account  | Determines the report suite where data is stored and reported.  |
|  browserHeight  | Displays the height of the browser window.  |
|  browserWidth  | Displays the width of the browser window.  |
|  campaign  | Identifies marketing campaigns used to bring visitors to your site. The value of *`campaign`* is usually taken from a query string parameter.  |
|  channel  | Usually identifies a section of your website. For example, a merchant may have sections such as Electronics, Toys, or Apparel. A media site may have sections such as News, Sports, or Business.  |
|  charSet  | Translates the character set of the Web page into UTF-8.  |
|  colorDepth  | Displays the number of bits used to display color on each pixel of the screen.  |
|  connectionType  | Indicates (in Microsoft Internet Explorer) whether the browser is configured on a LAN or modem connection.  |
|  cookieDomainPeriods  | Determines the domain on which the [!DNL Analytics] [!UICONTROL visitor ID] (s_vi) cookie will be set by determining the number of periods in the domain of the page URL. For www.mysite.com, *`cookieDomainPeriods`* should be "2." For www.mysite.co.jp, *`cookieDomainPeriods`* should be "3."  |
|  cookieLifetime  | Used by both JavaScript and [!DNL Analytics] servers to determine the lifespan of a cookie.  |
|  cookiesEnabled  | Indicates whether a first-party session cookie could be set by JavaScript.  |
|  currencyCode  | Determines the conversion rate to be applied to revenue as it enters the [!DNL Analytics] databases. [!DNL Analytics] databases store all monetary amounts in a currency of your choice. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.  |
|  dc  | Lets you set the data center to which your data is sent.  |
|  doPlugins  | *`doPlugins`* is a reference to the *`s_doPlugins`* function. It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file.  |
|  dynamicAccountList  | Dynamically selects a report suite to which data is sent. The *`dynamicAccountList`* variable contains the rules that used to determine the destination report suite.  |
|  dynamicAccountMatch  | Uses the DOM object to retrieve the section of the URL to which all rules in *`dynamicAccountList`* are applied. This variable is only valid when *`dynamicAccountSelection`* is set to 'True.'  |
|  dynamicAccountSelection  | Lets you dynamically select the report suite based on the URL of each page.  |
|  dynamicVariablePrefix  | Allows deployment to flag variables that should be populated dynamically. Cookies, request headers, and image query string parameters are available to be populated dynamically.  |
|  eVarN  | Used for building custom reports within the [!DNL Analytics] [!UICONTROL Conversion Module]. When an eVar is set to a value for a visitor, [!DNL Analytics] remembers that value until it expires. Any success events that a visitor encounters while the eVar value is active are counted toward the eVar value.  |
|  events  | Records common shopping cart success events and custom success events.  |
|  fpCookieDomainPeriods  | Determines the domain on which [!DNL Analytics] cookies other than the [!UICONTROL visitor ID] (s_vi) cookie will be set by determining the number of periods in the domain of the page.  |
|  hierN  | Determines the location of a page in your site's hierarchy. This variable is most useful for sites that have more than three levels in the site structure.  |
|  homepage  | Indicates (in Internet Explorer) whether the current page is set as the user's home page.  |
|  javaEnabled  | Indicates whether Java is enabled in the browser.  |
|  javascriptVersion  | Displays the version of JavaScript supported by the browser.  |
|  linkDownloadFileTypes  | A comma-separated list of file extensions. If your site contains links to files with any of these extensions, the URLs of these links appear in the [!UICONTROL File Downloads] report.  |
|  linkExternalFilters  | If your site contains many links to external sites, and you don't want to track all exit links, *`linkExternalFilters`* can be used to report on a specific subset of exit links.  |
|  linkInternalFilters  | Determines which links on your site are exit links. It is a comma-separated list of filters that represent the links that are part of the site.  |
|  linkLeaveQueryString  | Determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports.  |
|  linkName  | An optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link. The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.  |
|  linkTrackEvents  | Contains the events that should be sent with custom, download, and exit links. This variable is only considered if *`linkTrackVars`* contains "events."  |
|  linkTrackVars  | A comma-separated list of variables that will be sent with custom, exit, and download links. If *`linkTrackVars`* is set to "", all variables that have values are sent with link data.  |
|  linkType  | An optional variable used in link tracking that determines which report a Link Name or URL will appear (custom, download, or exit Links). *`linkType`* is not normally needed because the second parameter in the *`tl()`* function replaces it.  |
|  mediaLength  | Specifies the total length of the media being played.  |
|  mediaName  | Specifies the name of the video or media item. It is only available via the [!UICONTROL Data Insertion API] and [!UICONTROL Full Processing Data Source].  |
|  mediaPlayer  | Specifies the player used to consume a video or media item.  |
|  mediaSession  | Specifies the segments of a video or media asset consumed.  |
|  Media.trackEvents  | Identifies which events should be sent with a media hit. It is only applicable with JavaScript [!UICONTROL ActionSource.].  |
|  Media.trackVars  | Identifies which variables should be sent with a media hit. It is only applicable with JavaScript [!UICONTROL ActionSource.].  |
|  mobile  | Controls the order in which cookies and subscriber ids are used to identify visitors.  |
|  s_objectID  | A global variable that should be set in the [!UICONTROL onClick] event of a link. By creating a unique object ID for a link or link location on a page, you can improve visitor click map tracking or use visitor click map to report on a link type or location, rather than the link URL.  |
|  pageName  | Contains the name of each page on your site. If *`pageName`* is blank, the URL is used to represent the page name in [!DNL Analytics].  |
|  pageType  | Used only to designate a 404 Page Not Found Error page. It only has one possible value, which is "errorPage." On a 404 Error page, the *`pageName`* variable should not be populated.  |
|  pageURL  | In rare cases, the URL of the page is not the URL that you would like reported in [!DNL Analytics]. To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page.  |
|  plugins  | On Netscape and Mozilla-based browsers, lists the plugins installed in the browser.  |
|  products  | Used for tracking products and product categories as well as purchase quantity and purchase price. The *`products`* variable should always be set in conjunction with a success event. Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars.  |
|  propN  | Used for building custom reports within the [!DNL Analytics] [!UICONTROL Traffic Module]. [!UICONTROL props] may be used as counters (to count the number of times a page view is sent), for pathing reports, or in correlation reports.  |
|  purchaseID  | Used to keep an order from being counted multiple times by [!DNL Analytics]. Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable.  |
|  referrer  | Restores lost referrer information.  |
|  resolution  | Displays the monitor resolution of the visitor viewing the Web page.  |
|  server  | Shows either the domain of a Web page (to show which domains people come to) or the server serving the page (for a load balancing quick reference).  |
|  state  | Captures the state in which a visitor to your site resides.  |
|  trackDownloadLinks  | Set *`trackDownloadLinks`* to 'true' if you want to track links to downloadable files on your site. If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* determines which links are downloadable files.  |
|  trackExternalLinks  | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link.  |
|  trackingServer  | Used for first-party cookie implementation to specify the domain at which the image request and cookie is written. Used for non-secure pages.  |
|  trackingServerSecure  | Used for first-party cookie implementation to specify the domain at which the image request and cookie is written. Used for secure pages.  |
|  trackInlineStats  | Determines whether visitor click map data is gathered.  |
|  transactionID  | Ties offline data to an online transaction (like a lead or purchase generated online). Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. See the [Data Sources Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).  |
|  s_usePlugins  | If the *`s_doPlugins`* function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.' When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request.  |
|  visitorID  | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. The *`visitorID`* may be up to 100 alphanumeric characters and must not contain a hyphen.  |
|  visitorNamespace  | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. This variable is used to identify the domain with which cookies are set. If *`visitorNamespace`* changes, all visitors reported in [!DNL Analytics] may become new visitors. In short, do not alter this variable without approval from an Adobe consultant.  |
|  zip  | Captures the ZIP code in which a visitor to your site resides.  |

