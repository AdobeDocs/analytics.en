---
title: Referring domain
description: The overarching domain a visitor was on before clicking through to your site.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Referring domain

The 'Referring domain' [dimension](overview.md) reports which domains visitors click through to reach your site. This dimension is useful to understand which third-party sites drive the most traffic to yours. A link must exist on the external site and a visitor must click it in order for the dimension item to show up.

>[!IMPORTANT]
>
>You must configure your report suite's [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

The same report can show different results between Analysis Workspace and Data Warehouse. Analysis Workspace reports the referring domain for each individual page, excluding values that match internal URL filters. Data Warehouse reports only the first referring domain of the visit, and ignores internal URL filters.

## Populate this dimension with data

This dimension requires configuration in the Analytics interface and data in image requests.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

Adobe persists referring domain for a visit. If a visitor leaves and clicks through a link on a different domain within a single visit, the new value updates and persists for the remainder of the visit. If you only want to see the original value, see [Original referring domain](original-referring-domain.md).

## Dimension items

Dimension items include domains that visitors click through to your site. If a hit does not have any referrer data (either set or persisted), it groups under the dimension item `"Typed/Bookmarked"`. This dimension item means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark. The `"Typed/Bookmarked"` dimension item also appears for redirects that don't accommodate Analytics. See [Redirects and aliases](/help/technotes/redirects.md) in the Technotes user guide.

### Dimension items containing `googleusercontent.com`

Users can see dimension items with the domain `googleusercontent.com`.

* **Cached pages**: Google's spiders constantly crawl the web and store copies of pages in case they are taken offline. These cached pages are available next to most search results by clicking the "Cached" link. When a user clicks this link and views the content that Google cached, `googleusercontent.com` is the dimension item.
* **Translated pages**: Google offers a robust and convenient translation service. When viewing a site using this service, it originates from `googleusercontent.com`. This dimension item appears if the user clicks a link to return to the original content.
