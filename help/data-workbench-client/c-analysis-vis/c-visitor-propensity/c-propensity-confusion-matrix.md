---
description: The statistical calculations for Propensity Scoring for Data Workbench are defined.
seo-description: The statistical calculations for Propensity Scoring for Data Workbench are defined.
seo-title: Calculate propensity scoring
solution: Analytics
title: Calculate propensity scoring
topic: Data workbench
uuid: e7f72613-cfec-4641-9ab5-fcc70c21447d
index: y
internal: n
snippet: y
---

# Calculate propensity scoring

The statistical calculations for Propensity Scoring for Data Workbench are defined.

 Conceptually, the score calculated for each visitor is an estimated probability that the specified event (defined by the target filter) might happen, resulting in a score value range from 0 to 100 percent. The scoring procedure uses existing samples as training data to find the relationship between the event probability and the selected independent variables of interest.

Mathematically, such relationships are reflected in each quantitative value associated for each independent variable. Those values are called model coefficients. ScoreDim currently uses the Iteratively Reweighted Least Squares (IRLS) algorithm to estimate the model coefficients. IRLS goes through the samples multiple times until the difference of coefficients between current pass and the previous pass is less than 1.0e-6, at which point it is called "converged." However, depending on the data, IRLS may not be able to reach convergence.

In such case, the model training iteration will terminate when

* the coefficient difference gets larger instead of smaller, 
* 1,000 passes have been reached, or 
* a mathematical error prevents continuing iteration.

If IRLS doesn't converge, a backup algorithm called Stochastic Gradient Decent (SGD) will be used. SGD will also go through the training samples multiple times. But unlike IRLS, the SGD model coefficients are controlled so that the difference between iteration will always decrease in an exponential manner. Similarly, SGD will terminate when the coefficient difference falls below 1.0e-6 or 100,000 passes have been reached. The failure of IRLS and engagement of SGD will be recorded in trace log.

For both algorithms, not all samples go into model training. 80 percent are currently used to train the model. After the model is trained, the remaining 20 percent samples will be used to assess the model strength in terms of Accuracy, Recall, and Precision that is calculated from the confusion matrix. The closer to 100%, the better the scoring model.

>[!IMPORTANT]
>
>In some customer datasets, the default metric produced from a predictive analytics feature such as Propensity Scoring might need additional configuration when the baseline definition of the Visitor's metric has been changed. For example, if you have a Visitor definition based on this filter— [!DNL Sum(New_Accounts_Scoring, Visitor) * .01]—then you may have a problem where the denominator has fewer visitors identified than the numerator, rendering a value over 100 percent.

