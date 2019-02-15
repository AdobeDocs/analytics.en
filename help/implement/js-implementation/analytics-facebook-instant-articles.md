---
description: How to implement Analytics in Facebook Instant Articles.
keywords: Analytics Implementation;embed;custom variable;custom event;visitor tracking;tracking;limitations
seo-description: How to implement Analytics in Facebook Instant Articles.
seo-title: Facebook Instant Articles
solution: Analytics
title: Facebook Instant Articles
topic: Developer and implementation
uuid: 04b6366b-7c52-4dae-b2dd-bb6b78fd409c
---

# Facebook Instant Articles

How to implement Analytics in Facebook Instant Articles.

Facebook Instant Articles is a new method for publishers to build fast, interactive articles on Facebook. Instant Articles can load content up to 10 times faster than mobile web.

Adobe Analytics can be embedded within the Facebook Instant Articles to track visitor behavior as they interact with the content. Because publisher content is within the Facebook app and not on the publisher's websites, the tagging approach is slightly different than a standard Analytics implementation.

## Step 1. Embed an Analytics HTML page {#section_0DF847F8BA624CF8A239C10003A39E59}

When creating your Facebook Instant Article content, you can embed the analytics HTML content within an iFrame. For example:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## Step 2. Modify your Analytics HTML {#section_76707B51D63A47FF833C2D3FFF8412B4}

The sample HTML below can be used to capture stats from the instant articles. This file would typically be hosted on one of your company's web servers. Each time an Instant Article is loaded, it loads the file in an iframe as outlined in step one, which triggers sending the analytics data to Adobe.

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**To modify this sample HTML for your specific implementation**

1. It is recommended to host the latest copies of unmodified versions of the VisitorAPI.js and AppMeasurement.js on a common directory on your company's web servers.

   These files can also be downloaded from within the Code Manager in the Analytics UI if required. 

1. Include your Analytics implementation standard configuration variables:

    1. Your Experience Cloud Org ID. 
    1. The report suite ID where the Facebook Instant Article traffic will be captured. 
    1. Your company's tracking server domain. 
    1. Your visitor namespace variable. **Note:** Many of these values can be found within your standard Analytics implementation. Customer Care or Adobe Consulting can assist in providing the proper values if necessary.

1. [Set custom variable and event tracking](../../implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B). 
1. Include the page view image request syntax `( s.t())`.

## Step 3. Set custom variable and event tracking {#section_932C41BD21154C25B99389299BDF3E0B}

Custom variables and events can be tracked within your analytics HTML via different approaches. The first approach is to include JavaScript logic in your custom configuration, similar to what you might do with a standard Analytics implementation. For example, to set the value of a prop, simply use the same syntax that you would use in a normal implementation:

```
s.prop10 = "Facebook Instant Article";
```

You can also dynamically send variables to the iframe by leveraging query string parameters in the iframe `src` attribute. For example:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

Those query string parameters can subsequently be set in the custom variables section of your analytics HTML JavaScript by using the `Util.getQueryParam` function within the default [!DNL AppMeasurement] library, as follows:

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## Visitor Tracking {#section_60F0C77659534949831E85B5FD9AE81E}

As long as the Analytics HTML page is hosted on your web server, Adobe can support your existing privacy policy across all Facebook Instant Articles. This means that if an end user has opted out of tracking on your primary site, they will also be opted out of tracking on all your Facebook Instant Articles, with no additional steps required. Using this utility page also means that the Experience Cloud ID service (visitor ID) is supported so that you can integrate the metrics and variables captured on your Facebook Instant Articles with the rest of the Experience Cloud. (An example is for targeted advertising using [!DNL Adobe Audience Manager]).

## Tracking Limitations {#section_1EE1BB069A3148DB9446371AFE196567}

There are few issues that should be noted with this approach. Any DOM values that are typically only accessible via JavaScript on the Facebook Instant Article (such as referrer) will not be retrievable in the iframe for tracking. However, standard technology reports like browser, device, screen size or resolution should work normally. Moreover, the pageURL can be obtained by referencing [!DNL document.referrer] from your utility page.

## What's Next? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] is excited to partner with Facebook and our publishers to bring industry leading analytics capabilities to publishers on the mobile web in a blazing fast user experience. We are committed to building the best long term solution to answer the evolving analytics needs our customers have.

The Facebook Instant Article project is moving quickly and changes are happening all the time, so check back with us frequently for updates. Expect changes as we improve our integrations further and as more publishers adopt Facebook Instant Articles in the future.

If you have questions or problems, please reach out to your Adobe Consultant or Customer Care. 
