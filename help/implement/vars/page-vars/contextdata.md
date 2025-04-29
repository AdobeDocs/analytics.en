---
title: contextData
description: Context data variables let you define custom variables on each page that processing rules can read.
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
---
# contextData

Context data variables let you define custom variables on each page that processing rules can read. Instead of explicitly assigning values to Analytics variables in your code, you can send data in context data variables. Processing rules then take context data variable values and pass them into respective Analytics variables. See [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) in the Admin user guide.

Context data variables are helpful for development teams to collect data in named elements instead of numbered variables. For example, instead of requesting development teams assign the page's author to `eVar10`, you can request they assign it to `s.contextData["author"]` instead. An Analytics administrator in your organization can then create processing rules to map context data variables into analytics variables for reporting. Development teams would ultimately only worry about context data variables instead of the many page variables that Adobe offers.

## Context data variables using the Web SDK

If using the [**XDM object**](/help/implement/aep-edge/xdm-var-mapping.md), all fields that don't map to an Adobe Analytics variable are automatically included as a context data variable. You can also explicitly set context data using the XDM object. You can then use [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) to assign the context data variable to the desired Analytics variable.  See [Mapping other XDM fields to Analytics variables](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables) for more information.

If using the [**data object**](/help/implement/aep-edge/data-var-mapping.md), all context data variables reside within `data.__adobe.analytics.contextData` as key-value pairs:

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

The [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) interface would show `example_variable` and `second_example` in applicable drop-down menus.

## Context data variables using the Adobe Analytics extension

Adobe Experience Platform Data Collection does not have a dedicated location to set context data variables. Use the custom code editor, following AppMeasurement syntax.

## s.contextData in AppMeasurement and the Analytics extension custom code editor

The `s.contextData` variable does not directly take a value. Instead, set the properties of this variable to a string.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Valid context data variables contain only alpha-numeric characters, underscores, and periods. Adobe does not guarantee data collection in processing rules if you include other characters, such as hyphens.
* Do not start context data variables with `"a."`. This prefix is reserved and used by Adobe. For example, do not use `s.contextData["a.InstallEvent"]`.
* Context data variables are not case-sensitive. The variables `s.contextData["example"]` and `s.contextData["EXAMPLE"]` are identical.
* A single key cannot contain more than one value. If you want to use context data variables for multi-value variables, concatenate all values using a delimiter (typically a comma) and pass it into either a [list prop](prop.md#list-props) or a [list variable](list.md) using processing rules.

## Use processing rules to populate analytics variables

>[!WARNING]
>
>Context data variables are discarded after processing rules run. If you do not have processing rules active that place values into variables, that data is permanently lost!

1. Update your implementation to set context data variable names and values.
2. Log in to Adobe Analytics and go to **[!UICONTROL Admin]** > **[!UICONTROL Report]** Suites.
3. Select the desired report suite, then go to **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
4. Create a processing rule that sets an Analytics variable to the context data variable value.
5. Save changes.

Processing rules immediately take effect once saved. They do not apply to historical data.

## Send context data in a link tracking call

Include the context data variable as a property of `contextData` in [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Increment events using context data variables

When creating processing rules, you can assign context data variables to events.

* If a context data variable contains any kind of text, the event increments by one.
* If a context data variable contains an integer, the event increments by that integer amount.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
