---
description: To help with the statistics, Data Workbench provides three statistical measures in the guided analysis visualization.
seo-description: To help with the statistics, Data Workbench provides three statistical measures in the guided analysis visualization.
seo-title: Statistical measures
solution: Analytics
title: Statistical measures
topic: Data workbench
uuid: 70aaf635-a019-4eff-99dc-39bd832a921e
index: y
internal: n
snippet: y
---

# Statistical measures

To help with the statistics, Data Workbench provides three statistical measures in the guided analysis visualization.

>[!NOTE]
>
>Although mathematics can help you make judgments about the correlations in your data, the context surrounding the data also must be taken into account.

* **Chi Sq p** is a test of statistical significance that controls the appearance of the check mark in the visualization. Mathematically, it is a probability that we can reject the null hypothesis, which states that the differences observed between the two groups can be explained by random variation. Practically, if the Chi Sq p value is less than almost 100% we can ignore the correlation regardless of its measured strength (as described in the following U statistic and V statistic sections). 
* **U statistic** is a measure of strength of statistical correlation. Mathematically, it comes from a branch of mathematics called information theory and is closely related to the concept of mutual information between the distributions of the two groups. Alternatively, it can be thought of as the compressibility of one group given an optimal coding scheme for the other group. Practically, this measure performs very well in the common case of a dimension with many elements containing few visitors. The measure varies from 0 (weak) to 1 (strong). 
* **V statistic** is also a measure of strength of statistical correlation. Mathematically, it is related to the familiar Cramer’s V statistic, differing only by a normalization step intended to improve symmetry of the measure with respect to selection inversion. Practically, this measure works reasonably well with many types of dimensions and is related to a commonly-used statistical measure. The measure varies from 0 (weak) to 1 (strong).

>[!NOTE]
>
>The U and V statistics were selected to complement one another—each tuned to detect types of correlations to which the other one might not respond as strongly.

Using this visualization as your guide, you can add other visualizations to your workspace to provide more insight into your data based on the selection.

The following [!UICONTROL Site] example contains a bar graph that shows sessions for days in January, February, March, and April. Note that one day in January is selected.

![](assets/vis_GuidedAnalysis_withVis.png)

The guided analysis visualization in the lower-left corner of the workspace indicates that the Session Number dimension provides useful information about the selected day.

By examining the Session Number bar graph in the lower-right corner of the workspace, you can see that the data for Session Number 2 is much lower than the benchmark. Thus, we can conclude that, as a percentage, fewer second sessions occurred on the selected day than is usual. To view a bar graph for any of the dimensions listed in the guided analysis visualization, simply select the dimension by clicking the dimension with your mouse. 
