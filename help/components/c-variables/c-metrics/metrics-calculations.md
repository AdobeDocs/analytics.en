---
description: Metrics are calculated using standard, participation, recent, and linear allocation methods. Each method calculates values differently based on formulas.
seo-description: Metrics are calculated using standard, participation, recent, and linear allocation methods. Each method calculates values differently based on formulas.
seo-title: Metric calculations
solution: Analytics
title: Metric calculations
topic: Metrics
uuid: 1ed9d729-a202-4c6d-b5f9-60744e0bbc76
index: y
internal: n
snippet: y
---

# Metric calculations

Metrics are calculated using standard, participation, recent, and linear allocation methods. Each method calculates values differently based on formulas.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric Calculation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Original </td> 
   <td colname="col2"> <p>Full credit is given to the first variable value associated with the success event. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recent </td> 
   <td colname="col2"> <p>Full credit is given to the last variable value associated with the success event. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linear </td> 
   <td colname="col2"> <p>When linear allocation is selected, success events are evenly divided across all variable values seen in the visit. For numeric and currency events such as <span class="term"> Revenue</span>, the monetary amount is divided. For counter events such as <span class="term"> Orders</span>, a fraction of the event is awarded to each variable value in the visit. These fractions in reporting are summed, then rounded to the nearest integer in reporting. </p> <p>For example, in a visit where four pages are visited prior to a success event, each page would receive credit for 25% of the event. If, in the same visit, <span class="varname"> campaign</span> had two values, each campaign value would receive 50% of the credit for the event. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Participation </td> 
   <td colname="col2"> <p>Assigns full credit to each variable value that contributed to a success event within a visit. This calculation can also apply across visitor sessions, if you use cross-visit participation metrics. </p> <p>See <a href="../../c-variables/c-metrics/metrics-participation.md#concept_8E6B39106A244CB49E055150B291B477" format="dita" scope="local"> Participation</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Example - Metric Calculation {#section_4CE01DA35108418D9909823A7ECC4B45}

Assume your site has an internal search that is tracked using a conversion variable (eVar). The visitor performs several internal searches before making a $100 purchase:

*`Pet`* > *`Feline`* > *`Cat`* > *`Kitten`* > $100 purchase

In reporting, credit allocation is as follows: 

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar Value </th> 
   <th colname="col2" class="entry"> First </th> 
   <th colname="col3" class="entry"> Last </th> 
   <th colname="col4" class="entry"> Linear </th> 
   <th colname="col5" class="entry"> Participation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pet </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feline </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cat </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kitten </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

