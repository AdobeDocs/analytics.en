---
description: You can specify a date range by selecting cells from a worksheet that contains a request. Report builder uses the specific date range information in those requests. If you select today's date, you see partial data based on the time of day the request runs.
title: Dates from a cell
uuid: 0d9bf08d-d39d-4f37-94f1-232da0813245
feature: Report Builder
role: User, Admin
exl-id: e10573cc-984e-4202-a797-c2c9bec2af96
TQID: https://experienceleague.adobe.com/9-U5bdrNbEahhtBuJA4ylaXzGEgH01q1z7FBR2w5sPs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Dates from a cell

{{legacy-arb}}

You can specify a date range by selecting cells from a worksheet that contains a request. Report builder uses the specific date range information in those requests. If you select today's date, you see partial data based on the time of day the request runs.

 **To configure dates from a cell** 

1. On the [!UICONTROL Request Wizard: Step 1], select **[!UICONTROL Dates From Cell]**.
1. Enter cell references in the **[!UICONTROL From]** and **[!UICONTROL To]** fields, or click the selector and select the cells containing the requests with the starting and ending dates.

   For example, create a Report Builder request with the date range set to "yesterday" and output the request date in the same cell as "today()-1".

Here is a list of supported date formats:

![Screenshot showing supported date formats.](assets/date-formats.png)

