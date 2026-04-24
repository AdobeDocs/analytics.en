---
title: Consent Management Opt-In
description: See which privacy settings that a visitor opted in to.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Consent Management Opt-In

The 'Consent Management Opt-In' [dimension](overview.md) displays which privacy settings that a visitor has opted in to. You can use this dimension to filter data based on privacy settings, or see the most common privacy opt-in reasons.

## Populate this dimension with data

This dimension collects data from the following [Context data variables](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` when set to `Y`. If `opt.dmp` equals `N`, the [Consent Management Opt-Out](cm-opt-out.md) dimension is populated instead.
* `contextData.['opt.sell']` when set to `Y`. If `opt.sell` equals `N`, the [Consent Management Opt-Out](cm-opt-out.md) dimension is populated instead.

Your organization determines the logic to implement these context data variables. They do not persist beyond the hit that they are set on, so you must set each context data variable on each page.

## Dimension items

Dimension items include the following two values:

* **`DMP`**: The visitor opted in to sharing to data management platforms. This dimension item is present when the context data variable `opt.dmp` equals `Y`.
* **`SELL`**: The visitor opted in to the sharing or selling of the data to third parties. This dimension is present when the context data variable `opt.sell` equals `Y`.
