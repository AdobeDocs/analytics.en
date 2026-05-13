---
description: Explains the three Product Compatibility options.
title: Metric compatibility
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
TQID: https://experienceleague.adobe.com/nbLLWHYtTLKmGnUxyU2Gp9spVCtE-AZgH2MiXE4nOVY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
---
# Metric compatibility {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Product Compatibility"
>abstract="A small number of available metric criteria are not compatible with all Adobe Analytics tools. Tools that are compatible with the metric are indicated in this list. To make a metric compatible with all Adobe Analytics tools, try editing your criteria."

This article explains the three product compatibility options.

When you create calculated metrics in the calculated metric builder, your metric will show as compatible with one or more tools within Adobe Analytics.


| Compatible with | Description |
| --- | --- |
| **[!UICONTROL Current Data]** | The [!UICONTROL Include Current Data] option in Adobe Analytics lets you view the latest Analytics data, often before data is fully processed and finalized. [!UICONTROL Current Data] displays most metrics within minutes, providing actionable data for quick decision making. [!UICONTROL Current Data] supports calculated metrics only (those that include multiplication, division, addition, and subtraction.) [!UICONTROL Current Data] does not support advanced calculated metrics (that contain segments or functions). |
| **[!UICONTROL Fully Processed Data]** | Data that is fully processed and includes segments and classifications. If you would rather view all metrics after the data is fully processed, you can disable [!UICONTROL Current Data] by removing users from the Current Data Users group. |
| **[!UICONTROL Marketing Channel Reports]** | Metrics with first-touch allocation are compatible only with Marketing Channel reports. |
