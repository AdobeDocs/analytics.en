---
description: Common issues when using Report Builder with Power BI.
title: Troubleshooting Power BI integration
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
---
# Troubleshooting Power BI integration

Research and resolve common issues when using Report Builder with Power BI.

## Failure to publish to Power BI

Scheduled workbooks that require Power BI publishing are dependent on Power BI services to be up and running. Two main reasons for a failure to publish are:

* Power BI services may be down.
* The user who scheduled the workbook no longer has valid Microsoft account credentials.

Each Report Builder scheduled task gets three tries per scheduled run:

* After the first unsuccessful attempt, you will get this message: ""We were unable to publish this scheduled workbook to Microsoft Power BI. We will try again shortly." 
* After the second unsuccessful attempt, you will get no message.
* After the third unsuccessful attempt, you will get this message: "We were unable to publish this workbook to Power BI."

## Broken visualizations in Power BI

Here are the top reasons why you could end up with broken visualizations after publishing Report Builder requests to Power BI:

* You edited a request in Report Builder, such as changing metrics or dimensions and then republished to Power BI. Editing requests can break your visualizations.
* You deleted a request that was used in a visualization.

## Report Builder needs to be authorized to access your organization resources. This access can only be granted by an admin. Ask an admin to grant you permission.

Have a Microsoft Admin review the "Users can register application" setting found under: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. If this option is set to No, then that admin can register these types of applications.

Users can grant Access by using the following [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Admins granted access for every one by using the following [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).
## Reaching the API limit

Reporting in power bi works on analytics reporting api, API threshold limits will be applicable here as well.For the Analytics 2.0 APIs, the throttle limit is set at 120 calls per minute, per user, regardless of report suite or company. When the throttle limit is crossed, the server returns an HTTP 429 status to the user the with message content: "too many requests"
{"error_code":"429050","message":"Too many requests"}
Adobe recommends adhering to the following guidelines:

Make multiple, smaller requests instead of a large, single request.
Request data once and cache it.
Do not poll for new data faster than a 30 minute interval.
Pull historical data and increment it regularly instead of requesting the entire data set.
Adobe recommends avoiding the following:

Requesting as much data as possible in a single request
Requesting one year of data at day granularity everyday to get a rolling 12-month window. Adobe recommends that you instead request the new day's data and merge it with the existing data from previous days.
Driving a web page with a site performance widget by making an API request every time the web page is loaded
Migrating from 1.4

