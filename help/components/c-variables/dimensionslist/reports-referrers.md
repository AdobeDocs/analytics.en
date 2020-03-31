---
title: Referrers
description: Shows the URL of the previous hit, if that hit was outside your site.
---

# Referrers

The 'Referrer' dimension shows the URL where your visitors came from before they arrived at your site. For example, if a visitor clicks a link from `example.com/example-page.html` and arrives on your site, `example.com/example-page.html` is the referrer if it is not defined as part of your domain.

This dimension requires you to configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). If you do not configure internal URL filters, Adobe Analytics considers all domains as internal to your site.

## Dimension properties

* This dimension uses most recent allocation by default.
* This dimension expires after visit by default.
* This dimension is subject to the 500k unique limit before grouping dimension values under (Low-traffic). Data Warehouse does not have a unique limit.
* If a there is no referrer value for a metric, it is grouped under `Typed/Bookmarked`.
* This dimension is typically set on the first hit of the visit, but can be set mid-visit.

## Troubleshooting

**Q: Why do I see `googleusercontent.com` as a dimension value?**

A: [Google](https://about.google/) uses the domain `googleusercontent.com` for their hosted content. Hosted content includes:

* **Cached pages**: Google's spiders constantly crawl the web and save web pages in the case they are taken offline or otherwise unavailable. These cached pages are available next to all search results by clicking the "Cached" link from one of Google's search result pages. When a user clicks this link then looks at the original content on your site, `googleusercontent.com` is listed as their referring domain. These pages have the subdomain `webcache.googleusercontent.com`.
* **Translated pages**: Google offers a robust and convenient translation service. When viewing a site using this service, it originates from `googleusercontent.com`. The referrer dimension shows URLS from this domain if the user clicks a link to return to the original content. These pages have the subdomain `translate.googleusercontent.com`.
