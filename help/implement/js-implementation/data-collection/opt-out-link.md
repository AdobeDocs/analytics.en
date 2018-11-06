---
description: Specify an opt-out link, and customize the branding for the link. Visitors to your web site may choose not to have their activity tracked in Adobe’s analytics products by visiting the opt-out page for your data collection domain.
keywords: Analytics Implementation
seo-description: Specify an opt-out link, and customize the branding for the link. Visitors to your web site may choose not to have their activity tracked in Adobe’s analytics products by visiting the opt-out page for your data collection domain.
seo-title: Add an opt-out link
solution: Analytics
subtopic: Troubleshooting
title: Add an opt-out link
topic: Developer and implementation
uuid: c12092be-3be7-4621-b838-d6b78d074f84
index: y
internal: n
snippet: y
---

# Add an opt-out link

Specify an opt-out link, and customize the branding for the link. Visitors to your web site may choose not to have their activity tracked in Adobe’s analytics products by visiting the opt-out page for your data collection domain.

 If a user chooses not to be tracked and an opt-out cookie is set, your JavaScript file will continue to send data to Adobe servers but that data will not be processed or reported on.

The collection_domain section of the URL structure is the trackingServer used in your JavaScript file. The collection domain used for your Adobe Analytics implementation can be seen in the DigitalPulse debugger in the first row of the Adobe Analytics table, which is labeled either “First Party Cookies” or “Third Party Cookies” depending on your implementation. The collection domain for your website may contain 2o7.net, omtrdc.net or your website domain, such as metrics.example.com.

Visitors opt-out by clicking the link on the opt-out page, thereby causing a cookie to be set in their browser. By having the `omniture_optout` cookie for the applicable tracking domain, the user's activities will not be reported by Adobe Analytics. You can provide your own link to the opt-out cookie, or you can follow the steps below to set the opt-out cookie.

Adobe offers opt-outs for all implementation types. You are responsible for your own privacy policy and for remaining in compliance with your signed terms. Note that the link to the opt-out page changes based on your implementation type, as outlined here.

If you implement Adobe Analytics products and services with cookies set on domains owned by Adobe (i.e. 207.net or omtrdc.net), you can point your website visitors to the opt-out mechanism provided in the [Adobe Privacy Center](http://www.adobe.com/privacy/opt-out.html) for all sites that use Adobe cookies for Adobe Analytics products and services. The direct link to the Adobe opt-out mechanism is http://collection_domain/optout.html.

More information about Adobe Analytics privacy practices can be found at [http://www.adobe.com/privacy/advertising-services.html](http://www.adobe.com/privacy/advertising-services.html).

* [Opt-out Page URL Structure](../../../implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748) 
* [Example Opt-Out URLs](../../../implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E) 
* [Branding your Opt-Out URL](../../../implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## Opt-out Page URL Structure {#section_E0462428D2E440E7863E24D2F6DBF748}

Your opt out page is at the following URL:

```
http://collection_domain/optout.html[?optional_parameters]
```

The `optional_parameters` include:

`locale=[code]`: Provides a translated version of the opt-out page. The following locales are supported:

* en_US (default) 
* de_DE 
* es_ES 
* fr_FR 
* jp_JP 
* ko_KR 
* zh_CN 
* zh_TW

`popup=1`: Treats the page as if it were a popup, and offers a “Close Window” button.

## Example Opt-Out URLs {#section_258DE5226AA0483CA790D2C9C5318B2E}

An English web page in a full window containing a link that, when clicked, will prevent the visitor from being tracked on metrics.example.com:

```
http://metrics.example.com/optout.html
```

A French web page in a full window, containing a link that, when clicked, will prevent the visitor from being tracked on example.d3.sc.omtrdc.net:

```
http://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

A German web page, in a popup window, containing a link that, when clicked, will prevent the visitor from being tracked on example.112.2o7.net:

```
http://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## Branding your Opt-Out URL {#section_674AB62E810B414AB8F1615C0E3061F8}

You can provide a link, such as the following somewhere on your website:

```
 <a href=" http://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

Where *`stats.adobe.com`* is replaced with whatever the *`s.trackingServer`* variable is set to.

Additionally, if you want like to provide a link to opt-in, use the same URL, but replace `?optout=1` with `?optin=1`, and keep the `confirm_change=1`. 
