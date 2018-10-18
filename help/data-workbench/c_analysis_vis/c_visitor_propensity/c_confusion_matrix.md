---
seo-title: Confusion matrix
solution: Analytics
title: Confusion matrix
topic: Data workbench
uuid: 2211c83e-d34a-4eb1-9aea-36ef012f5aa2
index: y
internal: n
snippet: y
---

# Confusion matrix

The Confusion Matrix gives four counts by the combination of Actual Positive (AP), Actual Negative (AN), Predicted Positive (PP), and Predicted Negative (PN). These numbers are obtained by applying the resulted scoring model to the 20% withheld testing data of which we know the true answer. If the score is greater than 50%, it is predicted as a positive case (matching the defined event).

![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> Accuracy</b> </p> </td> 
   <td colname="col2"> <p>Indicates how accurate the model is by identifying the correct predictions over all predictions. </p> <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Recall</b> </p> </td> 
   <td colname="col2"> <p>Identifies the ability to re-identify the scoring model. </p> <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Precision</b> </p> </td> 
   <td colname="col2"> <p>Identifies the level of discrepancy. </p> <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

