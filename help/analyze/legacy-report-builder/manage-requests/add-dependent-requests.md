---
description: Learn about adding dependent requests.
title: How to add dependent requests
uuid: 243619db-81b4-40cc-88c4-e93a14f6993b
feature: Report Builder
role: User, Admin
exl-id: e45eef96-0bd2-4c5a-b1d1-cd41390c08d4
TQID: https://experienceleague.adobe.com/EqZhxywH6nUN2ulkJvcamtODaAMPBFWLvJiCnmC490c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Add dependent requests

{{legacy-arb}}

A dependent request is a request that is dependent upon an existing request.

For reports with correlation breakdowns enabled within the report table, to take a closer look at an item,  right-click in the cell and then click **[!UICONTROL Add Dependent Request]** > **[!UICONTROL Breakdown]**.

>[!NOTE]
>
>You can also add a breakdown request when you create the original request. See [Create a Data Request](/help/analyze/legacy-report-builder/data-requests/t-create-a-data-request.md).

>[!NOTE]
>
>Adobe Report Builder enforces request dependencies only within the same worksheet, not across worksheets. Restricting to dependencies within a single worksheet ensures timeliness of execution.

