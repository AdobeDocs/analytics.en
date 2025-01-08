---
title: Data object variable mapping to Adobe Analytics
description: View which data object fields Experience Platform Edge automatically maps to Analytics variables.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
---
# Data object variable mapping to Adobe Analytics

The following table shows the data object variables that the Adobe Experience Platform Edge Network automatically maps into Adobe Analytics. If you use these data object field paths, no additional configuration is necessary to send data to Adobe Analytics.

Use of these fields is recommended if you intend to use Customer Journey Analytics in the future. This implementation method allows your organization to send data to Adobe using the Web SDK without conforming to an XDM schema. When your organization is ready to send data to Adobe Experience Platform, you can use [Datastream mapping](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep#mapping) to point data object fields to their respective XDM fields.

## Value priorities

Most data object fields in this table coincide with a [mapped XDM field](xdm-var-mapping.md). If you set both a given data object field and its respective XDM field, the data object field takes priority. For example, if the field `data.__adobe.analytics.events` is present, it overwrites all event-related XDM object fields.

Some data object fields also support their respective [Query parameter value](../validate/query-parameters.md) as shorthand values. You can use standard data object fields and shorthand data object fields interchangeably, as long as they are each for unique variables. Avoid setting both a standard data object field and its respective shorthand data object field at the same time. Adobe cannot guarantee which field takes priority.

## Data object field mapping

Previous updates to this table can be found on this page's [commit history on GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md). Similarly to AppMeasurement variables, all data object fields are case-sensitive.

| Data object field path | Analytics variable and description |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | The [Browser height](../../components/dimensions/browser-height.md) dimension. The shorthand field `data.__adobe.analytics.bh` is also supported. |
| `data.__adobe.analytics.browserWidth` | The [Browser width](../../components/dimensions/browser-width.md) dimension. The shorthand field `data.__adobe.analytics.bw` is also supported. |
| `data.__adobe.analytics.campaign` | The [Tracking code](../../components/dimensions/tracking-code.md) dimension. The shorthand field `data.__adobe.analytics.v0` is also supported. |
| `data.__adobe.analytics.channel` | The [Site section](../../components/dimensions/site-section.md) dimension. The shorthand field `data.__adobe.analytics.ch` is also supported. |
| `data.__adobe.analytics.colorDepth` | The [Color depth](../../components/dimensions/color-depth.md) dimension. The shorthand field `data.__adobe.analytics.c` is also supported. |
| `data.__adobe.analytics.connectionType` | The [Connection type](../../components/dimensions/connection-type.md) dimension. The shorthand field `data.__adobe.analytics.ct` is also supported. |
| `data.__adobe.analytics.contextData` | [Context data variables](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | The [Cookie support](../../components/dimensions/cookie-support.md) dimension. The shorthand field `data.__adobe.analytics.k` is also supported. |
| `data.__adobe.analytics.currencyCode` | The [`currencyCode`](../vars/config-vars/currencycode.md) implementation variable. The shorthand field `data.__adobe.analytics.cc` is also supported. |
| `data.__adobe.analytics.dynamicVariablePrefix` | The [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) implementation variable. |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensions. The shorthand fields `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` are also supported. |
| `data.__adobe.analytics.events` | [Custom events](../../components/metrics/custom-events.md). Format this field similarly to the [`events`](../vars/page-vars/events/events-overview.md) implementation variable. |
| `data.__adobe.analytics.javaEnabled` | The [Java enabled](../../components/dimensions/java-enabled.md) dimension. The shorthand field `data.__adobe.analytics.v` is also supported. |
| `data.__adobe.analytics.latitude` | Helps set the [Location](../../components/dimensions/lifecycle-dimensions.md) mobile lifecycle dimensions. The shorthand field `data.__adobe.analytics.lat` is also supported. |
| `data.__adobe.analytics.linkName` | The [Custom link](../../components/dimensions/custom-link.md), [Download link](../../components/dimensions/download-link.md), or [Exit link](../../components/dimensions/exit-link.md) dimension, depending on the value in `data.__adobe.analytics.linkType`. The shorthand field `data.__adobe.analytics.pev2` is also supported. |
| `data.__adobe.analytics.linkURL` | The [`linkURL`](../vars/config-vars/linkurl.md) implementation variable. The shorthand field `data.__adobe.analytics.pev1` is also supported. |
| `data.__adobe.analytics.linkType` | Determines the type of link clicked. Valid values include `o` (Custom links), `d` (Download links), and `e` (Exit links). The shorthand field `data.__adobe.analytics.pe` is also supported. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) implementation variables. The shorthand fields `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` are also supported. |
| `data.__adobe.analytics.longitude` | Help set the [Location](../../components/dimensions/lifecycle-dimensions.md) mobile lifecycle dimensions. The shorthand field `data.__adobe.analytics.lon` is also supported. |
| `data.__adobe.analytics.pageName` | The [Page](/help/components/dimensions/page.md) dimension. |
| `data.__adobe.analytics.pageURL` | The [Page URL](/help/components/dimensions/page-url.md) dimension. The shorthand field `data.__adobe.analytics.g` is also supported. |
| `data.__adobe.analytics.pageType` | The [`pageType`](../vars/page-vars/pagetype.md) implementation variable. |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensions. The shorthand fields `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` are also supported. |
| `data.__adobe.analytics.purchaseID` | The [`purchaseID`](../vars/page-vars/purchaseid.md) implementation variable. |
| `data.__adobe.analytics.products` | The [`products`](../vars/page-vars/products.md) implementation variable, following similar formatting. |
| `data.__adobe.analytics.referrer` | The [Referrer](/help/components/dimensions/referrer.md) dimension. |
| `data.__adobe.analytics.resolution` | The [Monitor resolution](../../components/dimensions/monitor-resolution.md) dimension. The shorthand field `data.__adobe.analytics.s` is also supported. |
| `data.__adobe.analytics.server` | The [Server](/help/components/dimensions/server.md) dimension. |
| `data.__adobe.analytics.transactionID` | The [`transactionID`](../vars/page-vars/transactionid.md) implementation variable. The shorthand field `data.__adobe.analytics.xact` is also supported. |
| `data.__adobe.analytics.zip` | The [Zip code](../../components/dimensions/zip-code.md) dimension. |

{style="table-layout:auto"}
