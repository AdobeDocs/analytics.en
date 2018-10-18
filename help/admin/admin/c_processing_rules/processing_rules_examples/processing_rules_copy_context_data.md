---
description: Processing rules are used to move values from Context Data variables to props and eVars.
seo-description: Processing rules are used to move values from Context Data variables to props and eVars.
seo-title: Copy a context data variable to an eVar
solution: Analytics
subtopic: Processing rules
title: Copy a context data variable to an eVar
topic: Admin tools
uuid: cfcc21f9-eb2f-4e06-b330-d6d32c239f21
index: y
internal: n
snippet: y
---

# Copy a context data variable to an eVar

Processing rules are used to move values from Context Data variables to props and eVars.

Context data variables are specified in AppMeasurement in the following format:

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

The following rule definition populates an eVar on every hit that contains a specific context data variable: 

|  Rule Set  | Value  |
|---|---|
|  Condition  | If 'search_term' context data is set  |
|  Action  | Overwrite value of eVar3 to 'search_term'  |

For example:

![](assets/set-context-data.png)

See [Context Data Variables](http://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) in Implementation Help. 
