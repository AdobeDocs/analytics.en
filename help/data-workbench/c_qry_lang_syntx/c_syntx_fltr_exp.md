---
description: A filter is an expression that defines a subset of the data in a dataset.
seo-description: A filter is an expression that defines a subset of the data in a dataset.
seo-title: Syntax for filter expressions
solution: Analytics
title: Syntax for filter expressions
topic: Data workbench
uuid: ed95f128-7da5-4a19-b40f-cadd27165ab1
index: y
internal: n
snippet: y
---

# Syntax for filter expressions

A filter is an expression that defines a subset of the data in a dataset.

A filter either admits or rejects each element of each dimension according to the relationships between dimensions.

Filters can be edited using the [!UICONTROL Filter Editor]. See [Filter Editors](../c_analysis_vis/c_filter_editors/c_filter_editors.md#concept_2F343ECBED8240F18B0C1F1ECCEF11E3).

In the following table, each syntax description includes an example of a metric expression using that filter. For example, Sessions[True] is a metric defined using the “True” filter. The Sessions[True] metric is the same as the Sessions metric because the True filter admits every element of the Session dimension.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <desc> 
  <b>Syntax for filter expressions</b> 
 </desc> 
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Constant filter. Admits every element of every dimension </p> <p>Example: Sessions[ True ] is the same as Sessions. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Constant filter. Rejects every element of every dimension. </p> <p>Example: Sessions[ False ] is always zero. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>not Filter </p> </td> 
   <td colname="col2"> <p>Admits elements that Filter rejects. </p> <p>Example: Sessions[ not Page=”A” ] is the number of Sessions that did not visit page A. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>FilterA and FilterB </p> </td> 
   <td colname="col2"> <p>Admits elements that FilterA and FilterB admit. </p> <p>Example: Sessions[ Page=”A” and Page=”B” ] is the number of Sessions that visited both page A and page B. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>FilterA or FilterB </p> </td> 
   <td colname="col2"> <p>Admits elements that FilterA or FilterB admit. </p> <p>Example: Sessions[ Page=”A” or Page=”B” ] is the number of Sessions that visited page A, page B, or both. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Filter by Dim </p> </td> 
   <td colname="col2"> <p>Admits the set of elements of the dimension Dim that are admitted by Filter. </p> <p>Example: Sessions[ Page=”/home” by Visitor ] is the number of Sessions belonging to a Visitor that saw the Page “/home”. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Identifier </p> </td> 
   <td colname="col2"> <p>Reference filters defined otherwise in the profile. </p> <p>Example: Sessions[ Broken_Session_Filter ] is the number of Sessions admitted by the Broken Session Filter. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim = “Value” </p> </td> 
   <td colname="col2"> <p>Admits the given element of the dimension Dim. </p> <p>Example: Sessions[ Page=”A” ] is the number of Sessions that visited Page A. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim &lt;&gt; “Value” </p> <p>Dim != “Value” </p> </td> 
   <td colname="col2"> <p>Admits every other element of the dimension Dim. </p> <p>Example: Sessions[ Page&lt;&gt;”A” ] is the number of Sessions that visited any page other than A. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Admits the element of the dimension Dim with the given ordinal value. </p> <p>Example: Sessions[ Month=#0 ] is the number of Sessions in the first month of the dataset. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim != #Ordinal </p> </td> 
   <td colname="col2"> <p>Admits every other element of the dimension Dim. </p> <p>Example: Sessions[ Session_Value &lt;&gt; #0 ] is the number of Sessions having a nonzero Session Value. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim matches “Expr” </p> </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim matching the given regular expression. Dim must not be a denormal or countable dimension. </p> <p>Example: Sessions[ URI matches “.*/product/.*” ] is the number of Sessions that visited any page in a product directory. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim notmatches “Expr” </p> </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim not matching the given regular expression. Dim must not be a denormal or countable dimension. </p> <p>Example: Sessions[ URI notmatches “.*\.jsp” ] is the number of Sessions that visited any page which was not a JSP page. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim &lt; “Value” </p> </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim with ordinal values less than the ordinal value of the element “Value.” If “Value” is not an element of dimension, then it is assumed to be larger than any current element of the dimension. </p> <p>Example: Sessions[ Month &lt; “Jul ‘04” ] is the number of Sessions that took place before July 2004. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim &gt; “Value” </p> </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim with ordinal values greater than the ordinal value of the element “Value.” If “Value” is not an element of dimension, then it is assumed to be larger than any current element of the dimension. </p> <p>Example: Sessions[ Month &gt; “Jul ‘04” ] is the number of Sessions that took place after July 2004. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim &lt;= “Value” </p> </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim with ordinal values less than or equal to the ordinal value of the element “Value.” If “Value” is not an element of dimension, then it is assumed to be larger than any current element of the dimension. </p> <p>Example: Sessions[ Session_Number &lt;= “2” ] is the number of Sessions that were the first or second session for a visitor. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Dim &gt;= “Value” </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim with ordinal values greater than or equal to the ordinal value of the element “Value.” If “Value” is not an element of dimension, then it is assumed to be larger than any current element of the dimension. </p> <p>Example: Sessions[ Session_Number &gt;= “5” ] is the number of sessions that were the fifth or greater session for a visitor. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>any Dim </p> </td> 
   <td colname="col2"> <p>Admits all elements of the dimension Dim. </p> <p>Example: Sessions[ any Page_View ] is the number of sessions with at least one page view. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>Admits elements that any Dim rejects. </p> <p>Example: Sessions[ no Page_View ] is the number of sessions without a page view. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>(FILTER) </p> </td> 
   <td colname="col2"> <p>The same as FILTER; used to group a part of a filter expression. </p> </td> 
  </tr> 
 </tbody> 
</table>

