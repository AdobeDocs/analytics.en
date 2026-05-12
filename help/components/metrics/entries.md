---
title: Entries
description: An instance of the first value in a visit.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
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
# Entries

*This help page describes how entries work as a metric. For information on how entries work as a dimension, see [Entry dimensions](../dimensions/entry-dimensions.md).*

The 'Entries' [metric](overview.md) shows the number of times a given dimension item is captured as the first value in a visit. This metric is helpful when you want to understand more about the first impressions visitors have on your site. Seeing the first values of a dimension can help you understand and optimize the experience a new visitor gets.

## How this metric is calculated

For a given dimension, record the first dimension item seen in a visit as an entry. Only one entry exists per dimension per visit. It is not necessarily the first hit of the visit if the dimension is not initially set. It is a visit-based metric; once it ties to a dimension item, it persists for the rest of the visit.

>[!TIP]
>
>If you view this metric against a dimension not always set in every visit, you can hide the 'Unspecified' dimension item in Analysis Workspace. Click the filter icon, then uncheck [!UICONTROL Include unspecified (None)].
