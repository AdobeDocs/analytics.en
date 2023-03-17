---
title: pageType
description: Determine if the current page is a 404 error.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
---
# pageType

The `pageType` variable is a flag used to designate error pages on your site, such as 404 errors. If this variable contains the string `errorPage`, it populates the 'Pages Not Found' [dimension](/help/components/dimensions/pages-not-found.md) and [metric](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Do not set this variable on non-error pages.

## Page Type using the Web SDK

Page Type is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `web.webPageDetails.isErrorPage`. This XDM field is a boolean; set it to `true` to flag it as an error page, or `false` if it is not an error page. Adobe automatically translates the boolean to the string value `errorPage` when it is sent to an Analytics report suite.

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
