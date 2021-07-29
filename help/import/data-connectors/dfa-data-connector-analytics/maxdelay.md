---
title: maxDelay
description: Determine the maximum amount of time that AppMeasurement waits for a response from DFA before sending an image request.
exl-id: 154f7e34-39e7-4390-ae36-d4fbc998787f
---
# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. If Adobe does not receive a response from DFA's servers within the specified period set in this variable, the connection is severed, and data is processed normally. Include this variable in your implementation if you are concerned with DFA's response time on each page. Adobe recommends experimenting with this value to determine the optimum timeout period.

This variable is only used in implementations using the DFA data connector. Even with implementations using DFA, this variable is optional.

## Max Delay using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.maxDelay in AppMeasurement and custom code editor

The `s.maxDelay` variable is an integer representing the number of milliseconds AppMeasurement waits for a response from DFA. If AppMeasurement doesn't receive a response from DFA in time, an image request is sent to Adobe without DFA data.

```js
s.maxDelay = 750;
```

## Properties

* Increasing the wait time collects more DFA data, but also increases the risk of losing Analytics hit data. Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* Decreasing wait time lowers the risk of losing Analytics hit data, but can reduce the amount of DFA data sent with hit data.
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

>[!NOTE]
>
>Adobe does not have control over DFA's response time. If you see consistent issues even after raising the max delay period to a reasonable time frame, consult your organization's DFA account administrator.
