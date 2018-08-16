---
description: Here are a few common pitfalls when using Report Builder with Power BI.
seo-description: Here are a few common pitfalls when using Report Builder with Power BI.
seo-title: Troubleshooting Power BI integration
title: Troubleshooting Power BI integration
uuid: 1dd790e5-739f-4e62-b57c-97197bd394d1
index: y
internal: n
snippet: y
translate: y
---

# Troubleshooting Power BI integration


* [ Failure to Publish to Power BI](../../report_builder_bucket/power_bi/troubleshooting.md#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B)
* [ Broken Visualizations in Power BI](../../report_builder_bucket/power_bi/troubleshooting.md#section_FFFE200D06F843B2AF093710FD678166)

## 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Scheduled workbooks that require Power BI publishing are dependent on Power BI services to be up and running. Two main reasons for a failure to publish are: 

* Power BI services may be down.
* The user who scheduled the workbook no longer has valid Microsoft account credentials.
Each Report Builder scheduled task gets three tries per scheduled run: 

* After the first unsuccessful attempt, you will get this message: ""We were unable to publish this scheduled workbook to Microsoft Power BI. We will try again shortly."
* After the second unsuccessful attempt, you will get no message.
* After the third unsuccessful attempt, you will get this message: "We were unable to publish this workbook to Power BI."

## 2. Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Here are the top reasons why you could end up with broken visualizations after publishing Report Builder requests to Power BI: 

* You edited a request in Report Builder, such as changing metrics or dimensions and then republished to Power BI. Editing requests can break your visualizations.
* You deleted a request that was used in a visualization.
