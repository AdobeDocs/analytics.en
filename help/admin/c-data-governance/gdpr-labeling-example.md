---
description: null
seo-description: null
seo-title: Labeling Example
title: Labeling Example
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
index: y
internal: n
snippet: y
---

# Labeling Example

* [Sample Hit Data](../../admin/c-data-governance/gdpr-labeling-example.md#section_94DE6BC0026F46D7AD7061C5625C8D52) 
* [Sample Access Request](../../admin/c-data-governance/gdpr-labeling-example.md#section_BDA817FD2415420DAAC835825484BA9D) 
* [Sample Delete Request](../../admin/c-data-governance/gdpr-labeling-example.md#section_6C75F70F5D574BE7AA540981E8B7EA26)

## Sample Hit Data {#section_94DE6BC0026F46D7AD7061C5625C8D52}

Suppose you have the following hit data:

* The first row contains the labels for each variable. 
* The second row is the name of the variable. If it has an ID label, it contains the assigned namespace in parentheses. 
* Hit data starts in the third row.

<table id="table_552CB5EA31B54C119487F91AE98723C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Labels </th> 
   <th colname="col2" class="entry"> <p>I2 </p> <p>ID-PERSON </p> <p>DEL-PERSON </p> <p>ACC-PERSON </p> </th> 
   <th colname="col3" class="entry"> <p>I2 </p> <p>ID-DEVICE </p> <p>DEL-DEVICE </p> <p>ACC-ALL </p> </th> 
   <th colname="col4" class="entry"> <p>I2 </p> <p>DEL-PERSON </p> <p>ACC-PERSON </p> <p> </p> </th> 
   <th colname="col5" class="entry"> <p>I2 </p> <p>DEL-DEVICE </p> <p>DEL-PERSON </p> <p>ACC-ALL </p> </th> 
   <th colname="col6" class="entry"> <p>I2 </p> <p>ID-DEVICE </p> <p>DEL-DEVICE </p> <p>ACC-ALL </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Variable Name</b> </p> <p><b>(Namespace)</b> </p> </td> 
   <td colname="col2"> <p><b>MyProp1</b> </p> <p><b>(user)</b> </p> </td> 
   <td colname="col3"> <p><b>Visitor ID</b> </p> <p><b>(AAID)</b> </p> </td> 
   <td colname="col4"> <p><b>MyEvar1</b> </p> </td> 
   <td colname="col5"> <p><b>MyEvar2</b> </p> </td> 
   <td colname="col6"> <p><b>MyEvar3</b> </p> <p><b>(xyz)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="7"> <p>Hit Data </p> </td> 
   <td colname="col2"> Mary </td> 
   <td colname="col3"> 77 </td> 
   <td colname="col4"> A </td> 
   <td colname="col5"> M </td> 
   <td colname="col6"> X </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Mary </td> 
   <td colname="col3"> 88 </td> 
   <td colname="col4"> B </td> 
   <td colname="col5"> N </td> 
   <td colname="col6"> Y </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Mary </td> 
   <td colname="col3"> 99 </td> 
   <td colname="col4"> C </td> 
   <td colname="col5"> O </td> 
   <td colname="col6"> Z </td> 
  </tr> 
  <tr> 
   <td colname="col2"> John </td> 
   <td colname="col3"> 77 </td> 
   <td colname="col4"> D </td> 
   <td colname="col5"> P </td> 
   <td colname="col6"> W </td> 
  </tr> 
  <tr> 
   <td colname="col2"> John </td> 
   <td colname="col3"> 88 </td> 
   <td colname="col4"> E </td> 
   <td colname="col5"> N </td> 
   <td colname="col6"> U </td> 
  </tr> 
  <tr> 
   <td colname="col2"> John </td> 
   <td colname="col3"> 44 </td> 
   <td colname="col4"> F </td> 
   <td colname="col5"> Q </td> 
   <td colname="col6"> V </td> 
  </tr> 
  <tr> 
   <td colname="col2"> John </td> 
   <td colname="col3"> 55 </td> 
   <td colname="col4"> G </td> 
   <td colname="col5"> R </td> 
   <td colname="col6"> X </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Alice </td> 
   <td colname="col3"> 66 </td> 
   <td colname="col4"> A </td> 
   <td colname="col5"> N </td> 
   <td colname="col6"> Z </td> 
  </tr> 
 </tbody> 
</table>

## Sample Access Request {#section_BDA817FD2415420DAAC835825484BA9D}

If I submit an access request, the summary file will contain the values indicated in the table below. A request may return only a device file, only a person file or one of each. Two summary files are only returned if a person ID is used and expandIds is true. 

<table id="table_BF98326DFA3A493B980485466AE0E910"> 
 <thead> 
  <tr> 
   <th class="entry" colspan="2"> API Values </th> 
   <th colname="col3" class="entry"> Returned File Type </th> 
   <th class="entry" colspan="5"> Data in Summary Access File </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Namespace/ ID</b> </td> 
   <td colname="col2"><b>expandIDs</b> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"><b>MyProp1</b> </td> 
   <td colname="col5"><b>Visitor ID</b> </td> 
   <td colname="col6"><b>MyEvar1</b> </td> 
   <td colname="col7"><b>MyEvar2</b> </td> 
   <td colname="col8"><b>MyEvar3</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AAID=77 </td> 
   <td colname="col2"> false </td> 
   <td colname="col3"> device </td> 
   <td colname="col4" morerows="1"> Variable not present </td> 
   <td colname="col5"> 77 </td> 
   <td colname="col6" morerows="1"> Variable not present </td> 
   <td colname="col7"> M, P </td> 
   <td colname="col8"> X, W </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AAID=77 </td> 
   <td colname="col2"> true </td> 
   <td colname="col3"> device </td> 
   <td colname="col5"> 77 </td> 
   <td colname="col7"> M, P </td> 
   <td colname="col8"> X, W </td> 
  </tr> 
  <tr> 
   <td colname="col1"> user=Mary </td> 
   <td colname="col2"> false </td> 
   <td colname="col3"> person </td> 
   <td colname="col4"> Mary </td> 
   <td colname="col5"> 77, 88, 99 </td> 
   <td colname="col6"> A, B, C </td> 
   <td colname="col7"> M, N, O </td> 
   <td colname="col8"> X, Y, Z </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> user=Mary </td> 
   <td colname="col2" morerows="1"> true </td> 
   <td colname="col3"> person </td> 
   <td colname="col4"> Mary </td> 
   <td colname="col5"> 77, 88, 99 </td> 
   <td colname="col6"> A, B, C </td> 
   <td colname="col7"> M, N, O </td> 
   <td colname="col8"> X, Y, Z </td> 
  </tr> 
  <tr> 
   <td colname="col3"> device </td> 
   <td colname="col4"> not present </td> 
   <td colname="col5"> 77, 88 </td> 
   <td colname="col6"> not present </td> 
   <td colname="col7"> N, P </td> 
   <td colname="col8"> U, W </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1">user=Mary <p>AAID=66 </p> </td> 
   <td colname="col2" morerows="1"> true </td> 
   <td colname="col3"> person </td> 
   <td colname="col4"> Mary </td> 
   <td colname="col5"> 77, 88, 99 </td> 
   <td colname="col6"> A, B, C </td> 
   <td colname="col7"> M, N, O </td> 
   <td colname="col8"> X, Y, Z </td> 
  </tr> 
  <tr> 
   <td colname="col3"> device </td> 
   <td colname="col4"> not present </td> 
   <td colname="col5"> 66, 77, 88 </td> 
   <td colname="col6"> not present </td> 
   <td colname="col7"> N, P </td> 
   <td colname="col8"> U, W, Z </td> 
  </tr> 
  <tr> 
   <td colname="col1"> xyz=X </td> 
   <td colname="col2"> false </td> 
   <td colname="col3"> device </td> 
   <td colname="col4"> not present </td> 
   <td colname="col5"> 55, 77 </td> 
   <td colname="col6"> not present </td> 
   <td colname="col7"> M, R </td> 
   <td colname="col8"> X </td> 
  </tr> 
  <tr> 
   <td colname="col1"> xyz=X </td> 
   <td colname="col2"> true </td> 
   <td colname="col3"> device </td> 
   <td colname="col4"> not present </td> 
   <td colname="col5"> 55, 77 </td> 
   <td colname="col6"> not present </td> 
   <td colname="col7"> M, P, R </td> 
   <td colname="col8"> W, X </td> 
  </tr> 
 </tbody> 
</table>

Notice that the setting for expandIDs does not make any difference to the output when a cookie ID is used.

## Sample Delete Request {#section_6C75F70F5D574BE7AA540981E8B7EA26}

With a delete request using the API values in the first row of the table, the hit table will be updated to look something like this: 

<table id="table_B7934409AE0141AB9528ABED98CC033F"> 
 <thead> 
  <tr> 
   <th class="entry" colspan="5">AAID=77 <p>expandIDs value does not matter </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>MyProp1</b> </td> 
   <td colname="col2"><b>AAID</b> </td> 
   <td colname="col3"><b>MyEvar1</b> </td> 
   <td colname="col4"><b>MyEvar2</b> </td> 
   <td colname="col5"><b>MyEvar3</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mary </td> 
   <td colname="col2"> 42 </td> 
   <td colname="col3"> A </td> 
   <td colname="col4"> GDPR-7398 </td> 
   <td colname="col5"> GDPR-9152 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mary </td> 
   <td colname="col2"> 88 </td> 
   <td colname="col3"> B </td> 
   <td colname="col4"> N </td> 
   <td colname="col5"> Y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mary </td> 
   <td colname="col2"> 99 </td> 
   <td colname="col3"> C </td> 
   <td colname="col4"> O </td> 
   <td colname="col5"> Z </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 42 </td> 
   <td colname="col3"> D </td> 
   <td colname="col4"> GDPR-1866 </td> 
   <td colname="col5"> GDPR-8216 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 88 </td> 
   <td colname="col3"> E </td> 
   <td colname="col4"> N </td> 
   <td colname="col5"> U </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 44 </td> 
   <td colname="col3"> F </td> 
   <td colname="col4"> Q </td> 
   <td colname="col5"> V </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 55 </td> 
   <td colname="col3"> G </td> 
   <td colname="col4"> R </td> 
   <td colname="col5"> X </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alice </td> 
   <td colname="col2"> 66 </td> 
   <td colname="col3"> A </td> 
   <td colname="col4"> N </td> 
   <td colname="col5"> W </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Only cells on rows containing AAID = 77 and a DEL-DEVICE label are impacted.

<table id="table_A11491B0E0FF41AD99407710FBAF0D1D"> 
 <thead> 
  <tr> 
   <th class="entry" colspan="5">user=Mary <p>expandIDs=false </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>MyProp1</b> </td> 
   <td colname="col2"><b>AAID</b> </td> 
   <td colname="col3"><b>MyEvar1</b> </td> 
   <td colname="col4"><b>MyEvar2</b> </td> 
   <td colname="col5"><b>MyEvar3</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GDPR-0523 </td> 
   <td colname="col2"> 77 </td> 
   <td colname="col3"> GDPR-1866 </td> 
   <td colname="col4"> GDPR-3681 </td> 
   <td colname="col5"> X </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GDPR-0523 </td> 
   <td colname="col2"> 88 </td> 
   <td colname="col3"> GDPR-2178 </td> 
   <td colname="col4"> GDPR-1975 </td> 
   <td colname="col5"> Y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GDPR-0523 </td> 
   <td colname="col2"> 99 </td> 
   <td colname="col3"> GDPR-9045 </td> 
   <td colname="col4"> GDPR-2864 </td> 
   <td colname="col5"> Z </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 77 </td> 
   <td colname="col3"> D </td> 
   <td colname="col4"> P </td> 
   <td colname="col5"> W </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 88 </td> 
   <td colname="col3"> E </td> 
   <td colname="col4"> N </td> 
   <td colname="col5"> U </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 44 </td> 
   <td colname="col3"> F </td> 
   <td colname="col4"> Q </td> 
   <td colname="col5"> V </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 55 </td> 
   <td colname="col3"> G </td> 
   <td colname="col4"> R </td> 
   <td colname="col5"> X </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alice </td> 
   <td colname="col2"> 66 </td> 
   <td colname="col3"> A </td> 
   <td colname="col4"> N </td> 
   <td colname="col5"> W </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Only cells on rows containing user=Mary and a DEL-PERSON label are impacted. Also, in practice the variable containing A_ID would probably be a prop or eVar and its replacement value would be a string starting with “GDPR-“, followed by a random number (GUID), rather than replacing the numeric value with a different, random numeric value.

<table id="table_21D0852EE2384F7789B3C0E418429CCA"> 
 <thead> 
  <tr> 
   <th class="entry" colspan="5">user=Mary <p>expandIDs=true </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>MyProp1</b> </td> 
   <td colname="col2"><b>AAID</b> </td> 
   <td colname="col3"><b>MyEvar1</b> </td> 
   <td colname="col4"><b>MyEvar2</b> </td> 
   <td colname="col5"><b>MyEvar3</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GDPR-5782 </td> 
   <td colname="col2"> 09 </td> 
   <td colname="col3"> GDPR-0859 </td> 
   <td colname="col4"> GDPR-8183 </td> 
   <td colname="col5"> GDPR-9152 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GDPR-5782 </td> 
   <td colname="col2"> 16 </td> 
   <td colname="col3"> GDPR-6104 </td> 
   <td colname="col4"> GDPR-2911 </td> 
   <td colname="col5"> GDPR-6821 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GDPR-5782 </td> 
   <td colname="col2"> 83 </td> 
   <td colname="col3"> GDPR-2714 </td> 
   <td colname="col4"> GDPR-0219 </td> 
   <td colname="col5"> GDPR-4395 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 09 </td> 
   <td colname="col3"> D </td> 
   <td colname="col4"> GDPR-8454 </td> 
   <td colname="col5"> GDPR-8216 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 16 </td> 
   <td colname="col3"> E </td> 
   <td colname="col4"> GDPR-2911 </td> 
   <td colname="col5"> GDPR-2930 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 44 </td> 
   <td colname="col3"> F </td> 
   <td colname="col4"> Q </td> 
   <td colname="col5"> V </td> 
  </tr> 
  <tr> 
   <td colname="col1"> John </td> 
   <td colname="col2"> 55 </td> 
   <td colname="col3"> G </td> 
   <td colname="col4"> R </td> 
   <td colname="col5"> X </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alice </td> 
   <td colname="col2"> 66 </td> 
   <td colname="col3"> A </td> 
   <td colname="col4"> N </td> 
   <td colname="col5"> W </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* Cells on rows containing user=Mary and a DEL-DEVICE or DEL-PERSON label are impacted, as well as cells with a DEL-DEVICE label on rows containing any Visitor ID that occurred on a row containing user=Mary. 
>* MyEvar2 in the fourth and fifth rows is updated because these rows contain the same Visitor ID values as those on the first and second rows, so ID expansion includes them for device-level deletes. 
>* The values of MyEvar2 in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request. 
>* MyEvar3 behaves very differently than it did without ID expansion, because without ID expansion, no ID-DEVICES matched. Now AAID matches on the first five rows. 
>

