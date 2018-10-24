---
description: Metrics can be edited using the Metric Editor and saved in the Metrics directory of a profile.
seo-description: Metrics can be edited using the Metric Editor and saved in the Metrics directory of a profile.
seo-title: Syntax for metric expressions
solution: Analytics
title: Syntax for metric expressions
topic: Data workbench
uuid: 2a0787f2-3cf8-449f-af23-49ca61c3a330
index: y
internal: n
snippet: y
---

# Syntax for metric expressions

Metrics can be edited using the Metric Editor and saved in the Metrics directory of a profile.

For more information, see [Creating and Editing Derived Metrics](../../data-workbench-client/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept_E41723B342A849309874B26232224A40). Metric expressions also can be used in worksheets. For more information, see [Worksheets](../../data-workbench-client/c-analysis-vis/c-wksts/c-wksts.md#concept_45B50AAFC4D84709841F14AEE8022581). The following syntax is used to define metric expressions.

Notes:

1. Underlined words should be entered in the expression text literally. 
1. The form {TEXT}? represents optional text. 
1. The form {TEXT}&#42; represents text that may occur zero or more times. 
1. The form {A | B | C |...} represents text that consists of exactly one of the given options, such as A or B or C.... 
1. The form [A,B) represents a range of numbers, from A up to but not including B.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Identifier </p> </td> 
   <td colname="col2"> <p>An identifier references a named metric. For the rules governing legal identifiers, see <a href="../../data-workbench-client/c-qry-lang-syntx/c-syntx-id.md#concept_735FA36FC49643269B3646AAAA8F2FA8" format="dita" scope="local"> Syntax for Identifiers </a>. </p> <p>Example: Revenue = Total_Price </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>(Metric) </p> </td> 
   <td colname="col2"> <p>The result of (Metric) is the same as the result of Metric. Parentheses specify the order of operations in an expression. </p> <p>Example: Average = (A + B) / 2 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Sum of the results of Metric A and Metric B. </p> <p>Example: Value = Revenue + Cost_Savings </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Difference of the results of Metric A and Metric B. </p> <p>Example: Profit = Revenue - Cost </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Product of the results of Metric A and Metric B. </p> <p>Example: Dollars = Cents * 0.01 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>A / B </p> </td> 
   <td colname="col2"> <p>Ratio of the results of Metric A and Metric B. </p> <p>Example: Revenue_per_Session = Revenue / Sessions </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Result of Metric A raised to the power of the result of Metric B. </p> <p>Example: Area = Width^2 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>confidence(metric) </p> </td> 
   <td colname="col2"> <p>An estimate of the standard deviation of the metric. This is calculated using a sampling technique known as jackknifing. </p> <p>This metric is memory-intensive and should not be used in large tables. </p> <p>To use this syntax, you must have a jackknife dimension (named “jackknife”) with the appropriate properties. For more information, contact Adobe Consulting Services. </p> <p>Example: confidence(Average_Score) </p> <p> <p>Note:  The confidence metric types, including confidence(metric) and confidence(metric,jacknife), are especially useful when using Adobe’s controlled experimentation functionality. If a metric jumped from 12% to 16% during a controlled experiment, you could use a confidence callout to calculate the odds that the jump was due to random variation. This can help you to avoid drawing the wrong conclusions from limited evidence, and, conversely, provide assurance that a questionable change is actually real. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>confidence(metric, jackknife) </p> </td> 
   <td colname="col2"> <p>An estimate of the standard deviation of the metric. This is calculated using a sampling technique known as jackknifing. This syntax enables you to determine the confidence of a metric using a jackknife dimension named something other than “jackknife.” </p> <p>This metric is memory-intensive and should not be used in large tables. </p> <p>To use this syntax, you must have a jackknife dimension (named something other than “jackknife”) with the appropriate properties. For more information, contact Adobe Consulting Services. </p> <p>Example: confidence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Treats the content of the cell you are referencing as a metric expression. This syntax can be used only in a worksheet visualization. </p> <p>Example: eval(B1) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>The mathematical logarithm function: Metric X is the parameter, and Metric B is the base. </p> <p>Example: dB = 20*log(10, Amplitude) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Metric[Filter] </p> </td> 
   <td colname="col2"> <p>“Metric where Filter”: A new metric filtered by the given filter. </p> <p>Example: Jan_Sessions = Sessions[ Month=”Jan” ] </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Metric by Dimension </p> </td> 
   <td colname="col2"> <p>A metric evaluated at the “level” of dimension. The result of (M by X)[F] (the result of metric “M by X” evaluated with Filter “F”) is the result of M[F by X] (the result of Metric “M” evaluated with Filter “F by X”). </p> <p>Example: AB_Visitors = </p> <p>(Visitors by Session)[Page=”A” and Page=”B”] = </p> <p>Visitors[(Page=”A” and Page=”B”) by Session] = </p> <p>The number of Visitors who visited page A and page B in the same Session. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>number </p> </td> 
   <td colname="col2"> <p>A metric with a fixed value. </p> <p>Example: Pi = 3.1415 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>total(Metric) </p> </td> 
   <td colname="col2"> <p>Ignores any dimension over which the metric is evaluated. The metric has the same value for every element of that dimension. </p> <p>Example: Pct_of_Visitors = Visitors / total(Visitors) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignores filters applying to the metric. The metric are unaffected by selections and other filters. </p> <p>Example: Benchmark_Sessions = all( Sessions ) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>total(all(Metric)) </p> </td> 
   <td colname="col2"> <p>Ignores all filters and dimensions. It has the same value throughout a given profile regardless of what filters or dimensions are applied. </p> <p>Example: Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>A metric that gives the count of a countable dimension such as Visitor or Session. </p> <p>Example: Visitors = sum(One,Visitor) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>A metric that gives the sum of a numeric dimension over a countable dimension. The ordinal values (as opposed to the formatted values) of the numeric dimension’s elements are used, so a scale factor often needs to be applied to the result. </p> <p>Example: Value = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>The lesser results of metric A and metric B. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>The greater of the results of metric A and metric B. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>A metric which is identical to metric A, except it uses the formatting function of metric B. </p> </td> 
  </tr> 
 </tbody> 
</table>

