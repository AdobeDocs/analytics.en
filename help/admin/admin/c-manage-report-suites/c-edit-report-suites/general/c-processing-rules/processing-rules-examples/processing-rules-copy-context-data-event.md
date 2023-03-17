---
description: Processing rules can trigger events based on Context Data variables.
subtopic: Processing rules
title: Set an event using a context data variable
feature: Admin Tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
---
# Set an event using a context data variable

Processing rules can trigger events based on Context Data variables.

Context data variables are specified in AppMeasurement in the following format:

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

The following rule definition expands on the [Copy a Context Data Variable to an eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) rule to also set an event on every hit that contains a specific context data variable: 

|  Rule Set  | Value  |
|---|---|
|  Condition  | If 'search_term' context data is set  |
|  Action  | Set event 'searches'  |

For example:

![](assets/processing_rule_set_event.png)

See [Context Data Variables](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html) in Implementation Help.
