---
description: Implement the Accelerated Mobile Pages (AMP) project in Adobe Analytics.
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
seo-description: Implement the Accelerated Mobile Pages (AMP) project in Adobe Analytics.
seo-title: Accelerated Mobile Pages
solution: Analytics
title: Accelerated Mobile Pages
topic: Developer and implementation
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
---

# Accelerated Mobile Pages

Implement the Accelerated Mobile Pages (AMP) project in Adobe Analytics.

 AMP is an [open source project](https://www.ampproject.org/) that lets you build web pages for static content that renders quickly. This feature is ideal for publishers who want to create mobile-optimized content once, and have it load instantly everywhere. Topics include:

* [How it Works](/help/implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF) 
* [Using the amp-analytics tag with the "adobeanalytics" template](/help/implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E) 
* [Using the amp-analytics tag with the "adobeanalytics_nativeConfig" template](/help/implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF) 
* [Summary](/help/implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07) 
* [Frequently Asked Questions](/help/implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Additional Documentation and Examples**

* External, open-source AMP project [documentation](https://www.ampproject.org/docs/get_started/about-amp.html) 
* Setup [examples](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)

## How it Works {#section_21C2836D63104794BCEBEECB6593AFBF}

AMPs have specially tagged HTML pages cached around the web on different content delivery networks (CDNs) of participating technology partners and publishers. By doing this, AMP content is delivered from the closest possible source with the lowest possible latency. This creates an analytics challenge because you can never be 100% sure where a publisher's content will be loaded from, and third-party cookies are troublesome for visitor identification.

In addition, to dramatically reduce page weight and speed page load time, AMPs restrict the use of JavaScript and cookies. While this is advantageous for your mobile device because it reduces the amount of processing, it introduces challenges to accurately measuring unique visitors and understanding user acquisition and retention.

To solve these problems, Adobe has collaborated with AMP partners and publishers on two options that a publisher can choose from to best suit their business needs, both using the `amp-analytics` tag. The first approach uses the `"adobeanalytics"` tracking template to construct the Analytics request directly from within the AMP. The second approach uses the `"analytics_nativeConfig"` tracking template, which uses an iframe containing the AppMeasurement code you deploy on your normal site. The following table gives you an idea of the pros and cons of each approach.

|   | **"adobeanalytics" template** | **"adobeanalytics_nativeConfig" template** |
|---|---|---|
|  Visitor/visit counts (in existing report suite)  | High inflation  | Minimal inflation  |
|  Using a separate report suite  | Recommended  | Not necessary  |
|  New vs. return visitors  | Not supported  | Supported  |
|  Visitor ID service  | Not supported  | Supported  |
|  Video & link tracking  | Partial support  | Not yet supported  |
|  Difficulty of implementation  | Somewhat difficult  | Relatively easy  |
|  [!DNL Experience Cloud] integrations  | Not supported  | Supported with caveats  |

## Using the amp-analytics tag with the "adobeanalytics" template {#section_2E4EBF4EF623440D95DE98E78C47244E}

The `"adobeanalytics"`tracking template utilizes the `amp-analytics` tag to construct a tracking request directly. Using the `"adobeanalytics"` template in the `amp-analytics` tag, you can specify hit requests that fire on specific page events, like the page becoming visible or on a click (and in the future, video views and more). Click events can be customized to apply to certain element IDs or classes by specifying a selector. Adobe has made this easy to set up using the `"adobeanalytics"` template specifically designed for [!DNL Adobe Analytics]. You can load the template by adding `type="adobeanalytics"` to the amp-analytics tag.

In the following code example, there are two triggers defined: `pageLoad` and `click`. The `pageLoad` trigger will fire when the document becomes visible and will include the `pageName` variable as defined in the `vars section`. The second trigger `click` will fire when a button is clicked. `eVar 1` will be set for this event with the value `button clicked`.

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
      }, 
      "click": { 
        "on": "click", 
        "selector": "button", 
        "request": "myClick", 
        "vars": { 
          "eVar1": "button clicked" 
        } 
      } 
    } 
  } 
  </script> 
  </amp-analytics> 

