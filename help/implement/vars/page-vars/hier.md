---
title: hier
description: (Retired) Implement hierarchy variables in Adobe Analytics.
feature: Appmeasurement Implementation
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ngX4oPKy0XWEb-9xLpxSAdoAqZmfsMM8rbEH2-llHX4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# hier

>[!IMPORTANT]
>
>This variable is retired and not an available dimension in Analysis Workspace. Adobe recommends using [eVars](evar.md) and classifications instead.

Hierarchy variables are custom variables that let you see a site's structure. Adobe supports up to 5 hierarchy variables in your implementation.

This variable is useful for sites that have more than three levels in their site structure. For example, a media site can have 4 levels to the Sports section: `Sports`, `Local Sports`, `Baseball`, and `Team name`. If someone visits the Baseball page, Sports, Local Sports, and Baseball, all levels reflect that visit.

Before using hierarchies in your implementation, make sure that you configure each hierarchy in report suite settings.

## Hierarchies using the Web SDK

Hierarchies are [mapped for Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) under the XDM fields `xdm._experience.analytics.customDimensions.hierarchies.hier1` to `xdm._experience.analytics.customDimensions.hierarchies.hier5`.

## Hierarchies using the Adobe Analytics extension

You can set hierarchies either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Hierarchy] section.

You can set a hierarchy value to a static string or reference a data element. You can also set the desired delimiter. Make sure that the delimiter that you set here matches the delimiter set in Report suite settings.

## s.hier1 - s.hier5 in AppMeasurement and the Analytics extension custom code editor

Each hierarchy is a string that contains custom values specific to your organization. Their max length is 255 bytes; values longer than 255 bytes are automatically truncated when sent to Adobe.

Make sure that none of your section names have the delimiter in them. For example, if one of your sections is called `Coach Griffin, Jim`, choose a delimiter other than a comma. The total variable limit is 255 bytes. Delimiters can consist of multiple characters, such as `||` or `/|\`, which are less likely to appear in variable values.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
