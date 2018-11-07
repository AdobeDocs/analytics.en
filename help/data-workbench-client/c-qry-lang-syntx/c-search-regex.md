---
description: Data workbench utilizes regular expressions (regex) for search and sort operations.
seo-description: Data workbench utilizes regular expressions (regex) for search and sort operations.
seo-title: Regular expressions
solution: Analytics
title: Regular expressions
topic: Data workbench
uuid: dac731d5-717a-4ba6-a2c4-bf243ea768eb
index: y
internal: n
snippet: y
---

# Regular expressions

Data workbench utilizes regular expressions (regex) for search and sort operations.

Within the **[!UICONTROL Search]** field you can perform a search following the "re:" statement using common expressions, for example:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" align="center" class="entry"> metacharacter </th> 
   <th colname="col2" align="center" class="entry"> description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" align="center"> <p>. (dot) </p> </td> 
   <td colname="col2"> <p>Matches a single character, for example: <span class="filepath"> re:x.z </span> matches "xyz" or "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="center"> <p>* (star) </p> </td> 
   <td colname="col2"> <p>Matches one or more characters, for example: <span class="filepath"> re:Z* </span> matches "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" align="center"> <p>? (wildcard) </p> </td> 
   <td colname="col2"> <p>Matches 0 or 1 of previous expression to force minimal matching, for example: <span class="filepath"> xy?z </span> matches "xy" and "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

Additional common regular expressions can also be used to create more complex search strings. Regular expressions are used across all Data Workbench search fields including the query entity panels.

See in-depth information at [regular expressions](https://marketing.adobe.com/resources/help/en_US/insight/dataset/index.html#Regular_Expressions). 
