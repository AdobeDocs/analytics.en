---
title: contextData
description: Context data variables let you define custom variables on each page that processing rules can read.
---

# contextData

Context data variables let you define custom variables on each page that processing rules can read. Instead of explicitly assigning values to Analytics variables in your code, you can send data in context data variables. Processing rules then take context data variable values and pass them into respective Analytics variables. See [Processing rules](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) in the Admin user guide.

Context data variables are helpful for development teams to collect data in named elements instead of numbered variables. For example, instead of requesting development teams assign the page's author to `eVar10`, you can request they assign it to `s.contextData["author"]` instead. An Analytics administrator in your organization can then create processing rules to map context data variables into analytics variables for reporting. Development teams would ultimately only worry about context data variables instead of the many page variables Adobe offers.

## Context data variables in Adobe Experience Platform Launch

Launch does not have a dedicated location to set context data variables. Use the custom code editor, following AppMeasurement syntax.

## s.contextData in AppMeasurement and Launch custom code editor

The `s.contextData` variable does not directly take a value. Instead, set properties of this variable to a string.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Valid context data variables contain only alpha-numeric characters, underscores, and periods. Adobe does not guarantee data collection in processing rules if you include other characters, such as hyphens.
* Do not start context data variables with `"a."`. This prefix is reserved and used by Adobe. For example, do not use `s.contextData["a.InstallEvent"]`.
* Context data variables are not case-sensitive. The variables `s.contextData["example"]` and `s.contextData["EXAMPLE"]` are identical.

## Use processing rules to populate analytics variables

> [!IMPORTANT] Context data variables are discarded after processing rules run. If you do not have processing rules active that place values into variables, that data is permanently lost!

1. Update your implementation to set context data variable names and values.
2. Log in to Adobe Analytics and go to Admin > Report Suites.
3. Select the desired report suite, then go to Edit Settings > General > Processing Rules.
4. Create a processing rule that sets an Analytics variable to the context data variable value.
5. Save changes.

Processing rules immediately take effect once saved. They do not apply to historical data.

## Send context data in a link tracking call

Include the context data variable as a property of `contextData` in `s.linkTrackVars`:

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
