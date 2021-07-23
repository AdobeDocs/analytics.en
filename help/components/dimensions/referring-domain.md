---
title: Referring domain
description: The overarching domain a visitor was on before clicking through to your site.
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
---
# Referring domain

The 'Referring domain' dimension reports which domains visitors click through to reach your site. This dimension is useful to understand which third-party sites drive the most traffic to yours. A link must exist on the external site and a visitor must click it in order for the dimension item to show up.

>[!IMPORTANT]
>
>You must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

The same report can show different results between Analysis Workspace and Data Warehouse. Analysis Workspace reports the referring domain for each individual page, excluding values that match internal URL filters. Data Warehouse reports only the first referring domain of the visit, and ignores internal URL filters.

## Populate this dimension with data

This dimension requires configuration in the Analytics interface and data in image requests.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

Adobe persists referring domain for a visit. If a visitor leaves and clicks through a link on a different domain within a single visit, the new value updates and persists for the remainder of the visit. If you only want to see the original value, see [Original referring domain](original-referring-domain.md).

## Dimension items

Dimension items include domains that visitors click through to your site. If a hit does not have any referrer data (either set or persisted), it groups under the dimension item `"Typed/Bookmarked"`. This dimension item means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark. The `"Typed/Bookmarked"` dimension item also appears for redirects that don't accommodate Analytics. See [Redirects and aliases](/help/technotes/redirects.md) in the Technotes user guide.

### Dimension items containing `googleusercontent.com`

Users can see dimension items with the domain `googleusercontent.com`.

* **Cached pages**: Google's spiders constantly crawl the web and store copies of pages in case they are taken offline. These cached pages are available next to most search results by clicking the "Cached" link. When a user clicks this link and views the content that Google cached, `googleusercontent.com` is the dimension item.
* **Translated pages**: Google offers a robust and convenient translation service. When viewing a site using this service, it originates from `googleusercontent.com`. This dimension item appears if the user clicks a link to return to the original content.
