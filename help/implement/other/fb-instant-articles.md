---
title: Implementing with Facebook Instant Articles
description: Implement Adobe Analytics on Facebook Instant Article pages.
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
---
# Implementing with Facebook Instant Articles

Facebook Instant Articles allow publishers to build fast, interactive articles on Facebook. Instant Articles can load content up to 10 times faster than mobile web.

You can embed Adobe Analytics on Facebook Instant Articles to track visitor behavior. Since publisher content is within the Facebook app and not on the publisher's websites, the tagging approach is slightly different than a standard Analytics implementation.

## Workflow

The overarching workflow to implement Adobe Analytics is the following:

1. Create a `stats.html` page. Code this page to pull query string parameters from the URL and assign each parameter to an Analytics variable
1. Host the `stats.html` page on your web server
1. Implement Analytics on the Facebook Instant Article by referencing the `stats.html` file in an iframe
1. Include query sting parameters in the iframe `src` attribute

### Step 1: Create a `stats.html` page

The sample HTML below can be used to capture stats from the instant articles. This file would typically be hosted on one of your company's web servers. Each time an Instant Article is loaded, it loads the file in an iframe, which triggers sending data to Adobe.

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
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
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### Step 2: Host the `stats.html` page on your web server

Adobe recommends hosting your `stats.html` page alongside the latest version of `AppMeasurement.js` and `VisitorAPI.js`. Work with the appropriate engineering teams in your organization to host this file in the correct location.

### Step 3: Reference `stats.html` on each Facebook Instant Article page

When creating Facebook Instant Article content, embed the analytics HTML content within an iframe. For example:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Step 4: Set custom variable and event tracking

Custom variables and events can be tracked within your analytics HTML through two different approaches:

* Include variable values and events directly in the `stats.html` page. Variables defined here would be best for values that are typically the same for all Facebook Instant Articles.
* Include variable values as part of a query string referencing the iframe. This method allows you to send variable values from the Facebook Instant Article to the iframe hosting Analytics code.

The following example shows several custom variables included in a query string. The JavaScript inside `stats.html` would then check the query string using `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>The Referrer dimension is not automatically tracked due to the nature of iframes. Make sure that you include this dimension as part of your query string if you want to track it.

## Facebook Instant Articles and privacy

As long as the Analytics HTML page is hosted on your web server, Adobe supports your existing privacy policy across all Facebook Instant Articles. If a user opts out of tracking on your primary site, they also opt out of tracking on all your Facebook Instant Articles. The utility page also supports the Adobe Experience Cloud Identity Service so that you can integrate Facebook Instant Article data with the rest of the Experience Cloud.
