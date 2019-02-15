---
description: Here are a few common pitfalls when using Report Builder with Power BI.
seo-description: Here are a few common pitfalls when using Report Builder with Power BI.
seo-title: Troubleshooting Power BI integration
title: Troubleshooting Power BI integration
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
---

# Troubleshooting Power BI integration

Here are a few common pitfalls when using Report Builder with Power BI.

## Step 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Scheduled workbooks that require Power BI publishing are dependent on Power BI services to be up and running. Two main reasons for a failure to publish are:

* Power BI services may be down. 
* The user who scheduled the workbook no longer has valid Microsoft account credentials.

Each Report Builder scheduled task gets three tries per scheduled run:

* After the first unsuccessful attempt, you will get this message: ""We were unable to publish this scheduled workbook to Microsoft Power BI. We will try again shortly." 
* After the second unsuccessful attempt, you will get no message. 
* After the third unsuccessful attempt, you will get this message: "We were unable to publish this workbook to Power BI."

## Step 2. Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Here are the top reasons why you could end up with broken visualizations after publishing Report Builder requests to Power BI:

* You edited a request in Report Builder, such as changing metrics or dimensions and then republished to Power BI. Editing requests can break your visualizations. 
* You deleted a request that was used in a visualization.

