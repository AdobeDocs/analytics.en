---
description: When a report has a large number of unique values, Adobe provides functionality to ensure that the most important values appear in your report.
title: Low-traffic value in Adobe Analytics
feature: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
---
# Low-traffic value in Adobe Analytics

When a report has many unique values, Adobe provides functionality to ensure that the most important values appear in your report. Unique variable values collected after approximately 500,000 existing values are listed under a line item titled **[!UICONTROL Low-Traffic]**.

## How [!UICONTROL Low-Traffic] works

* Reporting is not affected if the variable does not reach 500,000 unique values in a given month.
* When a variable reaches this first threshold of 500,000, data begins to be bucketed under low-traffic. Each value beyond this threshold goes through the following logic:
  * If a value is already seen in reports, add to that value as usual.
  * If a value is not yet seen in reports, it will appear in the [!UICONTROL Low-Traffic] line item. If a value that has been included in the [!UICONTROL Low-Traffic] line item is seen a significant number of times within a short time, it will start being recognized as its own line item. The significant number of times that an item has to be seen has many dependencies, such as the number of processing servers and daemons that are processing data for that particular report suite.
* If a report suite reaches more than 1,000,000 unique values, more aggressive filtering is applied:
  * If a value is already seen in reports, add to that value as usual.
  * If a value is not yet seen in reports, it will appear in the [!UICONTROL Low-Traffic] line item. If a value that has been included in the [!UICONTROL Low-Traffic] line item is seen a significant number of times within a short time, it will start being recognized as its own line item. The significant number of times that an item has to be seen has many dependencies, such as the number of processing servers and daemons that are processing data for that particular report suite.

Why does Adobe move an item from the [!UICONTROL Low Traffic] line item to its own line item? For example, this move might recognize a popular new page or new item that was added later in the month (after uniques were exceeded) and that gets a lot of hits/views. The move is not intended to catch everything that gets a certain number of hits/views per day or per month.

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
  * Low-traffic classification values obtained through the importer can be viewed in Data Warehouse. <!-- AN-115871 -->
  * Low-traffic classification values obtained through the rule builder *cannot* be viewed in Data Warehouse. <!-- AN-122872 -->
