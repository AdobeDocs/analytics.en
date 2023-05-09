---
title: channel
description: Populate the 'Site Sections' dimension.
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
---
# channel

The `channel` variable typically stores the section of the site a given page is on. It is helpful to determine what groups of your site are most popular. This variable populates the 'Site Sections' dimension.

## Channel using the Web SDK

Channel is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `web.webPageDetails.siteSection`.

## Channel using the Adobe Analytics extension

You can set channel either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Channel] section.

You can set channel to any string value or data element.

## s.channel in AppMeasurement and the Analytics extension custom code editor

The `s.channel` variable is a string that typically contains the page's site section. It has a maximum value of 100 bytes; longer values are truncated.

```js
s.channel = "Example site section";
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
