---
description: A guided analysis visualization provides cues for further analysis based on the selections that you make in a workspace.
seo-description: A guided analysis visualization provides cues for further analysis based on the selections that you make in a workspace.
seo-title: Guided analysis
solution: Analytics
title: Guided analysis
topic: Data workbench
uuid: e483113f-545e-44ec-9dc3-b6ea6af24d6f
index: y
internal: n
snippet: y
---

# Guided analysis

A guided analysis visualization provides cues for further analysis based on the selections that you make in a workspace.

 This visualization helps you identify which dimensions can provide you with more information, that is, those that are most strongly correlated with your selections. The guided analysis visualization in your Adobe application displays the dimensions relevant to your dataset, as in the following [!UICONTROL Site] guided analysis visualization.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>If a dimension name displays in red, it is not defined in your dataset.

When you make a selection within a workspace, the guided analysis visualization displays check marks to the left and dots to the right of the dimensions to show which ones provides the most relevant information:

* **Check marks** identify the dimensions whose values differ from the benchmark in a statistically significant way (that is, the difference between the selection and the benchmark is not due to random chance). 
* **Dots** indicate the degree by which the selection differs from the benchmark. The first dot represents the U statistic, and the second dot represents the V statistic. See [Understanding the Statistical Measures](../../../data-workbench-client/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept_BA2C7F417F384DC0A3438FCB6E268708). The brighter and larger the dots, the greater the difference, and the more relevant the information for the dimension based on your selection (that is, brighter, larger dots represent more useful information).

