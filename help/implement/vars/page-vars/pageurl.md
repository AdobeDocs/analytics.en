---
title: pageURL
description: Override the automatically collected page URL on your site.
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
---
# pageURL

AppMeasurement automatically collects the page URL in each hit. If you want to override the page URL automatically collected by AppMeasurement, you can use this variable. You do not need to set this variable in most cases.

>[!NOTE]
>
>This variable is not an available dimension in Analysis Workspace. It is only available in Data Warehouse and Data Feeds. Additionally, Adobe data collection servers strip this dimension from all [link tracking](/help/implement/vars/functions/tl-method.md) image requests. If you want to use page URL as a dimension in Analysis Workspace or want this dimension in link tracking hits, consider passing the `pageURL` variable into an [eVar](evar.md) on every hit.

## Page URL using tags in Adobe Experience Platform

The Data Collection UI automatically populates page URL. However, you can set the page URL override either while configuring the Analytics extension (global variables) or under rules.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the **[!UICONTROL Rules]** tab, then click the desired rule (or create a rule).
4. Under **[!UICONTROL Actions]**, click an existing **[!UICONTROL Adobe Analytics - Set Variables]** action or click the '+' icon.
5. Set the **[!UICONTROL Extension]** dropdown to Adobe Analytics, and the **[!UICONTROL Action Type]** to **[!UICONTROL Set Variables]**.
6. Locate the **[!UICONTROL Page URL]** section.

You can set page URL to any string value.

## s.pageURL in AppMeasurement and custom code editor

The `s.pageURL` variable is a string that contains the URL of the page. AppMeasurement automatically collects this variable, however you can override its value if desired.

```js
s.pageURL = "https://example.com";
```

If you would like to use page URL as a dimension in reports, consider using the following in your implementation:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
