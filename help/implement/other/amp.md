---
title: Implementing with AMP
description: Implement Adobe Analytics on AMP pages.
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
---
# Implementing with AMP

[AMP](https://amp.dev) is an open-source HTML framework that provides a straightforward way to create fast and smooth-loading web pages.

Since Adobe Analytics uses a JavaScript library to compile and send an image request, adjustments are required in your implementation to send data to Adobe on pages using AMP.

## Determine which method to implement Adobe Analytics on pages using AMP

Adobe has created two methods to implement Adobe Analytics on pages using AMP. Both use the `<amp-analytics>` HTML tag. See [amp-analytics tag](https://amp.dev/documentation/components/amp-analytics) on AMP's documentation for more information.

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

Weigh the pros and cons within your organization to determine which method you want to use. See [AMP examples](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) on Adobe's GitHub repository for sample code.

>[!WARNING]
>
>Do not use both the `"adobeanalytics"` and `"adobeanalytics_nativeConfig"` templates on the same page using AMP. If you attempt to do so, you can generate errors in the browser console and double-count visitors.

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
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
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

>[!NOTE]
>
>Image requests send to Adobe using this method does not include data for many default reports (for example, browser, screen size, or referrer). If you want to include this information in hits, make sure they are included as part of the image request query string. See [Data collection query parameters](../validate/query-parameters.md) for more information.

Adobe identifies visitors using a built-in AMP function, and sets the cookie `adobe_amp_id`. This visitor ID is unique to any other ID  set by Adobe Analytics (for example, the `s_vi` cookie). The Adobe Experience Cloud ID Service is not supported using this implementation method.

>[!NOTE]
>
>AMP uses CDN's to deliver content. It is structured to count a different unique visitor for each CDN a visitor retrieves content from, which can inflate unique visitor count.

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
        "host": "example.data.adobedc.net"
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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

>[!IMPORTANT]
>
>Your `stats.html` page must be hosted on a separate subdomain from the domain the AMP itself is hosted on. The AMP framework does not allow for iframes from the same subdomain that the AMP page itself exists on. For example, if your AMP is hosted on `amp.example.com`, host your `stats.html` page on a separate subdomain such as `ampmetrics.example.com`.

Using this method, if a user opts out of tracking on your primary site, they are also opted out of tracking on all your AMPs. Using this utility page also means that AMP can support the Adobe Experience Cloud ID Service. A separate report suite is not required.

Link tracking and video tracking cannot be used with this method. The `iframeMessage` tag in AMP can only load once per page, so you cannot send any other image requests after the frame loads. This method also requires more processing resources to run, which can impact scrolling performance. This method does not affect page load time, since all resources load asynchronously.

## FAQ

**Is video tracking available for either method?**

No. The AMP standard supports only triggers for "visible", "click", and "timer". It does not yet support explicit triggers for video tracking that the `amp-analytics` tag can listen to. Also, the `"adobeanalytics_nativeConfig"` template can only load once, so subsequent image requests after a page loads is not possible.

**How can I differentiate AMP visitors from others in my data?**

For all AMP pages, the [!UICONTROL JavaScript Version] dimension collects a value similar to `AMP vX.X`. You can also set a custom dimension to 'AMP' so you can segment these visitors.

**How does this implementation method compare to Facebook Instant Articles?**

Facebook Instant Articles support a similar solution to the `"adobeanalytics_nativeConfig"` method. The `stats.html` page for this method can serve your analytics needs for both AMP and FIA simultaneously. For more information on implementing tracking on FIA, see [Facebook Instant Articles](fb-instant-articles.md).
