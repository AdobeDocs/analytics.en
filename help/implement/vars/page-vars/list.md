---
title: list
description: Custom variables that hold multiple values in the same hit.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
---
# list

List variables are custom variables that you can use however you'd like. They work similarly to eVars, except they can contain multiple values in the same hit. List variables do not have a character limit.

Make sure you record how you use each list variable and their logic in your [solution design document](../../prepare/solution-design.md).

>[!NOTE]
>
>List variables store the most recent 250 values per visitor. If there are more than 250 unique values for a given visitor, the oldest values are not attributed to metrics.

## Set up list variables in report suite settings

Make sure that you configure each list variable in report suite settings before using them in your implementation. See [Conversion variables](/help/admin/admin/conversion-var-admin/list-var-admin.md) in the Admin guide. This step applies to all implementation methods.

## List variables using the Web SDK

List variables are [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM fields `_experience.analytics.customDimensions.lists.list1.list[]` to `_experience.analytics.customDimensions.lists.list3.list[]`. Each array element contains a `"value"` object that contains each string. There is no need to provide a delimiter. It will be automatically included using the value specified in [Report suite settings](/help/admin/admin/conversion-var-admin/list-var-admin.md). For example, if a comma ('`,`') is configured as the delimiter for list variable 1, the following XDM object would populate the `list1` variable with `"Example value 1,Example value 2,Example value 3"`.

```json
"xdm": {
    "_experience": {
        "analytics": {
            "customDimensions": {
                "lists": {
                    "list1": {
                        "list": [
                            {
                                "value": "Example value 1"
                            },
                            {
                                "value": "Example value 2"
                            },
                            {
                                "value": "Example value 3"
                            }
                        ]
                    }
                }
            }
        }
    }
}
```

>[!NOTE]
>
>The Adobe XDM schema contains `key` objects in addition to `value` objects in each `list[]` array. Adobe does not use these `key` objects when sending data to Adobe Analytics.

## List variables using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.list1 - s.list3 in AppMeasurement and the Analytics extension custom code editor

Each list variable is a string that contains custom values specific to your organization. They do not have a maximum byte count; however, each individual value has a maximum of 255 bytes. The delimiter that you use is determined when setting up the variable in [Report suite settings](/help/admin/admin/conversion-var-admin/list-var-admin.md). Do not use spaces when delimiting multiple items.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>If you set duplicate values in the same hit, Adobe de-duplicates all instances of those values. For example, if you set `s.list1 = "Brick,Brick";`, one instance is counted in reports.

## Compare list props to list vars

List props and list vars can both contain multiple values in the same hit. However, there are several key differences between these two variable types.

* Any prop can become a list prop. You effectively can have up to 75 list props, if every prop is a list prop. There are only 3 list vars available.
* List props have a 100-byte limit for the entire variable. List variables have a 255-byte limit per value, and no total byte limit.
* List props do not persist beyond the hit they are set. List variables have any expiration setting that you want. However, with [report time processing](/help/components/vrs/vrs-report-time-processing.md), you can apply custom attribution to both list props and list variables.
