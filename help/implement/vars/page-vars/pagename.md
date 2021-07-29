---
title: pageName
description: The name of the page on your site.
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
---
# pageName

The `pageName` variable typically stores the name of a given page. It is helpful to determine what individual pages are most popular. This variable populates the [Page](/help/components/dimensions/page.md) dimension.

If this variable is not defined on a given page tracking call, the [`pageURL`](pageurl.md) variable is used instead.

>[!NOTE]
>
>Adobe data collection servers strip this dimension from all [link tracking](/help/implement/vars/functions/tl-method.md) image requests. If you want this dimension to appear in link tracking hits, consider copying this dimension into an [eVar](evar.md).

## Page Name using tags in Adobe Experience Platform

You can set page name either while configuring the Analytics extension (global variables) or under rules.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Page name] section.

You can set page name to any string value, including data elements.

## s.pageName in AppMeasurement and custom code editor

The `s.pageName` variable is a string that typically contains the name of the page. It has a maximum value of 100 bytes; longer values are truncated. This truncation includes instances where it falls back to `pageURL` if this variable is blank.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
