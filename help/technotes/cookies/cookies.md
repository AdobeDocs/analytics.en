---
title: Adobe Analytics and browser cookies
description: Learn how tracking prevention measures affect third-party and first-party cookies set by Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
---
# Adobe Analytics and browser cookies

This document explains how major browsers' tracking prevention measures affect the third-party and first-party cookies set by Adobe Analytics. It includes information about Apple's Intelligent Tracking Prevention (ITP) program as well as Chrome's limitations on third-party cookies via the SameSite attribute.

## How have browsers limited the usage of cookies?

>[!NOTE]
>[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en#cda) and [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#comparing-cja-to-traditional-adobe-analytics) can stitch across cookies using a person ID, such as a hashed login id, if one is available.

### Third-party cookie limitations

Cookies used in a third-party context are being widely deprecated. Firefox and Safari started blocking third-party cookies by default starting in 2019 and 2020, respectively. Chrome has announced plans to stop supporting third-party cookies sometime in 2023. When they do, third-party cookies will effectively be unusable.

Additionally, Chrome currently only allows cookies to function in a third-party context if they have the "SameSite" attribute set to None and the are labelled as secure, meaning they can only be used over HTTPS. More information is available in the section "[What is the SameSite cookie attribute, and how does it affect Analytics?](#samesite-effect)"

#### Which Adobe third-party cookies are affected?

The Visitor ID service uses the "[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)" cookie to provide a persistent identifier for visitors across different customer domains. The legacy Analytics ID service, the "s_vi" cookie, is set as a third-party cookie for implementations not using a custom CNAME collection domain. 

On browsers where third-party cookies are blocked, cross-domain tracking is not available.

### First-party cookie limitations {#limitations-first-party-cookies}

First-party cookies are permitted on all major browsers. However, Apple limits the lifespan of first-party cookies set by Adobe through their Intelligent Tracking Program (ITP). This affects Safari as well as all browsers on iOS and iPadOS.

Adobe's first-party cookies are limited to a 7-day expiry or, for click-throughs that Apple determines are coming from trackers, a 24-hour expiry. With a 7-day expiry, if a user visits your site and returns within seven days, then the cookie's expiration date is extended by another seven days. However, if a user visits your site and returns in eight days, then they are treated as a new user on the second visit.

Currently, ITP policies apply to all first-party cookies set by Adobe, whether you're using the Visitor ID service or the legacy Analytics ID ("s_vi" cookie). At one point, these policies applied only to cookies set client-side and not to cookies set server-side via a CNAME implementation. In November of 2020, however, ITP was updated to apply to CNAME implementations as well.

#### Timeline of major changes to ITP policy {#ITP-timeline}

* February 2019 with [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Client-side cookies were limited to a seven-day expiry
* April 2019 with [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Client-side cookies were limited to 24 hours for ad clicks when the referring domain was a) involved in cross-site tracking and b) the final URL contained a query string and/or a fragment identifier.
* November 2020 with [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): ITP limitations were extended to CNAME implementations.
   
ITP policies are frequently evolving. For the latest policies, see Apple's [Tracking Prevention in Webkit](https://webkit.org/tracking-prevention).

#### Which Adobe first-party cookies are affected?

All first-party cookies set by Adobe, and the related JavaScript libraries, are affected by ITP policies:

* ["AMCV" cookies](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) set by the Adobe Experience Cloud Visitor ID (ECID) service library
* The Analytics legacy ["s_vi" cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) when it is configured with first-party data collection using a CNAME
* The Analytics legacy ["s_fid" cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html), which is the fallback cookie used when "s_vi" cannot be set

#### What is the impact of ITP to Safari for Analytics? 

The impact of the ITP limitations can vary significantly, depending on your users' behavior. Only visitors who use an ITP-impacted browser (for example, Safari) and return after a seven-day absence are affected. If visitors do not use an ITP browser or return within seven days, they are unaffected. It is important to review your own data in Analytics to understand the extent of the impact of this limitation. For tips on how to measure the impact to your sites, see "[How can I determine if Safari changes affect my business?](#measure-itp-effect)"

If these limitations do impact your data, you will see:

1. Increased Visitor counts as returning visitors are treated as new visitors because their cookies have expired. Any metrics based on the Visitor metric (such as Sales per Visitor) are also impacted.
2. Changes to attribution. Attribution relies on tying conversion events to preceding activities by the same visitor. Once a cookie expires, subsequent events are associated with a new visitor. The activities of the new visitor cannot be tied to the activities of the previous visitor.

>[!NOTE]
>
>ITP technologies currently do not apply to embedded browsers in mobile apps.

## What is the difference between third-party cookies and first-party cookies?

### Third-party cookies

Third-party cookies are not created by the websites that users visit.

Although browsers currently treat all third-party cookies the same and store them so, third-party cookies can behave in different ways. With a customer’s Analytics third-party cookie implementation, browsers store the Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) ID as a third-party cookie, but the client makes calls only to Adobe, and not too unknown or suspicious third-party domains. This cookie provides persistent identifiers across domains and allows for secure (HTTPS) content. For more information, see [Cookies and the Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

Within Analytics implementations, third-party cookies are used for cross-domain tracking and for advertising use cases, including retargeting ads. Third-party cookies allow you to identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### First-party cookies

First-party cookies are domain-specific and are created by customer websites and stored in client browsers as users visit the websites. All browsers generally accept first-party cookies, although [Safari limits the expiry of some types of first-party cookies](#limitations-first-party-cookies).

Within Analytics implementations, first-party cookies are used to identify users when they are on your site and therefore support all analysis of user activity. You don't need third-party cookies to understand on-site activity.

For more information, see [About first-party cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

![Cookie comparison](/help/technotes/assets/cookies2.png)

## What is the SameSite cookie attribute, and how does it affect Analytics cookies? {#samesite-effect}

With the release of the Chrome 80 browser in February 2020 &mdash; and successive versions of Firefox and Edge browsers &mdash; the SameSite cookie attribute enforces the specification for three different values that govern whether cookies can be used in a third-party context:

* `None`: This setting enables cross-site access and enables cookies to be passed in a third-party context. To specify this attribute, you must also specify `Secure` and all browser requests must follow HTTPS. For example, when setting the cookie, you pair the values of the attribute as follows: `Set-Cookie: example_session=test12; SameSite=None; Secure`. If not labelled properly, the cookies are unusable to the newer browsers and are rejected.

* `Lax`: Allows cross-site requests to be sent with same-site cookies only for top-level navigation with *safe* (read-only, such as `GET`) HTTP methods.

* `Strict`: The same-site cookie is not sent for any third-party website requests. The cookie is only sent if the site for the cookie matches the site in the URL bar.

The default behavior in these browser versions is to treat cookies that have no specified `SameSite` attribute the same as `SameSite=Lax`.

### How does Analytics manage SameSite cookie attributes?

For customers using the Visitor ID Service, cookies have the properties `SameSite=None` and `secure` set by default, which allows these cookies to support third-party use cases.

For customers using Analytics legacy identifiers ("s_vi" and "s_fid" cookies), cookies are also set to enable third-party use cases with standard collection domains: adobedc.net, 2o7.net, and omtrdc.net. For customers using a CNAME implementation, Analytics sets `SameSite=Lax`.

>[!NOTE]
>
>If you own multiple domains and use the same CNAME for data collection across all of your domains, then the cookie is treated as a third-party cookie on those other domains. If you are using the legacy Analytics identifiers, then you may want to update your setting to `SameSite=None` so that these cookies can be shared across your sites. See "[Change the SameSite value when you use one CNAME for multiple domains](#samesite-one-cname)" in the next section for more information.

For browsers that Google has identified as mishandling cookies when `SameSite` is set to `None`, `SameSite` is instead left unset.

The following table summarizes the SameSite attributes for Analytics cookies:

![Cookie table](/help/technotes/assets/cookies1.png)

### How can my site address requirements for the SameSite attribute?

#### Serve all of your site pages with HTTPS

Confirm that your JavaScript configuration uses HTTPS for all calls to Adobe services.

If your site uses the Experience Cloud Visitor ID service, the service redirects third-party HTTP calls to its HTTPS endpoint, which can increase latency but means that you are not required to change your configuration.

#### Change the SameSite value when you use one CNAME for multiple domains {#samesite-one-cname}

>[!NOTE]
>
>The following information pertains only to sites that do not use the Experience Cloud Visitor ID service.

If you have a CNAME implementation that is set in the same domain as your website, then the cookie is created in a first-party context, and you do not need to make changes.

However, if you own multiple domains and use the same CNAME for data collection across all your domains, then the cookie is treated as a third-party cookie on those other domains. With Chrome 80 and higher, it is no longer visible on these other domains. To make the behavior more similar across all browsers, Analytics has explicitly set the `SameSite` value of this cookie to `Lax`. If you use this cookie in a friendly third-party context, then you must have the cookie set with the `SameSite=None` value, which also means you must always use HTTPS. If you have not already done so, then contact Adobe Customer Care to have the SameSite value changed for your secure CNAMEs.

## How can I determine if Safari changes affect my business? {#measure-itp-effect}

Adobe recommends that customers measure the impact within their own company before changing data collection. You can use Analysis Workspace to measure the impact of ITP tracking prevention on your individual business:

* Measure the percentage of your traffic from ITP-governed browsers:

   1. Create a segment to see how many visitors are using an ITP platform.
   
       >[!NOTE]
       >
       >The specific browsers impacted by ITP depends on whether you were using a CNAME implementation. See "[Timeline of major changes to ITP policy](#ITP-timeline)" for more detail.

       ![Segment for ITP visitors](/help/technotes/assets/itp-visitor-segment.png)

   2. Apply the segment to the number of visits to understand the relative usage of Safari in your user base. This lets you create a table like this:
   
       ![Percentage of visits by ITP visitors](/help/technotes/assets/visits-vs-safari-visits.png)

* Measure the percentage of visitors using non-Safari browsers who do not return within seven days. If your non-Safari visitors return repeatedly within seven days, your Safari traffic may not be significantly affected.

   1. Create a segment like the following for non-Safari traffic.

       ![Segment for visitors who return after seven days](/help/technotes/assets/visits-after-seven-days.png)

   2. Apply the segment to the number of visits to understand the relative usage of Safari in your user base. This lets you create a table like this:
   
       ![Percentage of visitors who return after seven days](/help/technotes/assets/percent-visits-after-seven-days.png)

### Ways to adjust your data during reporting

If your business is affected by ITP tracking prevention, you might consider the following measures to adjust your data during reporting.

* Create a segment to filter out ITP users.

    ![Segment for non-ITP visitors](/help/technotes/assets/non-itp-visitor-segment.png)

* Create a calculated metric to adjust for known visitor inflation.

    ![Calculated metric to adjust for visitor inflation](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Options to mitigate the effect of browser cookie limitations](cookieless.md)
>[The Impact of Apple's New App Tracking Transparency Framework on Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
