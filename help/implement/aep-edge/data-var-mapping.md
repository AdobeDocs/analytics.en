---
title: Data object variable mapping to Adobe Analytics
description: View which data object fields that Edge automatically maps to Analytics variables.
feature: Implementation Basics
role: Admin, Developer
---
# Data object variable mapping to Adobe Analytics

The following table shows the data object variables that the Adobe Experience Platform Edge Network automatically maps into Adobe Analytics. If you use these data object field paths, no additional configuration is necessary to send data to Adobe Analytics.

Use of these fields are recommended if you intend to use Customer Journey Analytics in the future. This implementation mathod allows your organization to send data to Adobe using the Web SDK without conforming to an XDM schema. When your organization is ready to send data to Adobe Experience Platform, you can use [Datastream mapping](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) to point data object fields to their respective XDM fields.

## Value priorities

Most data object fields in this table coincide with a [mapped XDM field](xdm-var-mapping.md). If you set both a given `data` object field and its respective XDM field, the XDM field takes priority.

Several values in this table have alternative fields mapped to the same analytics variable. Avoid setting both a data object field and its respective alternative data object field at the same time. Adobe cannot guarantee which data object field takes priority.

## Data object field mapping

Previous updates to this table can be found on this page's [commit history on GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md).

| Data object field path | Analytics variable and description |
| --- | --- |
| `data.__adobe.bh` | Alternative field for `data.__adobe.browserHeight`. |
| `data.__adobe.browserHeight` | The [Browser height](../../components/dimensions/browser-height.md) dimension. |
| `data.__adobe.browserWidth` | The [Browser width](../../components/dimensions/browser-width.md) dimension. |
| `data.__adobe.bw` | Alternative field for `data.__adobe.browserWidth`. |
| `data.__adobe.c` | Alternative field for `data.__adobe.colorDepth`. |
| `data.__adobe.c1` - `data.__adobe.c75` | Alternative fields for `data.__adobe.prop1` - `data.__adobe.prop75`. |
| `data.__adobe.campaign` | The [Tracking code](../../components/dimensions/tracking-code.md) dimension. |
| `data.__adobe.cc` | Alternative field for `data.__adobe.currencyCode`. |
| `data.__adobe.ch` | Alternative field for `data.__adobe.channel`. |
| `data.__adobe.channel` | The [Site section](../../components/dimensions/site-section.md) dimension. |
| `data.__adobe.colorDepth` | The [Color depth](../../components/dimensions/color-depth.md) dimension. |
| `data.__adobe.connectionType` | The [Connection type](../../components/dimensions/connection-type.md) dimension. |
| `data.__adobe.contextData` | [Context data variables](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.cookiesEnabled` | The [Cookie support](../../components/dimensions/cookie-support.md) dimension. |
| `data.__adobe.ct` | Alternative field for `data.__adobe.connectionType`. |
| `data.__adobe.currencyCode` | The [`currencyCode`](../vars/config-vars/currencycode.md) implementation variable. |
| `data.__adobe.dynamicVariablePrefix` | The [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) implementation variable. |
| `data.__adobe.eVar1` - `data.__adobe.eVar250` | [eVar](../../components/dimensions/evar.md) dimensions. |
| `data.__adobe.events` | [Custom events](../../components/metrics/custom-events.md). Format this field similarly to the [`events`](../vars/page-vars/events/events-overview.md) implementation variable. |
| `data.__adobe.g` | Alternative field for `data.__adobe.pageName`. |
| `data.__adobe.javaEnabled` | The [Java enabled](../../components/dimensions/java-enabled.md) dimension. |
| `data.__adobe.l1` - `data.__adobe.l3` | Alternative fields for `data.__adobe.list1` - `data.__adobe.list3`. |
| `data.__adobe.lat` | Alternative field for `data.__adobe.latitude`. |
| `data.__adobe.latitude` | Helps set the [Location](../../components/dimensions/lifecycle-dimensions.md) mobile lifecycle dimensions. |
| `data.__adobe.linkName` | The [Custom link](../../components/dimensions/custom-link.md), [Download link](../../components/dimensions/download-link.md), or [Exit link](../../components/dimensions/exit-link.md) dimension, depending on the value in `data.__adobe.linkType`. |
| `data.__adobe.linkURL` | The [`linkURL`](../vars/config-vars/linkurl.md) implementation variable. |
| `data.__adobe.linkType` | Determines the type of link clicked. Valid values include `o` (Custom links), `d` (Download links), and `e` (Exit links). |
| `data.__adobe.list1` - `data.__adobe.list3` | [`list`](/help/implement/vars/page-vars/list.md) implementation variables. |
| `data.__adobe.lon` | Alternative field for `data.__adobe.longitude`. |
| `data.__adobe.longitude` | Help set the [Location](../../components/dimensions/lifecycle-dimensions.md) mobile lifecycle dimensions. |
| `data.__adobe.k` | Alternative field for `data.__adobe.cookiesEnabled`. |
| `data.__adobe.pageName` | The [Page](/help/components/dimensions/page.md) dimension. |
| `data.__adobe.pageURL` | The [Page URL](/help/components/dimensions/page-url.md) dimension. |
| `data.__adobe.pageType` | The [`pageType`](../vars/page-vars/pagetype.md) implementation variable. |
| `data.__adobe.pe` | Alternative field for `data.__adobe.linkType`. |
| `data.__adobe.pev1` | Alternative field `data.__adobe.linkURL`. |
| `data.__adobe.pev2` | Alternative field for `data.__adobe.linkName`. |
| `data.__adobe.prop1` - `data.__adobe.prop75` | [Prop](../../components/dimensions/prop.md) dimensions. |
| `data.__adobe.purchaseID` | The [`purchaseID`](../vars/page-vars/purchaseid.md) implementation variable. |
| `data.__adobe.products` | The [`products`](../vars/page-vars/products.md) implementation variable, following similar formatting. |
| `data.__adobe.referrer` | The [Referrer](/help/components/dimensions/referrer.md) dimension. |
| `data.__adobe.resolution` | The [Monitor resolution](../../components/dimensions/monitor-resolution.md) dimension. |
| `data.__adobe.s` | Alternative field for `data.__adobe.resolution`. |
| `data.__adobe.server` | The [Server](/help/components/dimensions/server.md) dimension. |
| `data.__adobe.tnta` | Used in A4T integrations. |
| `data.__adobe.transactionID` | The [`transactionID`](../vars/page-vars/transactionid.md) implementation variable. |
| `data.__adobe.v` | Alternative field for `data.__adobe.javaEnabled`. |
| `data.__adobe.v0` | Alternative field for `data.__adobe.campaign`. |
| `data.__adobe.v1` - `data.__adobe.v250` | Alternative fields for `data.__adobe.eVar1` - `data.__adobe.eVar250`. |
| `data.__adobe.xact` | Alternative field for `data.__adobe.transactionID`. |
| `data.__adobe.zip` | The [Zip code](../../components/dimensions/zip-code.md) dimension. |

{style="table-layout:auto"}
