---
title: Single page visits (metrics)
description: The number of times that the 'Page' dimension item did not change in a visit.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
TQID: https://experienceleague.adobe.com/iDXuwf-Ls1N7VzmtZiMRISLbSEtHOtDTeoddfDEiAwA
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
# Single page visits

*This help page describes how 'Single page visits' works as a metric. See the [Single page visits](../dimensions/single-page-visits.md) dimension for more information.*

The **[!UICONTROL Single page visits]** [metric](overview.md) shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single value for the entire visit. This metric is helpful in the context of dimensions where you want to see short visits, but not have as stringent of a rule as [[!UICONTROL Bounces]](bounces.md) does.

## How this metric is calculated

The definition of this metric depends on the project setting of [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **[!UICONTROL Count repeat instances] enabled**: Counts the number of visits where the [!UICONTROL Page] dimension contained a single value for the visit. If a visitor reloads the page, it disqualifies as a single page visit.
* **[!UICONTROL Count repeat instances] disabled**: Counts the number of visits where the [!UICONTROL Page] dimension contained a single unique value for the entire visit.

Regardless of the '[!UICONTROL Count repeat instances]' project setting, this metric adheres to the following rules:

* A visit still qualifies as a single page visit if a visitor fires link tracking calls (the [!UICONTROL Page] dimension is stripped from all link tracking calls).
* As soon as the [!UICONTROL Page] dimension changes to a second unique value, the visit no longer qualifies as a single page visit.

See [Single access](single-access.md) for a comparison between metrics.
