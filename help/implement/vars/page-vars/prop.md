---
title: prop
description: Custom variables you can use in your implementation.
---

# prop

Props are custom variables that you can use however you'd like.

> [!TIP] Adobe recommends using eVars in most cases. In previous versions of Adobe Analytics, props and eVars had advantages and disadvantages to each other. However, Adobe has improved eVars to where they fulfill almost all use cases for props. See [eVars](evar.md) for a feature comparison between these two custom variable types.

If your organization uses props, make sure you record their use and logic in your [solution design document](../../../prepare/solution-design.md).

## Props in Adobe Experience Platform Launch

You can set props either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Props] section.

You can select a prop to set a value or data element. You can also copy the value from another Analytics variable.

## s.prop1 - s.prop75 in AppMeasurement and Launch custom code editor

Each prop variable is a string that contains custom values specific to your organization. Their max length is 100 bytes; values longer than 100 bytes are automatically truncated when sent to Adobe.

```js
s.prop1 = "Example custom value";
```

## List props

List props are a setting applied to props that allow the variable to hold multiple values in the same hit. If this setting is not enabled, or if the wrong delimiter is used, the variable is treated as a single value.

## Configure list props

Enable list props in report suite settings. See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. Make sure that the desired delimiter is configured correctly. Adobe does not provide a default delimiter.

> [!TIP] Common delimiters used in implementations are a comma (`,`), colon (`:`), semicolon (`;`), or pipe (`|`). You can use any delimiter that best fits your implementation.

## Set list props

Once you configure list props in report suite settings with the desired delimiter, there are no implementation differences other than using the delimiter.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] List props are still subject to the 100-byte maximum length. List props are easier to hit this limit and be truncated, since they can contain multiple values. Consider using abbreviations or shortening values if you might hit this 100-byte limit.
