---
title: Data collection query parameters
description: Lists all query string parameters used in image requests.
feature: Validation
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
---
# Data collection query parameters

The following table lists all query string parameters Adobe uses in image requests. This information can be used when debugging using [Packet analyzers](packet-monitor.md), when [hardcoding image requests](../other/hardcoded.md), or when using [Dynamic Variables](../vars/page-vars/dynamic-variables.md).

| Parameter | Analytics implementation variable | Description |
| --- | --- | --- |
| `aamlh` | None | Audience Manager location hint. Used in Experience Cloud Shared Profile integration. |
| `aamb` | None | Audience Manager blob. Used in Experience Cloud Shared Profile integration. |
| `aid` | None | Analytics visitor ID. |
| `AQB` | None | Indicates the beginning of an image request query string. |
| `AQE` | None | Indicates the end of an image request, meaning that the request was not truncated. |
| `bh` | None | Browser height (in pixels). Used in the [Browser height](/help/components/dimensions/browser-height.md) dimension. |
| `bw` | None | Browser width (in pixels). Used in the [Browser width](/help/components/dimensions/browser-width.md) dimension. |
| `c` | None | Color quality (in bits). Used in the [Color depth](/help/components/dimensions/color-depth.md) dimension. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indicates the start of context data variables. Never contains a value. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indicates the end of context data variables. Never contains a value. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md), or custom traffic variables. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | The type of currency used in the hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | The number of periods in a domain. Used to help store cookies correctly. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | The character encoding of the image request. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | The lifetime of the visitor cookie. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Used in the [Site sections](/help/components/dimensions/site-section.md) dimension. |
| `cp` | None | Used in the [Hit Type](/help/components/dimensions/hit-type.md) dimension. |
| `ct` | None | Used in the [Connection Type](/help/components/dimensions/connection-type.md) dimension. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Denotes what to use for dynamic variables. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Shorthand for the `events` query string. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Comma-separated list of events on the page. Used by most [metrics](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | The current URL of the page, up to 255 bytes. Used in the [Page URL](/help/components/dimensions/page-url.md) dimension. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) |  URLs longer than 255 bytes are split. The first 255 bytes appear in the `g` parameter, and all remaining bytes appear in the `-g` parameter. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Shorthand for the `pageName` query string. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Shorthand for the `pageType` query string. |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Hierarchy dimensions. |
| `hp` | None | No longer used. In previous versions of Adobe Analytics, determined if the current URL was the browser's homepage. |
| `j` | None | The JavaScript version installed in the browser. |
| `k` | None | Used in the [Cookie support](/help/components/dimensions/cookie-support.md) dimension. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | List variables. |
| `lrt` | None | The "last request timing," which is the roundtrip time for the last request, in milliseconds. It is sent only when more than one request is going out from a page or when the page is a single-page application (SPA). |
| `mid` | None | Experience Cloud visitor ID. |
| `ndh` | None | Flag indicating if the image request originated from AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Helps determine where cookies are set. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Object identifier for the last page. Used in Activity Map. |
| `ot` | None | Object name for the last page. Used in previous versions of Activity Map. |
| `p` | None | No longer used. List of plug-ins used in the browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Used in the [Page](/help/components/dimensions/page.md) dimension. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Used in the [Pages not found](/help/components/dimensions/pages-not-found.md) dimension. |
| `pccr` | None | Only set for new visitors and always set to `true`. Helps prevent infinite redirects. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determines the type of custom link. Required for [Custom links](/help/components/dimensions/custom-link.md), [Download links](/help/components/dimensions/download-link.md), and [Exit links](/help/components/dimensions/exit-link.md). |
| `pev1` | None | The URL the custom link occurred on.|
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Custom link friendly name. |
| `pev3` | None | No longer used. Tracked milestones in previous versions of video reporting. |
| `pf` | None | Platform flag; for Adobe use only. Do not alter. |
| `pid` | None | Page identifier for last page. Used in previous versions of Activity Map. |
| `pidt` | None | Page identifier type for last page. Used in previous versions of Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Shorthand for the `products` query string. |
| `products` | [`products`](../vars/page-vars/products.md) | Products variable. Used in the [Product](/help/components/dimensions/product.md) and [Category](/help/components/dimensions/category.md) dimensions. |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Used to deduplicate purchases. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | Referring URL of the hit. Used in traffic sources dimensions, such as [Referrer](/help/components/dimensions/referrer.md) and [Referring domain](/help/components/dimensions/referring-domain.md) |
| `s` | None | Screen resolution, in `width x height`. Used in the [Monitor resolutions](/help/components/dimensions/monitor-resolution.md) dimension. |
| `server` | [`server`](../vars/page-vars/server.md) | [Server](/help/components/dimensions/server.md) dimension. |
| `sv` | [`server`](../vars/page-vars/server.md) | Shorthand for the `server` query string. |
| `state` | [`state`](../vars/page-vars/state.md) | State dimension. |
| `t` | None | Generated date/time of the hit. Uses the format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` is date/time in JavaScript. Month `0` is January, while month `11` is December.<br>- `w` is the day of the week. `0` is Sunday, while `6` is Saturday.<br>- `o` is the negative GMT offset in minutes. For example, `420` is GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | The custom timestamp set with the hit. Typically used for offline tracking. |
| `v` | None | Used in the [Java enabled](/help/components/dimensions/java-enabled.md) dimension. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Tracking Code](/help/components/dimensions/tracking-code.md) dimension. |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md), or custom conversion dimensions. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Visitor ID variable. |
| `vmk` | `vmk` | No longer used. Visitor migration key, which helped migrate implementations from third-party to first-party cookies. |
| `vvp` | `variableProvider` | Used in Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Used with Data Sources to tie online and offline data together. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Used in the [Zip code](/help/components/dimensions/zip-code.md) dimension. |
