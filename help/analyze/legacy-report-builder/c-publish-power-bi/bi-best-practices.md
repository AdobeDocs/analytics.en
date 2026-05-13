---
description: Power BI best practices.
title: Best practices
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
TQID: https://experienceleague.adobe.com/WXvRDft1TRz5qM9R8Psz-Yp2qY-AL-SrrXgXWRx55N0
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
# Best practices

{{legacy-arb}}

## Preserve references in Power BI visualizations

Once you create a request, that request will always have the same reference in Power BI. But if you delete a request, the reference will be used by a new request you create for the same dimension.

If you delete a request in your workbook, make sure that you do not have a visualization pointing to that request in Power BI, because otherwise the visualization will break.

* If at all possible, do not delete requests you created in Report Builder
* Make sure that if you do delete requests on Report Builder, you also delete the corresponding visualization in Power BI.
* If you aren't sure: delete requests you do not need any more, then republish and go to Power BI to see which visualizations have broken
