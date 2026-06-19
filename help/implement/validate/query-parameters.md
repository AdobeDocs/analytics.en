---
title: Data collection query parameters
description: Lists all query string parameters used in image requests.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Data collection query parameters

The following table lists all query string parameters Adobe uses in image requests. This information is useful when debugging with [packet analyzers](packet-monitor.md), when [hardcoding image requests](../other/hardcoded.md), or when using [dynamic variables](../vars/page-vars/dynamic-variables.md).

| Parameter | Analytics implementation variable | Description |
| --- | --- | --- |
| `aamlh` | None | Audience Manager location hint. Identifies the regional data center used for Audience Manager ID syncing through the Experience Cloud ID Service. |
| `aamb` | None | Audience Manager blob. Encoded Audience Manager profile data passed during ID syncing through the Experience Cloud ID Service. |
| `aid` | None | The legacy Analytics visitor ID, stored in the `s_vi` cookie. Superseded by the `mid` parameter in modern implementations. |
| `AQB` | None | Indicates the beginning of an image request query string. |
| `AQE` | None | Indicates the end of an image request, meaning that the request was not truncated. |
| `bh` | None | Browser height (in pixels). Used in the [[!UICONTROL Browser height]](/help/components/dimensions/browser-height.md) dimension. |
| `bw` | None | Browser width (in pixels). Used in the [[!UICONTROL Browser width]](/help/components/dimensions/browser-width.md) dimension. |
| `c` | None | Color quality (in bits). Used in the [[!UICONTROL Color depth]](/help/components/dimensions/color-depth.md) dimension. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indicates the start of context data variables. Never contains a value. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indicates the end of context data variables. Never contains a value. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md), or custom traffic variables. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | The type of currency used in the hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **No longer used.** The number of periods in a domain. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | The character encoding of the image request. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | The lifetime of the visitor cookie. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Used in the [[!UICONTROL Site sections]](/help/components/dimensions/site-section.md) dimension. |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | Specifies whether a mobile app hit occurred while the app was in the foreground or background. Used in the [[!UICONTROL Hit type]](/help/components/dimensions/hit-type.md) dimension. |
| `ct` | None | Used in the [[!UICONTROL Connection type]](/help/components/dimensions/connection-type.md) dimension. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Denotes what to use for dynamic variables. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Shorthand for the `events` parameter. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Comma-separated list of events on the page. Used by most [metrics](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | The current URL of the page, up to 255 bytes. Used in the [[!UICONTROL Page URL]](/help/components/dimensions/page-url.md) dimension. |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | URLs longer than 255 bytes are split. The first 255 bytes appear in the `g` parameter, and all remaining bytes appear in the `-g` parameter. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Shorthand for the `pageName` parameter. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Shorthand for the `pageType` parameter. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefix for several variables that represent [Client hints](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **No longer used.** Hierarchy dimensions. |
| `hp` | None | **No longer used.** In previous versions of Adobe Analytics, determined if the current URL was the browser's homepage. |
| `j` | None | **No longer used.** The JavaScript version installed in the browser. |
| `k` | None | Used in the [[!UICONTROL Cookie support]](/help/components/dimensions/cookie-support.md) dimension. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | List variables. |
| `lat` | None | **No longer used.** Latitude. Set by legacy mobile SDK implementations; current mobile implementations send geolocation through datastreams. |
| `lon` | None | **No longer used.** Longitude. Set by legacy mobile SDK implementations; current mobile implementations send geolocation through datastreams. |
| `lrt` | None | The "last request timing," which is the roundtrip time for the last request, in milliseconds. It is sent only when more than one request is sent from a single page, such as in a single-page application (SPA). |
| `mcorgid` | None | The Experience Cloud Organization ID, which identifies the organization to the Experience Cloud ID Service. |
| `mid` | None | Used in the [[!UICONTROL Experience Cloud Visitor ID]](/help/components/dimensions/experience-cloud-visitor-id.md) dimension. |
| `ms_a` | None | Set by the Media SDK to `1` when the tracked streaming media is audio rather than video. |
| `ndh` | None | Added by AppMeasurement to every image request it generates. Because hardcoded requests typically omit it, its presence indicates that the hit came from AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **No longer used.** Helps determine where cookies are set. |
| `oi` | None | **No longer used.** Object instance for the last page. Used in previous versions of Activity Map. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Object identifier for the last page. Used in the current version of Activity Map. |
| `oidt` | None | **No longer used.** Object identifier type for the last page. Used in previous versions of Activity Map. |
| `ot` | None | **No longer used.** Object name for the last page. Used in previous versions of Activity Map. |
| `p` | None | **No longer used.** List of plug-ins used in the browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Used in the [[!UICONTROL Page]](/help/components/dimensions/page.md) dimension. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Used in the [[!UICONTROL Pages not found]](/help/components/dimensions/pages-not-found.md) dimension. |
| `pccr` | None | Persistent cookie check redirect flag. Set by Adobe data collection servers for new visitors, and always set to `true`. When a new visitor's cookie support is unknown, the data collection server redirects the image request to itself with this flag to confirm the persistent cookie check already occurred. This parameter prevents infinite redirects if the visitor rejects cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determines the type of hit. Valid values include `lnk_o` ([[!UICONTROL Custom link]](/help/components/dimensions/custom-link.md)), `lnk_d` ([[!UICONTROL Download link]](/help/components/dimensions/download-link.md)), `lnk_e` ([[!UICONTROL Exit link]](/help/components/dimensions/exit-link.md)), and `tnt` (an Analytics for Target hit). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | The URL on which the custom link occurred. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | The friendly name of the [custom link](/help/components/dimensions/custom-link.md). |
| `pev3` | None | **No longer used.** Tracked milestones in previous versions of video reporting. |
| `pf` | None | Platform flag; for Adobe use only. Do not alter. |
| `pid` | None | **No longer used.** Page identifier for last page. Used in previous versions of Activity Map. |
| `pidt` | None | **No longer used.** Page identifier type for last page. Used in previous versions of Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Shorthand for the `products` parameter. |
| `products` | [`products`](../vars/page-vars/products.md) | Products variable. Used in the [[!UICONTROL Product]](/help/components/dimensions/product.md) and [[!UICONTROL Category]](/help/components/dimensions/category.md) dimensions. |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Used in the [[!UICONTROL Purchase ID]](/help/components/dimensions/purchase-id.md) dimension. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | Referring URL of the hit. Used in traffic sources dimensions, such as [[!UICONTROL Referrer]](/help/components/dimensions/referrer.md) and [[!UICONTROL Referring domain]](/help/components/dimensions/referring-domain.md). |
| `s` | None | Screen resolution, in `width x height`. Used in the [[!UICONTROL Monitor resolutions]](/help/components/dimensions/monitor-resolution.md) dimension. |
| `sdid` | None | Supplemental Data ID. Links multiple hits that describe the same event, such as Analytics and Target hits in an [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html) integration. |
| `server` | [`server`](../vars/page-vars/server.md) | Used in the [[!UICONTROL Server]](/help/components/dimensions/server.md) dimension. |
| `sv` | [`server`](../vars/page-vars/server.md) | Shorthand for the `server` parameter. |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **No longer used.** Captured the U.S. state a visitor entered, typically through a shipping or billing form. |
| `t` | None | Generated date/time of the hit. Uses the format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` is date/time in JavaScript. Month `0` is January, while month `11` is December.<br>- `w` is the day of the week. `0` is Sunday, while `6` is Saturday.<br>- `o` is the negative GMT offset in minutes. For example, `420` is GMT-7. |
| `tnt` | None | Target data payload used in [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html) integrations. Sent when `pe=tnt`. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | The custom timestamp set with the hit. Typically used for offline tracking. |
| `u` | None | **No longer used.** Account marker used in previous versions of Activity Map. |
| `v` | None | Used in the [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md) dimension. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Used in the [[!UICONTROL Tracking code]](/help/components/dimensions/tracking-code.md) dimension. |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md), or custom conversion dimensions. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Visitor ID override variable. |
| `vidn` | None | Set by Adobe data collection servers for new visitors, accompanying the `pccr` parameter in the redirected image request. Contains the visitor ID value stored in the visitor cookie. |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **No longer used.** Visitor migration server used during the migration from third-party to first-party cookies. |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **No longer used.** Visitor migration key, which helped migrate implementations from third-party to first-party cookies. |
| `vvp` | None | **No longer used.** Variable provider used in Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Used with Data Sources to tie online and offline data together. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Used in the [Zip code](/help/components/dimensions/zip-code.md) dimension. |
