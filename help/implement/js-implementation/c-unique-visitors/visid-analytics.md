---
description: When a user visits your site, a persistent cookie is set by the Adobe web server by including it in the HTTP response to the browser. This cookie is set on the specified data collection domain.
keywords: Analytics Implementation
title: Analytics Visitor ID
topic: Developer and implementation
uuid: fa7737cc-0190-4d27-af1b-87301a715df2
---

# Analytics Visitor ID

When a user visits your site, a persistent cookie is set by the Adobe web server by including it in the HTTP response to the browser. This cookie is set on the specified data collection domain.

When a request is sent to the Adobe data collection server, the header is checked for the visitor ID cookie ( `s_vi`). If this cookie is in the request, it is used to identify the visitor. If the cookie is not in the request, the server generates a unique visitor ID, sets it as a cookie in the HTTP response header, and sends it back with the request. The cookie is stored in the browser and is sent back to the data collection server during subsequent visits the site, which enables the visitor to be identified across visits.

## Third-Party Cookies and CNAME records {#section_61BA46E131004BB2B75929C1E1C93139}

Some browsers, such as Apple Safari, no longer store cookies that are set in the HTTP header from domains that do not match the domain of the current website (this is a cookie used in a third-party context, or a third-party cookie). For example, if you are on `mysite.com` and your data collection server is `mysite.omtrdc.net`, the cookie that is returned in the HTTP header from `mysite.omtrdc.net` might be rejected by the browser.

To avoid this, many customers have implemented CNAME records for their data collection servers as part of a [first-party cookie implementation](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). If a CNAME record is configured to map a hostname on the customer's domain to the data collection server (for example, mapping `metrics.mysite.com` to `mysite.omtrdc.net`), the visitor ID cookie is stored since the data collection domain now matches the domain of the website. This increases the likelihood that the visitor ID cookie will be stored, but it introduces some overhead as you need to configure CNAME records and maintain SSL certificates for data collection servers.

## Cookies on Mobile Devices {#section_7D05AE259E024F73A95C48BD1E419851}

When mobile devices are tracked using cookies, there are some settings you can use to modify how measurement occurs. Cookie default lifetime is 5 years, but you can use the CL query param variable ( `s.cookieLifetime`) to change this default. To set the cookie location for cname implementations, use the CDP query string `s.cookieDomainPeriods`. The default is 2 if no value is specified. and the default location is domain.com. For implementations that do not use CNAME, the visitor ID cookie location is at the 207.net domain.
