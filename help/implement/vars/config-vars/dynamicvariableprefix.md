---
title: dynamicVariablePrefix
description: Lets you customize the string that identifies dynamic variables.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
---
# dynamicVariablePrefix

Dynamic variables are a shorthand concept that let you copy values from one variable to another. They are valuable for long variable values, as they help shorten an image request's URL length. See [Dynamic variables](../page-vars/dynamic-variables.md) for more information on this concept.

By default, dynamic variables use the prefix `D=`. The `dynamicVariablePrefix` variable lets you customize the string that identifies dynamic variables. It is case-sensitive.

## Dynamic variable prefix using the Web SDK

The Web SDK does not use dynamic variable formatting. Instead, you can use Datastream mapping to populate multiple Target Fields using a single Source Field. See [Dynamic variables using the Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) for more information.

## Dynamic Variable Prefix using the Adobe Analytics extension

Dynamic Variable Prefix is a field under the [!UICONTROL Global Variables] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL Global Variables] accordion, which reveals the [!UICONTROL Dynamic Variable Prefix] field.

This field contains `D=` by default. You can change the value if you want to use a different dynamic variable prefix. You can use any value you want, as long as it matches the character encoding on your site.

## s.dynamicVariablePrefix in AppMeasurement and the Analytics extension custom code editor

The `s.dynamicVariablePrefix` variable is a string that can contain any sequence of characters. If this variable is not defined, AppMeasurement uses the string `D=` by default.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
