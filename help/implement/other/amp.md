---
title: Implementing with AMP
description: Implement Adobe Analytics on AMP pages.
---

# Implementing with AMP

[AMP](https://amp.dev) is an open-source HTML framework that provides a straightforward way to create fast and smooth-loading web pages.

Since Adobe Analytics uses a JavaScript library to compile and send an image request, adjustments are required in your implementation to send data to Adobe on pages using AMP.

## Determine which method to implement Adobe Analytics on pages using AMP

Adobe has created two methods to implement Adobe Analytics on pages using AMP. Both use the `<amp-analytics>` HTML tag. See [amp-analytics tag](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) on the ampproject GitHub for more information.

* **Use the `"adobeanalytics"` tracking template**: Construct the Analytics request directly on the page
* **Use the `"analytics_nativeConfig"` tracking template**: Use an iframe containing the same AppMeasurement code you deploy on your normal site

The following table compares these two methods:

|   | **"adobeanalytics" template** | **"adobeanalytics_nativeConfig" template** |
|---|---|---|
| Visitor/visit counts in existing report suite | High inflation | Minimal inflation |
| Use a separate report suite | Recommended | Not necessary |
| New vs. return visitors | Not supported | Supported |
| Visitor ID service | Not supported | Supported |
| Video and link tracking | Partial support | Not yet supported |
| Difficulty of implementation | Somewhat difficult | Relatively easy |
| Adobe Experience Cloud integrations | Not supported | Partial support |

Weigh the pros and cons within your organization to determine which method you want to use.

> [!WARNING] Do not use both the `"adobeanalytics"` and `"adobeanalytics_nativeConfig"` templates on the same AMP. If you attempt to do so, you can generate errors in the browser console and double-count visitors.

## Method 1: Use the amp-analytics tag with the "adobeanalytics" template

The `"adobeanalytics"` tracking template uses the `<amp-analytics>` HTML tag to construct a tracking request directly. You can specify hit requests that fire on specific page events, like the page becoming visible or on a click. Click events can be customized to apply to certain element IDs or classes by specifying a selector. You can load the template by adding `type="adobeanalytics"` to the amp-analytics tag.

In the following code example, there are two triggers defined: `pageLoad` and `click`. The `pageLoad` trigger fires when the document becomes visible and includes the `pageName` variable as defined in the `vars` section. The second trigger `click` fires when a button is clicked. `eVar1` is set for this event with the value `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
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

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and is automatically set to denote this hit as a link tracking call.

Additionally, `amp-analytics` supports a number of variable substitutions so that AMP can provide data values that it is aware of. See [variables supported in amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) on GitHub for more information.

> [!NOTE] Image requests send to Adobe using this method does not include data for many default reports (for example, browser, screen size, or referrer). If you want to include this information in hits, make sure they are included as part of the image request query string. See [Data collection query parameters](../validate/query-parameters.md) for more information.

Adobe identifies visitors using a built-in AMP function, and sets the cookie `adobe_amp_id`. This visitor ID is unique to any other ID  set by Adobe Analytics (for example, the `s_vi` cookie). The Adobe Experience Cloud ID Service is not supported using this implementation method.

> [!NOTE] AMP uses CDN's to deliver content. It is structured to count a different unique visitor for each CDN a visitor retrieves content from, which can inflate unique visitor count.

Using a separate report suite for AMP pages is recommended because of how AMP identifies unique visitors.

This solution requires that the tracking server you specify in the `host` property matches the tracking server on your main site, so that your existing privacy policy controls are respected. Otherwise, create a separate privacy policy for pages using AMP.

## Method 2: Use the amp-analytics tag with the "adobeanalytics_nativeConfig" template

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it uses the same tagging methodology you use on your normal web pages. Add the following to your `amp-analytics` tag:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

An HTML page hosted on your web servers is also required:

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;
      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

This approach sends data to a utility web page through query string parameters added to the `iframeMessage` request parameter. These query string parameters can be named whatever you like, as long as your `stats.html` page is configured to collect data from them.

The `"adobeanalytics_nativeConfig"` template also adds query string parameters based on the variables listed in the `extraUrlParams` section of the amp-analytics tag. In the above example, the `pageName` and `v1` parameters are included.

> [!IMPORTANT] Your `stats.html` page must be hosted on a separate subdomain from the domain the AMP itself is hosted on. The AMP framework does not allow for iframes from the same subdomain that the AMP page itself exists on. For example, if your AMP is hosted on `amp.example.com`, host your `stats.html` page on a separate subdomain such as `ampmetrics.example.com`.

Using this method, if a user opts out of tracking on your primary site, they are also opted out of tracking on all your AMPs. Using this utility page also means that AMP can support the Adobe Experience Cloud ID Service. A separate report suite is not required.


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

