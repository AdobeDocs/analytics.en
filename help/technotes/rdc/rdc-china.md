---
title: Regional Data Collection for China
seo-title: Adobe Analytics China RDC
description:
seo-description:
---

# Regional Data Collection for China

Adobe's Regional Data Collection (RDC) in mainland China enables customers within China to send data directly to a Data Collection Center (DCC) within China, instead of other locations globally. This improves page load times and data accuracy over sending the data to DCCs outside of China.

## Setting the tracking server for China

Tracking can be brought on to China RDC at any point that is convenient for your service. For any digital property (such as a mobile app or web page) you want routed to China RDC, change the tracking server to:

`<namespace>.sc.adobedc.cn`

Be sure to insert the proper namespace. This is typically found at the beginning of your existing tracking server. For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. You can also point a non-SSL first-party [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) record to this new location.

Do not set your trackingServer value globally, for all properties and geographies, to the China RDC if any substantial part of your customer base is outside of China. The trackingServer should be set to the China RDC value only for customers who are in China. Otherwise, it will negatively affect the speed for your users outside China because it forces data collection to go to China and back for a response.

## Identifying users in China

Regardless of where your digital property is hosted, or which language it uses, your users in China will experience improvements if you are using the RDC node in China. Thus, the recommended practice is to determine which users are located in China and then use China RDC for those users. Methods that might help you to identify these users include:

* Using a reliable GeoIP solution.  You might decide to use a server-side solution to easily integrate with Launch (or Data Tag Management). In this case, the location can be determined by including a standard data element in the Launch or DTM object. Or, you might use a client-side GeoIP solution. In this case, Launch can be hooked into the client-side code. Note that such solutions may involve prompting the user to navigate to the localized site. This presents a risk that the first page is counted by the global tracking server and the second page by the one in China, which can result in a double-counted visit. Follow best practices for GeoIP solutions. Adobe is not responsible for the accuracy of the GeoIP solution you use.
* Using site structure or the browser language (the `navigator.language / accept-language` header). The advantage of this method is lower cost and possibly better performance. The disadvantage of this method is that Chinese-speaking visitors visiting outside of China are subject to negatively-affected speeds.
* Using a hosting solution based in China and setting the trackingServer to China RDC based on your host. This will also increase speed substantially.

## Current limitations

The current limitations of China RDC:

1. China RDC does not support first party SSL ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in your JavaScript), or [Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to Adobe Audience Manager.
1. Although [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) and [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) are supported, the Target and Demdex domains are not currently in mainland China and will not have the same speed or reliability benefits as those within the China RDC.

## Adobe’s commitment to China

Adobe plans to permanently keep China RDC progressing and will eventually add support for features such as first-party SSL and server-side forwarding. Additionally, Adobe plans to provide a demdex (or equivalent) domain in China to fully support ECID and Audience Manager collection from within China. Customers who begin using Adobe's China RDC are welcome to continue using this data collection endpoint indefinitely.
