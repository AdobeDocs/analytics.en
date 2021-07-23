---
title: Referrer
description: The URL a visitor was at before clicking through to your site.
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
---
# Referrer

The 'Referrer' dimension reports which URLs visitors were on when clicking through to reach your site. This dimension is useful to understand which specific URLs drive the most traffic to your site. A link must exist on the external URL and a visitor must click it in order for the dimension item to show up.

>[!IMPORTANT]
>
>You must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal URLs or prevent external URLs from appearing.

The same report can show different results between Analysis Workspace and Data Warehouse. Analysis Workspace reports the referrer for each individual page, excluding values that match internal URL filters. Data Warehouse reports only the first referrer of the visit, and ignores internal URL filters.

## Populate this dimension with data

This dimension requires configuration in the Analytics interface and data in image requests.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. You can use the [`referrer`](/help/implement/vars/page-vars/referrer.md) variable override to manually set it. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal URLs or prevent external URLs from appearing.

## Dimension items

Dimension items include URLs that visitors click through to your site. If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. This dimension item means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark. The `"Typed/Bookmarked"` dimension item also appears for redirects that don't accommodate Analytics. See [Redirects and aliases](/help/technotes/redirects.md) in the Technotes user guide.

### Dimension items containing `googleusercontent.com`

Users can see dimension items with the domain `googleusercontent.com`.

* **Cached pages**: Google's spiders constantly crawl the web and store copies of pages in case they are taken offline. These cached pages are available next to most search results by clicking the "Cached" link. When a user clicks this link and views the content that Google cached, `webcache.googleusercontent.com` is a typical dimension item.
* **Translated pages**: Google offers a robust and convenient translation service. When viewing a site using this service, it originates from `translate.googleusercontent.com`. This dimension item appears if the user clicks a link to return to the original content.
