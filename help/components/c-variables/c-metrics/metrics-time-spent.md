---
description: Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.
solution: Analytics
title: Time Spent
topic: Metrics
---

# Time spent 

Various 'time spent' metrics and dimensions are offered across Adobe Analytics products.

## 'Time spent' metrics

|Metric|Definition|Available in|
|---|---|---|
|Total seconds spent|Represents the total amount of time visitors interact with a specific dimension item. Includes the instance of a value & persistence across all subsequent hits. In the case of props, time spent is counted across subsequent link events as well.|Analysis Workspace, Reports & Analytics, Report Builder (called ‘total time spent’), Data Warehouse|
|Time spent per visit (Seconds)|*Total seconds spent / (visit-bounces)*<br>Represents the average amount of time visitors interact with a specific dimension item during each visit.|Analysis Workspace, Reports & Analytics|
|Time spent per visitor (Seconds)|*Total seconds spent / unique visitor*<br>Represents the average amount of time visitors interact with a specific dimension item across the visitor’s lifetime (length of their cookie).|Analysis Workspace, Reports & Analytics|
|Average time spent on site (Seconds)|Represents the total amount of time visitors interact with a specific dimension item, per sequence with a dimension item. It is not just limited to “site” averages as the name suggests. See the "How Time Spent is Calculated" section for more information on sequences.<br>**Note**: This metric very likely differs from 'Time Spent per Visit' at a dimension item level due to the differences in the denominator in the calculation.|Analysis Workspace, Reports & Analytics (shown in minutes), Report Builder (shown in minutes)|
|Average time spent on page|Deprecated metric.<br> Instead, we recommend that you use ‘Average time spent on site’ if average time for a dimension item is needed.|Report Builder (when a dimension is in the request)|
|Total session length, a.k.a. Previous session length|Mobile App SDK only. <br>Determined the next time the app is launched, for the previous session. Calculated in seconds, this metric does not count when the app is in the background, only when in use. This is a session-level metric.<br>Example: We install app ABC and launch and use it for 2 minutes and then close the app. No data is sent about this session time. The next time we launch the app, Previous Session Length will be sent with a value of 120.|Analysis Workspace, Reports & Analytics, Report Builder, Mobile Services UI |
|Average session length (mobile)|*Total Session Length / (Launches – First Launches)*<br>Mobile App SDK only. This is a session-level metric.|Report Builder, Mobile Services UI|

## 'Time spent' dimensions

