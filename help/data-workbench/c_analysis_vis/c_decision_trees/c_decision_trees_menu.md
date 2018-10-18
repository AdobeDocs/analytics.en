---
description: The Decision Tree menu includes features to set the positive use case, filters, leaf distribution options, confusion matrix, and other advanced options.
seo-description: The Decision Tree menu includes features to set the positive use case, filters, leaf distribution options, confusion matrix, and other advanced options.
seo-title: Decision tree options
solution: Analytics
title: Decision tree options
topic: Data workbench
uuid: 73da4e01-6c06-42ae-b290-0746d664325f
index: y
internal: n
snippet: y
---

# Decision tree options

The Decision Tree menu includes features to set the positive use case, filters, leaf distribution options, confusion matrix, and other advanced options.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Toolbar buttons </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" valign="top"> <p>Go </p> </td> 
   <td colname="col2" valign="top"> <p>Click to run the decision tree algorithm and display the visualization. This is grayed-out until there are inputs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Reset </p> </td> 
   <td colname="col2" valign="top"> <p> <b>Reset Models</b>—Clears out the model but maintains the settings and inputs. Makes the <b>Go</b> button selectable. </p> <p> <b>Reset All</b>—Resets all settings as in previous design. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Save </p> </td> 
   <td colname="col2" valign="top"> <b>Save the Decision Tree</b>. You can save the Decision Tree in different formats: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Predictive Markup Language (<b>PMML</b>), an XML-based file format used by applications to describe and exchange decision tree models. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Text</b> displaying simple columns and rows of true or false, percentages, number of members, and input values. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> with branches corresponding to predicted outcome elements. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options </p> </td> 
   <td colname="col2"> <p>See table below for Options menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric </p> </td> 
   <td colname="col2"> <p>Lists Metrics that can be added to the model </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Element </p> </td> 
   <td colname="col2"> <p>Drag and drop Dimensions and Elements to this box (or directly to the visualization). </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Options menu </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" valign="top"> <p>Set Positive Case </p> </td> 
   <td colname="col2" valign="top"> <p>Defines the current workspace selection as the model's Positive Case. Clears the case if no selection exists. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Set Population Filter </p> </td> 
   <td colname="col2" valign="top"> <p>Defines the current workspace selection as the model's Population Filter and will be drawn from visitors who satisfy this condition. The default is "Everyone." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Show Complex Filter Description </p> </td> 
   <td colname="col2" valign="top"> <p>Displays descriptions of the defined filters. Click to view the filtering scripts for the Positive Case and Population Filter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Hide Nodes </p> </td> 
   <td colname="col2" valign="top"> <p>Hides nodes with only a small percentage of the population. This menu command displays only when the decision tree is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Confusion Matrix </p> </td> 
   <td colname="col2" valign="top"> <p>Click <span class="uicontrol"> Options</span> &gt; <span class="uicontrol"> Confusion Matrix</span> to view the Accuracy, Recall, Precision and F-Score values. The closer to 100 percent, the better the score. </p> <p>The Confusion Matrix gives four counts of accuracy of the model using a combination of values: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Actual Positive (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Predicted Positive (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Actual Negative (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Predicted Negative (PN) </li> 
     </ul> </p> <p> <p>Note:  These numbers are obtained by applying the resulted scoring model of the 20 percent testing data withheld and already known as the true answer. If the score is greater than 50 percent, it is predicted as a positive case (that matches the defined filter). Then, Accuracy = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN), and Precision = TP / (TP + FP). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Display Legend </p> </td> 
   <td colname="col2" valign="top"> <p>Allows you to toggle a legend key on and off in the Decision Tree. </p> <p style="text-align: center;"><img href="assets/decison_tree_legend.png" align="left" placement="break" id="image_D5B9415A48C04619955BD96970F720A1" /> </p> <p>This menu command displays only when the decision tree is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Advanced </p> </td> 
   <td colname="col2" valign="top"> <p>Click to open Advanced menu for in-depth use of Decision Tree. See table below for menu options. </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Advanced menu </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" valign="top"> <p>Training Set Size </p> </td> 
   <td colname="col2" valign="top"> <p>Controls the size of the training set used for the model building. Larger sets take longer to train, smaller sets take less time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Input Normalization </p> </td> 
   <td colname="col2" valign="top"> <p> Allows the user to specify whether to use the Min-Max or the Z Score technique to normalize inputs into the model. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>SMOTE Over-Sampling Factor </p> </td> 
   <td colname="col2" valign="top"> <p>When the Positive Case does not occur very often (less than 10 percent) in the training sample, SMOTE is used to provide additional samples. This option allows the user to indicate how many more samples to create using SMOTE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top"> <p>Leaf Class Distribution Threshold </p> </td> 
   <td colname="col2" valign="top"> <p>Allows you to set the threshold assumed for a leaf during the tree building process. By default, all members of a node must be identical for it to be a leaf (prior to pruning stage). </p> </td> 
  </tr> 
 </tbody> 
</table>

