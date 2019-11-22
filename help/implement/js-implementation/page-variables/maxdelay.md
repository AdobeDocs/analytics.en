---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# maxDelay

The s.maxDelay variable is used primarily in Genesis DFA integrations to determine the timeout period in contacting the DFA host. If Adobe does not receive a response from DFA's servers within the specified period set in the  variable, the connection is severed, and data is processed normally. Implement this variable if you are concerned with DFA's response time on each page. It is recommended to experiment with this value to determine the optimum timeout period.


<!-- 

maxDelay.xml

 -->

**Implementation Example**

```
s.maxDelay="750";
```

**Properties**

* This variable is an optional event metric populated via the JavaScript implemented on your site.
* If the DFA host does not respond within the given amount of time, the event designated to Timeout runs (assigned via the Genesis integration wizard).
* This variable can only contain a numeric value.
* The amount of time specified is measured in milliseconds.
* Increasing the wait time collects more DFA data, but also increases the risk of losing Analytics hit data.

  Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* Decreasing the wait time will lower the risk of losing Analytics hit data, but can reduce the amount of DFA data sent with hit data.

  Losing DFA integration data would occur when the *`s.maxDelay`* period does not accommodate enough time for the DFA host to respond.

> [!NOTE] Adobe does not have control over DFA's response time. If you are seeing consistent issues even after raising the max delay period to a reasonable time frame, consult your organization's DFA account administrator.
