---
title: Exits
description: An instance of the last value in a visit.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Exits

*This help page describes how exits work as a metric. For information on how exits work as a dimension, see [Exit dimensions](../dimensions/exit-dimensions.md).*

The 'Exits' [metric](overview.md) shows the number of times a given dimension item is captured as the last value in a visit. This metric is helpful when you want to understand more about the last thing visitors see before leaving your site. Seeing the last values of a dimension can help you understand and optimize the experience a visitor gets before they leave.

## How this metric is calculated

After a [visit](visits.md) concludes, record the most recent dimension item as an exit. Only one exit exists per dimension per visit. It is not necessarily the last hit of the visit if the dimension was set in previous hits. It is a visit-based metric; it retroactively applies to all hits in the visit.

>[!TIP]
>
>If you view this metric against a dimension not always set in every visit, you can hide the 'Unspecified' dimension item in Analysis Workspace. Click the filter icon, then uncheck [!UICONTROL Include unspecified (None)].
