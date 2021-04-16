---
description: You can populate a variable using a query string parameter.
subtopic: Processing rules
title: Populate a campaign ID from a query string parameter
feature: Admin Tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
---
# Populate a campaign ID from a query string parameter

You can populate a variable using a query string parameter.

In most cases you use a plug-in to populate variables from the query string. If a typo or similar issue prevents the value from being populated, you can populate the variable using processing rules.

You should always check to see if a value is empty or contains the expected value before you overwrite it.

|  Rule Set  | Value  |
|---|---|
|  Condition  | Campaign is Not Set  |
|  Action  | Overwrite value of Campaign to Query String Parameter cpid  |

For example:

![](assets/set-campaign-conditionally.png)
