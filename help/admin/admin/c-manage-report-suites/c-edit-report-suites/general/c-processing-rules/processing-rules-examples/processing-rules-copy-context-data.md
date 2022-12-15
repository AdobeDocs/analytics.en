---
description: Processing rules are used to move values from Context Data variables to props and eVars.
subtopic: Processing rules
title: Copy a context data variable to an eVar
feature: Admin Tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
---
# Copy a context data variable to an eVar

Processing rules are used to move values from context data variables to props and eVars. Without processing rules, context data variables are meaningless and do not populate any reports in Analytics.

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![Add](assets/add-context-variable.png)

The following example takes the `search_term` context data variable and places its value into `eVar3`:

![Set](assets/set-context-data.png)

The above example works great when there are only a few eVars to populate. If your organization has hundreds of context data variables that each need their own eVar, you can use conditional statements. Dozens of conditional statements can fit inside a single processing rule, allowing your organization the ability to populate all eVars in a report suite without running into the processing rule limit of 150 rules.

The following example populates `prop7` with the context data variable `testhierarchy`, but only if `testhierarchy` is set:

![Conditional](assets/add-conditional.png)

For more information on implementing context data variables, see [Context data variables](/help/implement/vars/page-vars/contextdata.md) in the Implement user guide.
