---
title: Hash collisions
description: Describes what a hash collision is and how it can manifest.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
---
# Hash collisions

Adobe treats prop and eVar values as strings, even if the value is a number. Sometimes these strings are hundreds of characters long, other times they are short. To save space, improve performance, and make everything uniformly sized, the strings are not used directly in processing. Instead, a 32-bit or 64-bit hash is computed for each value. All reports run on these hashed values, where each hash is replaced by the original text. Hashes drastically increase the performance of Analytics reports.

For most fields, the string is first converted to all lower case (reducing the number of unique values). Values are hashed on a monthly basis (the first time they are seen each month). From month to month there is a small possibility that two unique variable values hash to the same value. This concept is known as a *hash collision*.

Hash collisions can manifest in reporting as follows:

* If you are trending a value and you see a spike for a month, it is likely that another values for that variable got hashed to the same value as the value you are looking at.
* The same things happens for segments for a specific value.

## Hash collision example

The likelihood of hash collisions increases with the number of unique values in a dimension. For example, one of the values that come in late in the month could get the same hash value as a value earlier in the month. The following example can help explain how this can cause segment results to change. Suppose eVar62 receives "value 100" on February 18. Analytics will maintain a table that may look like this: 

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 String Value </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Value 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Value 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Value 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

If you build a segment that looks for visits where eVar62="value 500", Analytics determines if "value 500" contains a hash. Because "value 500" does not exist, Analytics returns zero visits. Then, on February 23, eVar62 receives "value 500", and the hash for that is also 123. The table will look like this: 

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 String Value </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Value 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Value 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Value 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Value 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

When the same segment runs again, it looks for the hash of "value 500", finds 123, and the report returns all visits that contain hash 123. Now, visits that occurred on February 18 will be included in the results.

This situation can create problems when using Analytics. Adobe continues to investigate ways to reduce the likelihood of these hash collisions in the future. Suggestions to avoid this situation are to find ways to spread the unique values between variables, remove unnecessary values with processing rules, or otherwise reduce the number of values per variable.
