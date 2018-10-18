---
description: You can populate a variable using a query string parameter.
seo-description: You can populate a variable using a query string parameter.
seo-title: Populate a campaign ID from a query string parameter
solution: Analytics
subtopic: Processing rules
title: Populate a campaign ID from a query string parameter
topic: Admin tools
uuid: 25b5c855-976f-4331-9d29-26fc476de0ce
index: y
internal: n
snippet: y
---

# Populate a campaign ID from a query string parameter

You can populate a variable using a query string parameter.

In most cases you use a plugin to populate variables from the query string. If a typo or similar issue prevents the value from being populated, you can populate the variable using processing rules.

You should always check to see if a value is empty or contains the expected value before you overwrite it. 

|  Rule Set  | Value  |
|---|---|
|  Condition  | Campaign is Not Set  |
|  Action  | Overwrite value of Campaign to Query String Parameter cpid  |

For example:

![](assets/set-campaign-conditionally.png)

