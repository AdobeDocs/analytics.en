---
description: The Segment Builder allows you to compare and constrain values using selected operators.
seo-description: The Segment Builder allows you to compare and constrain values using selected operators.
seo-title: Comparison Operators for Segments
solution: Analytics
title: Comparison Operators for Segments
topic: Segments
uuid: d941e690-7d1f-425e-b295-0889943f6002
index: y
internal: n
snippet: y
translate: y
---

# Comparison Operators for Segments


>[!NOTE]
>
>Operators marked ** [!UICONTROL  (dw only)] ** indicate that they work with Data Warehouse segments only. 



The only supported wildcard character is the asterisk: *. If you need to search for *, you can escape it with a backslash. 

Example: Suppose you have a page name called "My cool product". 

The segment rule "Page name matches My*product" will match the above page name. However, the rule "Page name matches My\\*product" matches only the page name "My*Product". 



<table id="table_0D3C5790E8604F08B499AC88D739D7E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operator </th> 
   <th colname="col2" class="entry"> The selected dimension, segment, or metric event... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" align="left"> <b>equals</b> </td> 
   <td colname="col2" align="left"> Returns items that match exactly for a numeric or string value. <p>Note:  If using wildcard characters, use the "matches" operator. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not equal</b> </td> 
   <td colname="col2" align="left">Returns all items that do not contain the exact match of the value entered. <p> <p>Note:  If using wildcard characters, use the "does not match" operator. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>matches</b> </td> 
   <td colname="col2" align="left">Returns items that match exactly based on a given numeric or string value. <p>Note:  Use this operator when using wildcard (globbing) features. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not match</b> </td> 
   <td colname="col2" align="left">Returns all items that do not contain the exact match of the value entered. <p>Note:  Use this operator when using wildcard (globbing) features. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>is less than</b> <p>(dw only) </p> </td> 
   <td colname="col2" align="left"> Returns items whose numeric count is less than the value entered. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>is less than or equal to</b> <p>(dw only) </p> </td> 
   <td colname="col2" align="left"> Returns items whose numeric count is less than or equal to the value entered. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>is greater than</b> <p>(dw only) </p> </td> 
   <td colname="col2" align="left"> Returns items whose numeric count is greater than the value entered. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>is greater than or equal to</b> <p>(dw only) </p> </td> 
   <td colname="col2" align="left"> Returns items whose numeric count is greater than or equal to the value entered. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>contains</b> </td> 
   <td colname="col2" align="left"> Returns items that compare to the substrings of the values entered. For example, if the rule for "Page" contains "Search", then it will match any page that has the substring "Search" in it, including "Search Results", "Search", and "Searching". </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not contain</b> </td> 
   <td colname="col2" align="left"> Returns the inverse of the "contains" rule. Specifically, all items that match the entered value will be excluded from the entered values. For example, if the rule for "Page" does not contain "Search", then it will not match any page that has the substring "Search" in it, including "Search Results", "Search", and "Searching". These values will be excluded from the results. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>contains all of</b> </td> 
   <td colname="col2" align="left"> Returns items compared to the substrings, including multiple values joined together. For example, entering "Search Results" with this operator would match "Search Results" and "Results of Search", but not "Search" or "Results" independently. It would match Search AND Results found together. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not contain all of</b> </td> 
   <td colname="col2" align="left"> Identifies items compared to substrings—including multiple values joined together—and then only return items without these values. For example, entering "Search Results" with this operator would identify "Search Results" and "Results of Search" (but not "Search" or "Results" independently) and then exclude these items. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>contains any of</b> </td> 
   <td colname="col2" align="left"> Returns items compared to the substrings, including multiple values joined or independently identified. For example, entering "Search Results" with this operator would match "Search Results", "Results of Search", "Search", and "Results". It would match either "Search" OR "Results" found together or independently. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not contain any of</b> </td> 
   <td colname="col2" align="left"> Identifies items based on substrings and then returns values that do not contain these substrings. It can have multiple joined values or values independently identified. For example, entering "Search Results" would match "Search Results", "Results of Search", "Search", and "Results" where either "Search" or "Results" are found together or independently. It would then exclude items that contain these substrings. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>starts with</b> </td> 
   <td colname="col2" align="left"> Returns items that start with the character or strings of the value entered. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not start with</b> </td> 
   <td colname="col2" align="left"> Returns all items that do not start with the characters or strings of the values entered. This is the inverse of the "starts with" operator. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>ends with</b> </td> 
   <td colname="col2" align="left"> Returns items that end with the character or strings of the value entered. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>does not end with</b> </td> 
   <td colname="col2" align="left"> Returns all items that do not end with the characters or strings of the value entered. This is the inverse of the "ends with" operator. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>is null</b> </td> 
   <td colname="col2" align="left"> Returns items that contain an empty string identified as a null value. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"> <b>is not null</b> </td> 
   <td colname="col2" align="left"> Returns items that do not contain a null value. </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"><b>exists</b> </td> 
   <td colname="col2" align="left">Returns the number of items that exist. <p>For example, if you evaluate the Pages Not Found dimension using the "exist" operator, the number of error pages that exist is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="left"><b>does not exist</b> </td> 
   <td colname="col2" align="left">Returns all items that do not exist. <p>For example, if you evaluate the Pages Not Found dimension using the " does not exist" operator, the number of pages where this error page did not exist is returned. </p> </td> 
  </tr> 
 </tbody> 
</table>

