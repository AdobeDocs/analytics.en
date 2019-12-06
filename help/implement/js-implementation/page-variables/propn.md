---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---

# propN

Property (`prop`) variables are used for building custom reports within the Traffic Module.


<!-- 

propN.xml

 -->

The props variable may be used as counters (to count the number of times a page view is sent), for pathing reports, or in correlation reports.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 bytes  | c1-c75  | Custom Traffic  | ""  |

**Syntax and Possible Values** 

```js
s.propN="value"
```

There are no limitations on [!UICONTROL property] variables outside of the standard variable limitations.

**Examples** 

```js
s.prop2="editorial" 

```

```js
s.prop15="toy category"
```

**Configuration Settings** 

Contact Adobe Customer Care about showing Visit, Visitor, and Path metrics for `prop` variables.
