---
description: Common issues when using Report Builder with Power BI.
title: Troubleshooting Power BI integration
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Troubleshooting Power BI integration

{{legacy-arb}}

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

>[!IMPORTANT]
>
>Report Builder requires an administrator to authorize access to your organization resources. If you need access, ask an administrator to grant you permission.
> A Microsoft Admin can review the *Users can register application* setting found under: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. If this option is set to **No**, then the admin can register these types of applications.

Users can grant Access by logging into their [Microsoft Power BI account](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Admins can grant access for every one by logging into their [Administrator's Microsoft Power BI account](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

## Reaching the API limit

Reporting in Power BI works with the Analytics Reporting API, so API threshold limits apply.
