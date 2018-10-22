---
description: A model viewer lets you generate a logistic regression model using the Propensity Scoring feature.
seo-description: A model viewer lets you generate a logistic regression model using the Propensity Scoring feature.
seo-title: Model viewer
solution: Analytics
title: Model viewer
topic: Data workbench
uuid: 1a1d9fd6-c625-4eb3-bd87-3a43862345dc
index: y
internal: n
snippet: y
---

# Model viewer

A model viewer lets you generate a logistic regression model using the Propensity Scoring feature.

The Model Viewer displays the coefficient weights of each input variable (including the constant term) and their statistical error range. Input variables showing a high absolute coefficient and small margin of error are the most significant predictors in the model.

![](assets/propensity_model_viewer.png)

The input variables with a coefficient >= 1 are positive influences on the propensity model. The coefficients that are < 1 are negative influences on the propensity model. The range defined within the parentheses is the error, and indicates the consistency of the input variable across the successful population.

**To open a model viewer**

1. Right-click **[!UICONTROL Model Complete]** for your completed Score Model. 
1. Select **Model Viewer**.

**To open a saved score model**

1. Select **[!UICONTROL Add Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Lift Chart]** (or Gain Chart) > **[!UICONTROL Scoring]**. 
1. Select the saved Score Model to open a Lift or Gain chart.

