---
title: Reloads
description: The number of times the page was reloaded.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Reloads

The 'Reloads' [metric](overview.md) shows the number of times a dimension item was present during a reload. A visitor refreshing their browser is the most common way to trigger a reload.

## How this metric is calculated

This metric counts the number of hits where the [Page](../dimensions/page.md) dimension contains the same value as the previous hit.

The concept of a reload applies to the Page dimension regardless of what dimension that you use in reporting. For example, if you use [eVar1](../dimensions/evar.md) as a dimension and Reloads as a metric, the table shows you the number of times that each eVar value was present during a reload (two consecutive page values). It does not show the number of times two consecutive eVar1 values were present.
