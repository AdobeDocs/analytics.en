---
description: Dimension expressions are never used alone, but can be used anywhere a dimension is called for in a metric or filter expression.
seo-description: Dimension expressions are never used alone, but can be used anywhere a dimension is called for in a metric or filter expression.
seo-title: Syntax for dimension expressions
solution: Analytics
title: Syntax for dimension expressions
topic: Data workbench
uuid: eaacd773-a2b3-4d73-88db-e4a4eb0db25e
index: y
internal: n
snippet: y
---

# Syntax for dimension expressions

Dimension expressions are never used alone, but can be used anywhere a dimension is called for in a metric or filter expression.

1. Underlined words should be entered in the expression text literally. 
1. The form {TEXT}? represents optional text. 
1. The form {TEXT}&#42; represents text that may occur zero or more times. 
1. The form {A | B | C |...} represents text that consists of exactly one of the given options, such as A or B or C.... 
1. The form [A,B) represents a range of numbers, from A up to but not including B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <desc> 
  <b>Syntax for Dimension Expressions</b> 
 </desc> 
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Identifier </p> </td> 
   <td colname="col2"> <p>An identifier references a named dimension. For the rules governing legal identifiers, see <a href="../c_qry_lang_syntx/c_syntx_id.md#concept_735FA36FC49643269B3646AAAA8F2FA8" format="dita" scope="local"> Syntax for Identifiers </a>. </p> <p>Example: Sessions[ Session_Number = “1” ] is the number of Sessions that had a Session Number of “1.” Session Number is a named dimension referenced by identifier. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>(Dimension) </p> </td> 
   <td colname="col2"> <p>The result of (Dimension) is the same as the result of Dimension. Parentheses specify the order of operations in an expression. </p> <p>Example: Sessions[ (Page) = “/home” ] is the number of Sessions visiting the Page “/home”. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dim by Level </p> </td> 
   <td colname="col2"> <p>Defines a dimension having the same elements as the dimension Dim, but relating to other dimensions through the dimension level. </p> <p>Specifically, an element of the new dimension relates to the same elements of level as the same element of Dim, and relates to those elements of any other dimension that relate to any of those elements of level. </p> <p>Example: Sessions[ (Page by Visitor)=”/home” ] is the number of Sessions of Visitors who visited the Page “/home”. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Defines a dimension having the same elements as the dimension Dim. The eth element of the dimension level relates to the same element of the new dimension as the element of Dim related to by the e+Nth element of Level, provided that the eth and e+Nth elements of level relate to the same element of the dimension group. </p> <p>Example: Page_Views[ shift(Page, Page_View, Session, 1)=”/home” ] is the number of Page Views for which the next Page viewed in the same Session is “/home”. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Similar to shift(Dim,Level,Group,N), except that if there are empty values in the dimension, they are skipped. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Defines a dimension that classifies elements of Level based on a list of filters. The elements of the new dimension are the strings given as arguments. Each element of Level relates to the 1st element of the segment dimension whose filter admits the element of Level. This is similar to the segment visualization. </p> <p>Example: segment(Visitor, "One-Time Visitors" -&gt; Visitor_Sessions = 1, "Very Loyal Visitors" -&gt; Visitor_Sessions &gt; 10, "Everyone Else" -&gt; True) creates a dimension that classifies Visitors into three groups -- One-Time Visitors are those with only one Session, Very Loyal Visitors are those with more than ten Sessions, and all other Visitors have a value of "Everyone Else." </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Defines a dimension whose elements are ranges of numbers (of fixed size, e.g, [0-9], [10-19],...). Elements of Level relate to the element of the bucket dim whose range contains the value of Metric for that element of level. Format is the printf format string used to format the elements of Metric. </p> <p>Example: If Page_Duration_Minutes is a Page View-level dimension representing the number of minutes spent on each page, then bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) is a Session-level dimension representing the number of minutes spent in each Session; its elements are 5 minute intervals {[0-5), [5-10),...,[495-500)}. </p> <p>Start is the starting value of the first interval (default: 0) and Size is the size of the interval (default: 1). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Defines a dimension whose elements are the given ElementName strings and are associated with the corresponding sets of Prefix strings. Elements of Level relate to the element of the prefix dim, which is associated with the longest prefix matched by the name of the given element of level. Prefixes ending with the special character '$' must be matched exactly. </p> <p>For example, prefix(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Everything Else" -&gt; ("/"))) creates a dimension that classifies URIs into the four listed categories. The effect on various pages is as follows: </p> <p>/products/warranty.html Goes into Warranty, since it matches the /products/warranty.html$ prefix exactly. </p> <p>/products/cars/specialcar.html Goes into Products, since it matches the /products/ prefix and no longer prefix </p> <p>/products/service/something.html Goes into Services, since it matches the /products/service/ prefix which is longer than the /products/ prefix. </p> <p>/companyinfo/aboutus.html Goes into the "Everything Else" category, since the only prefix it matches is "/". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>See <a href="../c_intf_anlys_ftrs/c_config_ltcy_tbls/t_create_ltncy_dims.md#task_6D46EA8C89A047318D9C71BF105EF64A" format="dita" scope="local"> Creating Latency Dimensions </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Defines a dimension whose elements are all the combinations ("the cartesian product") of the elements of the dimensions given. The name of each element is made out of the concatenation of the corresponding elements in the input dimensions, separated by the given Separator string. </p> <p>For example, if the dimension D1 has elements {"a", "b"} and the dimension D2 has the elements {"x", "y"}, then cartesian product("-", D1, D2) has the elements {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Note that internally, each of the input dimensions is treated as if the number of its elements is the next higher power of two. This results in the cartesian product having some dummy elements. When using the Data Workbench API, depending on the output format, these elements may be ommited, or they may be shown as "#nnn", where nnn is the ordinal of the element (and should be ignored by the client). </p> <p>For example, in the example above, if D2 had the three elements {"x", "y", "z"}, it would be treated as if it had four elements, and the cartesian product would have the elements {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>If no dimensions are given, the result is a dimension with one element, "#0", which is equivalent to the None dimension. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>nearest_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Refers to an already existing dimension: the nearest countable ancestor of Dim in the schema. For example, nearest countable(URI) is identical to Page_View. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Defines a normalized dimension from the denormal dimension Dim, with up to Count elements. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Defines a dimension which has a subset of the elements of the dimension Dim, whose elements represent slices of time -- for example, days, weeks, or years. </p> <p>The subset is a range around a specified time, the value of the constant metric TimeMetric, which is interpreted as a time value in seconds since midnight UTC of January 1, 1970. The range has Count elements, the last of which is Offset elements after the given Dim's element whose name is the result of formatting the value of the metric with the given FormatString string. FormatString uses the same % escapes as the standard C library function strftime. </p> <p>If trimToData is true then any elements at the beginning of the resulting dimension, which would be before the beginning of Dim, are removed. When it is false, there will always be the exact number of elements specified by Count. Note that there may always be elements at the end of the resulting dimension that are not actually in Dim. </p> <p>The optional WeekStart, if specified, must be one of { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. It modifies TimeMetric by moving it backwards to the most recent occurence of that weekday. </p> <p>Example: If Week has the elements { "10/03/10", "10/10/10", ..., "12/12/10" } and the built-in As Of metric has the value 1292348109 (representing a time in the middle of December 14th, 2010), then last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") defines the dimension with elements { "12/12/10", "12/19/10", "12/23/10", "12/30/10" }. </p> <p>Example 2: If the Week dimension only has elements {"12/19/10", "12/26/10", ..., "01/30/11"}, and the As Of metric is as above, then last n(Week, As_Of, "%m/%d/%y", 4, 0, true, "Sun") gives a dimension with elements {"12/19/10", "12/23/10", "12/30/10"}. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Defines a dimension which has a subset of the elements of Dim, whose elements represent days. The subset is a range around a specified time, the value of the constant metric TimeMetric, which is interpreted as a time value in seconds since midnight UTC of January 1, 1970. The range will include the elements corresponding to each day in the nMonths months preceding the specified time. If includeThisMonth is true, the range also includes each day of the month that contains the specified time. </p> <p>FormatString specifies the formatting of the elements of Dim, using "%" escapes as in the standard C library function strftime. </p> <p>If trimToData is true then any elements at the beginning of the resulting dimension, which would be before the beginning of Dim, are removed. When it is false, there will always be the exact number of elements specified by Count. Note that there may always be elements at the end of the resulting dimension that are not actually in Dim. </p> <p>Example: If Day has the elements { "01/01/10", "01/02/10", ..., "12/31/10" } and the built-in As Of metric has the value 1292348109 (representing a time in the middle of December 14th, 2010), then days of previous months(Day, As_Of, "%m/%d/%y", 2, false, false) will have elements { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Similar to days of previous months, except the elements correspond only to days of the same month as the time specified by the TimeMetric. If allMonth is true, there will be an element for each day of the appropriate month; otherwise, only days from the first of the appropriate month through the day containing the specified time will be part of the dimension. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Similar to days of previous months, except that the elements correspond to the days of months after, rather than before, the month containing the time specified by the TimeMetric. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Defines a dimension which has a subset of the elements of Dim, whose elements represent hours. The subset is a range around a specified time, the value of the constant metric TimeMetric, which is interpreted as a time value in seconds since midnight UTC of January 1, 1970. The range includes the elements corresponding to each hour of the day nDaysForward after the day containing the time specified by the TimeMetric. </p> <p>FormatString specifies the formatting of the elements of Dim, using "%" escapes as in the standard C library function strftime. The format string should always output a string representing midnight at the beginning of the day of the time passed in. </p> <p>If trimToData is true then any elements at the beginning of the resulting dimension, which would be before the beginning of Dim, are removed. When it is false, there will always be the exact number of elements specified by Count. Note that there may always be elements at the end of the resulting dimension that are not actually in Dim. </p> <p>Example: If Hour has the elements { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }, and the built-in As Of metric has the value 1292348109 (representing a time in the middle of December 14th, 2010), then hours of day(Hour, As_Of, "%x 00:00", 0, false) has elements { "12/12/10 00:00", "12/12/10 01:00", ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>

