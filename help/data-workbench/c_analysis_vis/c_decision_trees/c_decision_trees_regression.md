---
description: Evaluate a Decision Tree using the Regression Tree option with new sampling and visualization features.
seo-description: Evaluate a Decision Tree using the Regression Tree option with new sampling and visualization features.
seo-title: Regression tree option for decision tree
title: Regression tree option for decision tree
uuid: ff47118a-33ca-4954-8fcc-f25980b6cae8
index: y
internal: n
snippet: y
---

# Regression tree option for decision tree

Evaluate a Decision Tree using the Regression Tree option with new sampling and visualization features.

Evaluate a Decision Tree using the Regression Tree option by right-clicking and selecting Options > **Regression Tree** within a Decision Tree visualization.

**Updated Decision Tree builder**: The new algorithm was introduced for building a [Decision Tree](https://marketing.adobe.com/resources/help/en_US/insight/client/?f=c_decision_trees). It handles more general data and provides a more informative visualization to improve the precision of the prediction.

**Improved data sampling module**: An updated adaptive sampling scheme helps Decision Tree and Propensity Score achieve higher precision results.

![](assets/CART-RegressionTreeOptions.jpg)

Green and red indicate true or false. The saturation of color—such as deep red versus light red—is used to indicate probability. For example, a node with deep red has a very high probability to be false, while a node with light red has a lower probability to be false. A node with deep green has a very high probability to be true.

All Decision Trees have varying branch widths to indicate the level of traffic for that branch of the tree.

In a Decision Tree visualization, right-click and select Options > **Regression Tree**. When selected, additional settings are provided:  

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regression setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Use Each Feature Only Once</b> </p> </td> 
   <td colname="col2"> <p>Selecting this option will not use a feature more than once (like the original decision tree)—so if you have five inputs, the tree will be no more than five levels and the tree structure will look similar to a Decision Tree (but a bit more complicated). This option will make the tree building fast by using each feature only once (like an original Decision Tree). Using this feature is a default setting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regression Tree Level Setting </b> </p> </td> 
   <td colname="col2"> <p>This option controls the complexity of the Regression Tree. Depending on your data, you might need to build a <i>Fine</i> tree (with a complicated structure with more nodes) to get a more meaningful tree classification. If you have much data, then a relatively <i>Coarse</i> tree (less complicated with fewer tree nodes) could work well. </p> <p> <p>Note: <i>Typical</i> is the default setting. There are some extreme cases where the <i>Typical</i> setting doesn't work as well and the <i>Coarse</i> or <i>Fine</i> setting can provide a better view of the data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fine</i>: The most complex tree with the most granular levels of reporting and most branches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Typical</i>: The average level of granularity and branches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Coarse</i>: The least complex tree with the fewest defined categories and fewest branches. </p> </td> 
  </tr> 
 </tbody> 
</table>

