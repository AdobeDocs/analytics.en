---
title: RDC Environment Characteristics
seo-title: Adobe Analytics RDC Environment Characteristics
description:
seo-description: 
---

# RDC Environment Characteristics

## Performance improvements

For current response times when using RDC, see [Adobe Analytics Request Performance](https://marketing.adobe.com/resources/help/en_US/whitepapers/performance/). 

Generally, users can expect response time improvements with RDC as follows:

| Regions | Response Time Removed by RDC |
| --- | --- |
| Asia | 36% |
| Australia | 5% |
| China and Russia | 41% |
| Japan | 41% |
| Europe | 83% |
| British Isles | 94% |
| Central and Eastern Europe | 84% |
| Northern Europe | 73% |
| Western Europe | 89% |
| North America | 38% |
| Canada | 26% |
| Central US | 48% |
| Eastern US | 46% |
| Western US | 20% |
| Global | 50% |

## First- or Third-Party Cookies

Depending on your implementation, you might be using first- or third-party cookies. You can learn more about first-party cookies [here](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_overview.html).

## Secure Pages

If your site contains pages that use the https: protocol, you have secured pages. These types of pages are typically used with ecommerce or login/account pages.

Secure pages require an SSL certificate for tracking. If your web property is currently using first-party cookies, you should have already created an FPSSL implementation with [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html). If your web property is using third-party cookies, your secure pages use a SSL certificate owned by Adobe, which allows data to be sent to our data collection servers securely without an FPSSL implementation.

## RDC detection method

If your web property uses first-party SSL that [CNAMES](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) to `2o7.net` your hostname is not fully enabled for RDC. Contact [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) if you want to move your hostname to RDC.

## DNS changes (CNAME update)

A [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) update is a change made to your company's DNS server. Your IT department or network operations team typically handles this operation. If your scenario requires this change, you should contact Customer Care for the new Adobe hostname.

If your site does not have secure pages and therefore no FPSSL implementation, an incorrect hostname could result in unrecoverable data loss.

## Additional considerations

If your implementation is part of an intranet site and relies on white-listing the `2o7.net` domain, you will need to also white-list the `omtrdc.net` version of the hostname on your firewall.
