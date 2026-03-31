---
title: Single access
description: The number of times a dimension item did not change in a visit.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
---
# Single access

The **[!UICONTROL Single access]** [metric](overview.md) shows the number of visits where the applicable reporting dimension contained only a single value for an entire visit. It is the broader, dimension-specific version of [[!UICONTROL Single page visits]](single-page-visits.md). This metric is helpful in context of any dimension where you want to see the value of a dimension when it was set only once during a visit.

## How this metric is calculated

The definition of this metric depends on the project setting of [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **Count repeat instances enabled**: Counts visits where the dimension contains exactly one value in a visit. If the dimension persists, then it no longer qualifies as a single access.
* **Count repeat instances disabled**: Counts visits where the dimension contains a single unique value. You can set the dimension item to the same value multiple times or have it persist and it still counts as a single access.

Regardless of '[!UICONTROL Count repeat instances]', the visit no longer qualifies as a single access if the dimension changes to a second unique value. Link tracking calls are included in this calculation if the dimension is set in them.

## Difference between '[!UICONTROL Single access]' and '[!UICONTROL Single page visit]'

In context of the [[!UICONTROL Page]](../dimensions/page.md) dimension, '[!UICONTROL Single access]' and '[!UICONTROL Single page visits]' are always exactly identical regardless of the '[!UICONTROL Count repeat instances]' project setting. Their differences emerge when you use other dimensions.

* **[!UICONTROL Single access]**: Shows the number of visits where the given dimension item was present for a single hit. It is contextual to the dimension that you use in your project.
* **[!UICONTROL Single page visit]**: Shows the number of visits where the '[!UICONTROL Page]' dimension was present for a single hit. Even though you use another dimension in your report, it still counts visits that contain a single unique '[!UICONTROL Page]' dimension item.

If [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) is disabled, metric definitions change slightly:

* **Single access**: Shows the number of visits where the given dimension item did not change for the entire visit.
* **Single page visit**: Shows the number of visits where the '[!UICONTROL Page]' dimension did not change for the entire visit.

For example, consider the following example two-hit visits. The dimension in your report is [[!UICONTROL Site section]](../dimensions/site-section.md) and '[!UICONTROL Count repeat instances]' is disabled.

* A visitor hits two pages, but they are both in the same site section. Since site section remained the same through the visit, it counts as a single access. It does not count as a single page visit because the visit contains more than one unique [!UICONTROL Page] dimension item.
* A visitor hits two pages in different site sections, but both pages just happen to be named the same. The visit does not count as a single access because there were two unique site section values. It counts as a single page visit because there was a single unique [!UICONTROL Page] dimension item.
