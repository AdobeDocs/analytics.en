---
title: Single page visits (metrics)
description: The number of times that the 'Page' dimension item did not change in a visit.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
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