```

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and will be automatically set to denote this hit as a non-stage event (i.e. `trackLink` call).

Additionally, `amp-analytics` supports a number of variable substitutions so that AMP can provide data values that it is aware of. You can learn all about those and more by visiting: [amp-analytics variable documentation](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md).

Be aware that if you want to incorporate any technology or DOM variables (such as browser, screen size, device, referrer, etc.) you will have to explicitly add them to any request, as they are not automatically generated for you. Documentation on each of our available query string parameters used for tracking can be found [here](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html).

If you inspect the hits created by amp-analytics, you will notice that in each request, Adobe has included the `vid` query parameter. We set the `vid` based on a built-in AMP function to set a custom Analytics cookie ID named `adobe_amp_id`. This ID is independent of any other ID being set by [!DNL Adobe Analytics] elsewhere (e.g. `s_vi cookie`) and creates new visitors in any report suite the hits are sent to.

There are a few caveats to be aware of. When using the amp-analytics tag as mentioned above, visitors will be independent of your normal tracking, and because the AMP can be loaded from any content delivery network, you will get a unique visitor for each CDN a visitor sees this AMP on (hence the visitor inflation mentioned previously). For this reason, Adobe recommends that if you use the `"adobeanalytics"` template for `amp-analytics`, you put your data into a separate report suite specific to AMP. Also, the [!DNL Experience Cloud] ID service (formerly, *`visitor ID service`*) is not supported using this method, so if your business requires additional [!DNL Experience Cloud] integrations, or will in the future, this is probably not the option for you.

Finally, and perhaps most importantly, this `amp-analytics` solution requires that the tracking server you specify in the `vars` section matches the tracking server on your main site, so that your existing privacy policy controls are respected. Otherwise, you must create a separate privacy policy just for AMPs.

## Using the amp-analytics tag with the "adobeanalytics_nativeConfig" template {#section_3556B68304A4492991F439885727E9FF}

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it will use the same tagging methodology you use on your normal web pages. To accomplish this, add the following to your `amp-analytics` tag:

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  

```

This approach sends data to a utility web page via special query string parameters added to the `iframeMessage` request parameter. In this case, notice that we have added the `ampdocUrl AMP` variable, and the `documentReferrer` to the query string parameters `pageURL`, and refer respectively to the `iframeMessage` request above. These extra query string parameters can be named whatever you like, as long as your [!DNL stats.html] page (shown below) is configured to collect the appropriate data from them.

The `"adobeanalytics_nativeConfig"` template also adds query string parameters based on the variables listed in the `extraUrlParams` section of the amp-analytics tag. In this case, you can see we have specified the `pageName` and `v1` parameters , which will be used by our [!DNL stats.html] page.

Be aware that you can only use a single `amp-analytics` template at a time and can not use the `"adobeanalytics"` template as well as the `"adobeanalytics_nativeConfig"` template on the same AMP. If you attempt to do so, you might see an error in the browser console, and you will erroneously inflate your visitor count.

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam("ref"); 
s.t(); 
</script> 
</body> 
</html> 

