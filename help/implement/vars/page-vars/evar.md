---
title: eVar (variable)
description: Custom variables you can use in your implementation.
feature: Appmeasurement Implementation
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7GS-wW0K3hh-uZ4fTi8yajH9wgFGBW-BQjT9m1mhXuU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
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
# eVar

*This help page describes how to implement eVars. For information on how eVars work as a dimension, see [eVars](/help/components/dimensions/evar.md) in the Components user guide.*

eVars are custom variables that you can use however you'd like. If you have a [solution design document](/help/implement/prepare/solution-design.md), most dimensions specific to your organization end up as eVars. By default, eVars persist beyond the hit they are set on. You can customize their expiration and allocation under [Conversion variables](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

The number of available eVars depends on your contract with Adobe. Up to 250 eVars are available if your contract with Adobe supports it.

## Set up eVars in report suite settings

Before using eVars in your implementation, make sure that you configure each eVar in report suite settings. See [Conversion variables](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## eVars using the Web SDK

eVars are mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.eVars.eVar1` to `xdm._experience.analytics.customDimensions.eVars.eVar250`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.eVar1` to `data.__adobe.analytics.eVar250`; or `data.__adobe.analytics.v1` to `data.__adobe.analytics.v250`

## eVars using the Adobe Analytics extension

You can set eVars either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL eVars] section.

You can set an eVar to a value or a data element. You can also copy the value from another Analytics variable.

## s.eVar1 - s.eVar250 in AppMeasurement and the Analytics extension custom code editor

Each eVar is a string that contains custom values specific to your organization. Their max length is 255 bytes; values longer than 255 bytes are automatically truncated when sent to Adobe.

```js
s.eVar1 = "Example custom value";
```

## Counter eVars

eVar values typically contain a string value. However, you can configure eVars to instead contain a counter. For example, you would like to count the number of internal searches made before a purchase. Instead of setting a text value, you would use the following syntax:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

If more than two decimal places are given, the eVar counter rounds to two decimal places. An eVar counter cannot contain negative numbers.

>[!IMPORTANT]
>
>You must first configure eVars to 'Counter' in the Admin Console before using counter eVars. See [Conversion variables](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) in the Admin guide.
