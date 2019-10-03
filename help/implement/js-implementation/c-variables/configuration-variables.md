---
description: Configuration variables set in AppMeasurement.js.
keywords: Analytics Implementation
seo-description: Configuration variables set in AppMeasurement.js for Adobe Analytics
seo-title: Configuration variables
solution: Analytics
subtopic: Variables
title: Configuration variables
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
---

# Configuration variables overview

Configuration variables control the way data is captured and processed in reporting. The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). These variables can be set within the Analytics page-level code and links when appropriate.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** > **[!UICONTROL Code Manager]**. Some of these configuration variables may not be applicable to your site's implementation needs.

Some of the goals of using these configuration variables are:

* Track multiple sites/domains.
* Use any currency on purchases.
* Capture data indifferent languages.
* Link tracking (number of downloaded files, links to external sites.
* Track custom links for unique purposes.

>[!NOTE]
>
>[!DNL AppMeasurement] requires that all configuration variables are set before the initial call to the track function, `t()`. If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

For help with specific configuration variables, click any of the following links:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specify the report suite where data is stored and reported.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Dynamically select the report suite based on the URL of each page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Specify the rules used for determining the destination report suite.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Use the DOM object to retrieve the section of the URL to which all rules are applied.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Deploy flagging for dynamically-populated variables.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Convert incoming data to UTF-8 for storage and reporting by Analytics. 

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Determine the conversion rate to apply to revenue.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Determines which domain the `s_cc` and `s_sq` cookies are set.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html): Determine the domain for `s_cc` and `s_sq` cookies by specifying the number of periods in the domain of the page URL.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Specify cookies set by JavaScript (`s_sq`, `s_cc`, plug-ins) that are inherently first-party cookies, even with third-party `2o7.net` or `omtrdc.net` domains.

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Determine lifespan of a cookie as processed by both JavaScript and data collection servers.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Refer and allow the function to be called at the appropriate location within the JavaScript file.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Function for taking as parameters both the callback (a function), and the parameters to that function.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Function for taking as parameters both the callback (a function), and the parameters to that function.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Track links to downloadable files on your site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Determine whether any link clicked is an exit link.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determine whether ClickMap data is gathered.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html): Include a comma-separated list of file extensions.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html): Includes a comma-separated list of filters that represent the links that are part of the site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Determine whether or not the query string should be included in the Exit Links and File Download reports.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Include a comma-separated list of variables that are sent with custom, exit, and download links.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Use to report on a specific subset of exit links.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html): Call the `s_doPlugins` function prior to each image request.

