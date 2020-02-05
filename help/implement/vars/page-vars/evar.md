---
title: eVar
description: Custom variables you can use in your implementation.
---

# eVar

eVars are custom variables that you can use however you'd like.

> [!TIP] Adobe recommends using eVars over props in most cases. In previous versions of Adobe Analytics, props and eVars had advantages and disadvantages to each other. However, Adobe has improved eVars to where they fulfill almost all use cases for props.

Make sure you record how you use each eVar and their logic in your [solution design document](../../prepare/solution-design.md).

## Set up eVars in report suite settings

Before using eVars in your implementation, make sure you configure each eVar in report suite settings. See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## eVars in Adobe Experience Platform Launch

You can set eVars either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL eVars] section.

You can select an eVar to set a value or data element. You can also copy the value from another Analytics variable.

## s.eVar1 - s.eVar250 in AppMeasurement and Launch custom code editor

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

## Exclusive advantages to props or eVars

In the current version of Adobe Analytics, props and eVars are both custom variables with similar capabilities. However, they have several major differences:

* Data in props are available in reporting within minutes. eVars can take upwards of 30 minutes to appear in reporting.
* Props have a 100-byte limit in reports. eVars have a 255-byte limit.
* Props have the ability to become list props, which accept multiple values in the same hit. List vars are a separate variable, and there are only three list variables available.
* Props by default do not persist beyond the hit they are set. eVars have custom expiration, allowing you to determine when an eVar no longer gets credit for a subsequent event. If you use [report time processing](../../../components/vrs/vrs-report-time-processing.md), both props and eVars can use any attribution model that you'd like.
