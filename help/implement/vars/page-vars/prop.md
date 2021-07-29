---
title: prop
description: Custom variables you can use in your implementation.
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
---
# prop

*This help page describes how to implement props. For information on how props work as a dimension, see [prop](/help/components/dimensions/prop.md) in the Components user guide.*

Props are custom variables that you can use however you'd like. They do not persist beyond the hit that they are set.

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. In previous versions of Adobe Analytics, props and eVars had advantages and disadvantages to each other. However, Adobe has improved eVars to where they fulfill almost all use cases for props.

If you have a [solution design document](/help/implement/prepare/solution-design.md), you can allocate these custom dimensions to values specific to your organization. The number of available props depends on your contract with Adobe. Up to 75 props are available if your contract with Adobe supports it.

## Props using tags in Adobe Experience Platform

You can set props either while configuring the Analytics extension (global variables) or under rules.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Props] section.

You can set a prop to a value or a data element. You can also copy the value from another Analytics variable.

## s.prop1 - s.prop75 in AppMeasurement and custom code editor

Each prop variable is a string that contains custom values specific to your organization. Their max length is 100 bytes; values longer than 100 bytes are automatically truncated when sent to Adobe.

```js
s.prop1 = "Example custom value";
```

## List props

List props are a setting applied to props that allow the variable to hold multiple values in the same hit. If this setting is not enabled, or if the wrong delimiter is used, the variable is treated as a single value.

### Configure list props

Enable list props in report suite settings. See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. Make sure that the desired delimiter is configured correctly. Adobe does not provide a default delimiter.

>[!TIP]
>
>Common delimiters used in implementations are a comma (`,`), colon (`:`), semicolon (`;`), or pipe (`|`). You can use any delimiter that best fits your implementation.

### Set list props

Once you configure list props in report suite settings with the desired delimiter, there are no implementation differences other than using the delimiter.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>List props are still subject to the 100-byte maximum length. List props are easier to hit this limit and be truncated, since they can contain multiple values. Consider using abbreviations or shortening values if you might hit this 100-byte limit.

If you set the same value more than once in a list prop, they are de-duplicated in reporting. Analysis Workspace counts the number of hits where a value is seen, and not the number of times a value exists in data.
