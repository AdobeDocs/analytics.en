---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# propN

Property ( [!UICONTROL prop]) variables are used for building custom reports within the [!UICONTROL Traffic Module].

<!-- 

propN.xml

 -->

The props variable may be used as counters (to count the number of times a page view is sent), for pathing reports, or in correlation reports.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 bytes  | c1-c75  | Custom Traffic  | ""  |

**Syntax and Possible Values** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

There are no limitations on [!UICONTROL property] variables outside of the standard variable limitations.

**Examples** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 

```

```js
s.prop15="toy category"
```

**Configuration Settings** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Contact Adobe Customer Care about showing [!UICONTROL Visit], [!UICONTROL Visitor], and [!UICONTROL Path] metrics for [!UICONTROL prop] variables.