```

As shown above, you can use or link to your existing [!DNL VisitorAPI.js] and [!DNL AppMeasurement.js] (as in our example), or whatever your existing implementation uses, then add the correct configuration parameters. To capture the correct values into the correct variables, you can use the provided `s.Util.getQueryParam` function to grab the value(s) that you passed in from the `iframeMessage` URL and set the appropriate variables, just as you would on a typical page. If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. In this case, `s.pageName` is set to the value we passed in the query string parameter `pageName`. Here, the page name would be set to *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>Due to restrictions on iframes in the AMP framework, your [!DNL stats.html] page must be hosted on a separate subdomain from the domain the AMP itself is hosted on. The AMP framework does not allow for iframes from the same subdomain that the AMP page itself exists on. For example, if your AMP is hosted on [!DNL amp.example.com], be sure to host your [!DNL stats.html] page on a separate subdomain such as [!DNL ampmetrics.example.com] or something similar.

Because the utility page is hosted on your original site, no additional work is needed to support your existing privacy policy across all AMPs. This means that if an end user opts out of tracking on your primary site, they are also opted out of tracking on all your AMPs, with no additional steps required. Using this utility page also means that AMP can support Adobe's [!DNL Experience Cloud] ID service so that you can integrate the measurement captured on your AMPs with the rest of the [!DNL Experience Cloud] (for targeted advertising using [!DNL Adobe Audience Manager] for example).

To reiterate, if your organization is not yet using the [!DNL Experience Cloud] ID service (or has tag management software like Adobe's [!DNL Dynamic Tag Manager]), you can tag the [!DNL stats.html] page however you want. Use your existing implementation as a reference point. The only difference from your standard implementation is that you will get the applicable data points from the amp-analytics `iframeMessage` URL (or [!DNL document.URL] from within the [!DNL stats.html] page ) for each of the variables you want to set. Also, if you want to use any of the [AMP specific variables](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (as mentioned above) like the AMP referrer or AMP page URL, please include them in the iframeMessage object as shown in our example above.

As flexible as this solution is, there are caveats. Due to inherent restrictions in the `amp-analytics` `iframeMessage`, it can only be loaded on a page load once. This means you will not be able to do link tracking or video tracking with the `"adobeanalytics_nativeConfig"` template. Moreover, some DOM values that are typically captured automatically by our [!DNL AppMeasurement] code, such as `referrer` (which impacts the Search Engine Keyword reports, Referrer, and Referrer Type reports, or may include a marketing campaign tracking code) will have to be passed manually to the `iframeMessage` using whatever AMP variables [are available](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). For this reason, Adobe recommends setting a custom variable with the value AMP if you put AMP data into an existing report suite, so that you can segment out AMP traffic when viewing the aforementioned reports. That said, standard technology reports, such as browser, device, screen size or resolution, should work automatically.

Finally, because the iframe loads as a separate page and fully executes the JavaScript on that page, the AMP is not as lightweight as the AMP standard intended. To be clear, this does not affect page load time (the iframe loads after the page is done loading), but the CPU and network will be doing slightly more than they otherwise would, which might impact scrolling smoothness. In practice, we have not seen a large impact, but we are working with Google to minimize the user experience impact of this approach.

## Summary {#section_4D8ED26084F249738A5C2BC66B933A07}

If you need click tracking and don't mind visitors being counted as entirely new visitors separate from your site, use the `"adobeanalytics"` tracking template, with our recommendation that you put the data into a *`separate report suite`*. If you need the [!DNL Experience Cloud] ID service, do not want visitor or visit inflation, and are okay with only firing Analytics on page load, we recommend using the `"adobeanalytics_nativeConfig"` solution.

Adobe Analytics is excited to partner with Google and our publishers to bring industry leading analytics capabilities to publishers on the mobile web in a blazing fast user experience. Although these two solutions currently offer their own tradeoffs, we are committed to building the best long term solution to answer the evolving analytics needs our customers have.

The AMP Project is moving fast and changes occur frequently, so check back [here](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) frequently for updates to our examples. What we've shown you here should be enough to get started, but expect changes as we improve our integrations further and as more publishers adopt AMP over time.

If you have questions or problems, please reach out to your Adobe Consultant or Customer Care.

## Frequently Asked Questions {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> Unfortunately, not yet. The AMP standard supports only triggers for "visible", "click", and "timer", and does not yet support explicit triggers for video tracking that can be listened to by the amp-analytics tag. Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You mention that visitor inflation is lower for the " <code> adobeanalytics_nativeConfig </code>" template in your comparison. What does that mean? What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> "adobeanalytics_nativeConfig" </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> "adobeanalytics" </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> "adobeanalytics_nativeConfig" </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. This means that any visitors from Safari who have not previously visited a publisher's site will be inflated in Adobe Analytics reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Should I use a separate report suite for AMPs? </p> </td> 
   <td colname="col2"> <p>We recommend using a separate report suite for AMPs if you use the adobeanalytics template, because of the visitor/visit inflation issue. However, we will also set the JavaScript version to "AMP vX.X" from the amp-analytics tag template so that you can segment that traffic out of a combined report suite if necessary. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What is the <span class="keyword"> Experience Cloud </span> ID service? Do I need it? </p> </td> 
   <td colname="col2"> <p>The <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"  > Identity Service </a> (formerly <span class="term"> visitor ID service </span>) enables <span class="keyword"> Experience Cloud </span> core services and allows integrations between different Adobe <span class="keyword"> Experience Cloud </span> solutions. If you have integrations with <span class="keyword"> Adobe Audience Manager </span> or <span class="keyword"> Adobe Target </span>, you are likely using this service. This service is also the foundation for many upcoming <span class="keyword"> Adobe Analytics </span> features. If you need ID service support or will need it in the future, we recommend using the <code> iframeMessage </code> solution. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>The AMP standard does not allow for iframes to load from the exact domain and subdomain of the AMP itself. As such, we recommend that you host the utility page on a separate subdomain from your main site, especially if your company has its own CDN that plans on caching AMPs. For maximum compatibility, pick a subdomain such as <span class="filepath"> ampmetrics.publisher.com </span> that is apart from where the actual AMP content will reside. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Isn't this similar to <span class="keyword"> Facebook Instant Articles </span>? How do I setup <span class="keyword"> Adobe Analytics </span> with Facebook Instant Articles? </p> </td> 
   <td colname="col2"> <p> Facebook Instant Articles support a similar solution to the nativeConfig solution outlined above. In fact, the stats.html page created above can serve your analytics needs for both AMP and FIA simultaneously. For more information on implementing tracking on FIA, see <a href="/help/implement/js-implementation/analytics-facebook-instant-articles.md"  > Facebook Instant Articles </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

