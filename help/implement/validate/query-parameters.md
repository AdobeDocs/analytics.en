---
title: Data collection query parameters
description: Lists all query string parameters used in image requests.
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
| `bh` | None | Browser height (in pixels). Used in the Browser Height dimension. |
| `bw` | None | Browser width (in pixels). Used in the Browser Width dimension. |
| `c` | None | Color quality (in bits). Used in the Color Depth dimension. |
| `c.` | `contextData` | Indicates the start of context data variables. Never contains a value. |
| `.c` | `contextData` | Indicates the end of context data variables. Never contains a value. |
| `c1` - `c75` | `prop1` - `prop75` | Custom traffic variables. |
| `cc` | `currencyCode` | The type of currency used in the hit. |
| `cdp` | `cookieDomainPeriods` | The number of periods in a domain. Used to help store cookies correctly. |
| `ce` | `charSet` | The character encoding of the image request. |
| `cl` | `cookieLifetime` | The lifetime of the visitor cookie. |
| `ch` | `channel` | Used in the Site Sections dimension. |
| `cp` | None | Used in the Hit Type dimension. |
| `ct` | None | Used in the Connection Type dimension. |
| `D` | `dynamicVariablePrefix` | Denotes what to use for dynamic variables. |
| `ev` | `events` | Shorthand for the `events` query string. |
| `events` | `events` | Comma-separated list of events on the page. |
| `g` | `pageURL` | The current URL of the page, up to 255 bytes. |
| `-g` | `pageURL` |  URLs longer than 255 bytes are split. The first 255 bytes appear in the `g` parameter, and all remaining bytes appear in the `-g` parameter. |
| `gn` | `pageName` | Shorthand for the `pageName` query string. |
| `gt` | `pageType` | Shorthand for the `pageType` query string. |
| `h1` - `h5` | `hier1` - `hier5` | Hierarchy variables. |
| `hp` | None | No longer used. In previous versions of Adobe Analytics, determined if the current URL was the browser's homepage. |
| `j` | None | The JavaScript version installed in the browser. |
| `k` | None | Used in the Cookie Support dimension. |
| `l1` - `l3` | `list1` - `list3` | List variables. |
| `mid` | None | Experience Cloud visitor ID. |
| `ndh` | None | Flag indicating if the image request originated from AppMeasurement. |
| `ns` | `visitorNameSpace` | Helps determine where cookies are set. |
| `oid` | `objectID` | Object identifier for the last page. Used in Activity Map. |
| `ot` | None | Object name for the last page. Used in previous versions of Activity Map. |
| `p` | None | No longer used. List of plugins used in the browser. |
| `pageName` | `pageName` | Used in the Page dimension. |
| `pageType` | `pageType` | Used in the Pages Not Found dimension. |
| `pccr` | None | Only set for new visitors and always set to `true`. Prevents infinite redirects. |
| `pe` | `linkType` | Determines the type of custom link. |
| `pev1` | None | The URL the custom link occurred on. |
| `pev2` | None | Custom link friendly name. |
| `pev3` | None | No longer used. Tracked milestones in previous versions of video reporting. |
| `pf` | None | Platform flag; for Adobe use only. Do not alter. |
| `pid` | None | Page identifier for last page. Used in previous versions of Activity Map. |
| `pidt` | None | Page identifier type for last page. Used in previous versions of Activity Map. |
| `pl` | `products` | Shorthand for the `products` query string. |
| `products` | `products` | Products variable. |
| `purchaseID` | `purchaseID` | Used to deduplicate purchases. |
| `r` | `referrer` | Referring URL of the hit. |
| `s` | None | Used in the Monitor Resolutions dimension. Screen resolution, in `width x height`. |
| `server` | `server` | Server dimension. |
| `sv` | `server` | Shorthand for the `server` query string. |
| `state` | `state` | State dimension. |
| `t` | None | Generated date/time of the hit. Uses the format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` is date/time in JavaScript. Month `0` is January, while month `11` is December.<br>- `w` is the day of the week. `0` is Sunday, while `6` is Saturday.<br>- `o` is the negative GMT offset in minutes. For example, `420` is GMT-7. |
| `ts` | `timestamp` | The custom timestamp set with the hit. Typically used for offline tracking. |
| `v` | None | Used in the Java Enabled dimension. |
| `v0` | `campaign` | Tracking Code dimension. |
| `v1` - `v250` | `evar1` - `eVar250` | Custom conversion dimensions. |
| `vid` | `visitorID` | Visitor ID variable. |
| `vmk` | `vmk` | No longer used. Helped migrate from third-party to first-party cookies. |
| `vvp` | `variableProvider` | Used in Data Connectors. |
| `xact` | `transactionID` | Used with Data Sources to link data together. |
| `zip` | `zip` | Used in the Zip Code dimension. |
