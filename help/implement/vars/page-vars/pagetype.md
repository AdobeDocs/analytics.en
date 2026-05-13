---
title: pageType
description: Determine if the current page is a 404 error.
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
TQID: https://experienceleague.adobe.com/SD-hwWJmZby-y99FIZHrnevSBsVqD6T5gwovn5tJfxo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# pageType

The `pageType` variable is a flag used to designate error pages on your site, such as 404 errors. If this variable contains the string `errorPage`, it populates the 'Pages Not Found' [dimension](/help/components/dimensions/pages-not-found.md) and [metric](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Do not set this variable on non-error pages.

## Page Type using the Web SDK

Channel is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.isErrorPage` - this XDM field is a boolean; set it to `true` to flag it as an error page, or `false` if it is not an error page.
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` - this data object field is a string; set it to `"errorPage"` to flag it as such.

## Page Type using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.pageType in AppMeasurement and the Analytics extension custom code editor

The `s.pageType` variable is a string where the value `errorPage` is its only valid value. Set this variable to this value on any error page on your site, such as on 404 pages.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Use an eVar to collect the error code so you can get more information on what specific errors visitors encounter on your site.
