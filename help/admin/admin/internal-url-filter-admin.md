---
description: Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.
seo-description: Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.
seo-title: Internal URL Filters
solution: Analytics
title: Internal URL Filters
topic: Admin tools
uuid: acb67a8e-61b2-46c8-8056-74da925c0a05
index: y
internal: n
snippet: y
---

# Internal URL Filters

Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.

A referrer, or referring page, is typically the page from which a visitor entered your site. To avoid skewing data, you can filter out internal referrers. Reports exclude filtered referrers from the [Referrers Report](reports_referrers.md#concept_40CF9C2D10B94E82819BC65A232F05C3), the [Referring Domains Report](reports_referring_domains.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF), and other Finding Methods reports.

The most common reason traffic sources reports don't populate data is that the Internal URL Filter List isn't defined. To check which Internal URL Filters have been set up on a report suite, follow these steps. To avoid this, remove the rule listing a period (.) as a filter, and add your own site.

The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated. 
