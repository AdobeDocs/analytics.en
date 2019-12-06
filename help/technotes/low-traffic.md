---
description: When a report has a large number of unique values, Adobe provides functionality to ensure that the most important values appear in your report.
title: Low-traffic value in Adobe Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
---

# Low-traffic value in Adobe Analytics

When a report has a large number of unique values, Adobe provides functionality to ensure that the most important values appear in your report. Unique variable values collected after approximately 500,000 existing values are listed under a line item titled **(Low-Traffic)**.

## How low-traffic works

* Reporting is not affected if the variable does not reach 500,000 unique values in a given month.
* When a variable reaches this first threshold of 500,000, data begins to be bucketed under low-traffic. Each value beyond this threshold goes through the following logic:
  * If a value is already in reports, add to that value as usual.
  * If a value is not yet in reporting, check to see if that value was seen more than approximately ten times today. If it has, add this value to reporting. If it hasn't been counted more than about ten times, leave it under low-traffic.
* If a report suite reaches more than 1,000,000 unique values, more aggressive filtering is applied:
  * If a value is already in reports, add to that value as usual.
  * If a value is not yet in reporting, check to see if that value was seen more than approximately 100 times today. If it has, add the value to reporting. If it hasn't, leave it under low-traffic.

> [!NOTE] If a variable value receives enough traffic to leave the low-traffic bucket, the first values collected do not move to its respective line item. Those first 10-100 instances stay under low-traffic.

## Changing unique limit thresholds

Threshold limits are 500,000 and 1 million unique values by default. These limits can be changed on a per-variable basis. Contact your organization's account manager to request this change. When requesting a change, include:

* The report suite ID
* The variable you would like to increase the threshold for
* Both the first and second threshold desired

Changes to thresholds can impact report performance. Adobe highly recommends using good judgment when requesting an increase to unique values in a variable.

Low-traffic thresholds are not visible in the Analytics UI. Please have a supported user in your organization contact Adobe Customer Care if you would like more information on existing thresholds.

## Low-traffic using components and other capabilities

Different capabilities treat low-traffic values in different ways.

* **Data Warehouse:** There is no limit to the number of unique values in Data Warehouse reports. Its unique architecture allows the reporting of any number of unique values.
  * In some limited scenarios, low-traffic values can still appear. Examples include list vars, list props, merchandising eVars, and marketing channel detail dimensions.
* **Segmentation:** If the segment criteria includes a variable with a high number of unique values, values captured under low-traffic are not included.
* **Classifications:** Classification reports are also subject to unique limits. If a classification's parent variable value is included under low-traffic, the value is not classified.
  * If you classify values before they are seen in data, those values count toward the unique threshold for that month.
