---
description: Each ID that you want to be able to search for is assigned a namespace, which is a custom string that identifies that ID in any variable where it is used across all your report suites.
seo-description: Each ID that you want to be able to search for is assigned a namespace, which is a custom string that identifies that ID in any variable where it is used across all your report suites.
seo-title: Namespaces
title: Namespaces
uuid: cab61844-3209-4980-b14c-6859de777606
index: y
internal: n
snippet: y
---

# Namespaces

Each ID that you want to be able to search for is assigned a namespace, which is a custom string that identifies that ID in any variable where it is used across all your report suites.

The namespace string is used to identify the field(s) that you want searched when providing an ID as part of a GDPR request. When a GDPR request is submitted, the request will include a JSON section specifying the data subject IDs to use for the request. Multiple IDs can be included as part of a single request for a data subject. The JSON includes:

* A "namespace" field containing the namespace string. 
* A "type" field that for most Adobe Analytics requests contains the value "analytics". 
* A "value" field containing the ID that Analytics should search for in the associated namespace variables from each of your report suites.

Refer to the [Experience Cloud GDPR API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details. 

<table id="table_A32B4BD12A26447C8A09928B246B4AE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID Type </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
   <th colname="col3" class="entry"> Notes </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="3"> <p><b>Cookie ID</b> </p> </td> 
   <td colname="col2"> <p><b>Legacy Analytics Tracking Cookie, also known as the Adobe Analytics ID (AAID):</b> </p> 
    <codeblock>
     {
     
&nbsp;&nbsp;&nbsp;&nbsp;namespace:&nbsp;"AAID",
     
&nbsp;&nbsp;&nbsp;&nbsp;type:&nbsp;"standard",
     
&nbsp;&nbsp;&nbsp;&nbsp;value:&nbsp;"2CCEEAE88503384F-1188000089CA"
     
}
    </codeblock> </td> 
   <td colname="col3"> <p>The value must be specified as two hexadecimal numbers separate by a dash. All hexadecimal digits that are alphabetic characters must be specified using upper case. The hexadecimal values should not have any leading zeros (note the difference from the same value specified in the deprecated form, where the leading zeros are required). </p> <p>It is also acceptable to use: </p> <p>“namespaceId”: 10 </p> <p>instead of or in addition to </p> <p>“namespace”: “AAID” </p> <p>and you may see some other Adobe products use that form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><b>Legacy Analytics Tracking Cookie: Deprecated form</b> </p> 
    <codeblock>
     &nbsp;
     
{
     
"namespace":&nbsp;"visitorId",
     
"type":&nbsp;"analytics",
     
"value":
     
"2cceeae88503384f-00001188000089ca"
     
}

    </codeblock> </td> 
   <td colname="col3"> <p><b>Deprecated form:</b> </p> <p>The value should be specified as two 16-digit hexadecimal numbers or as two 19-digit decimal numbers. The numbers should be separated by a dash, underscore or colon. Leading zeros should be added if either number doesn’t have enough digits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><b>Experience Cloud ID Service Cookie</b> </p> 
    <codeblock>
     {
     
&nbsp;&nbsp;&nbsp;&nbsp;namespace:&nbsp;"ECID",
     
&nbsp;&nbsp;&nbsp;&nbsp;type:&nbsp;"standard",
     
&nbsp;&nbsp;&nbsp;&nbsp;value:&nbsp;"00497781304058976192356650736267671594"
     
}
    </codeblock> </td> 
   <td colname="col3"> <p>The value must be specified as a 38-digit decimal number. If you are pulling this number from the two mcvisid_high/low or post_msvisid_high/low columns from a data feed or Data Warehouse report, you must zero pad each of the two numbers to 19 digits and then concatenate them with the high value first. </p> <p>It is also acceptable to use: </p> <p>“namespaceId”: 4 </p> <p>instead of or in addition to </p> <p>“namespace”: “ECID” </p> <p>and you may see some other Adobe products use that form. </p> <p>Note:  The Experience Cloud ID (ECID) was previously known as the Marketing Cloud ID (MCID), and is still referred to by that name in some existing documentation. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>Note:  These IDs are the only IDs supported by Analytics that use a "type" value other than "analytics". </p> <p>If the format of the value portion of any of these cookie IDs does not follow the format described for that ID, then the GDPR request will fail, with an error of “Value not formatted correctly.” </p> <p>You will most commonly collect these cookie IDs using the new<a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html#!api-specification/markdown/narrative/gdpr/use-cases/adobe-privacy-library.md" format="html" scope="external"> privacy JavaScript</a>, which will automatically provide all of the relevant key/value pairs for these JSON IDs. </p> <p>This JavaScript code populates the JSON with other key/value pairs besides those listed above (namespace, type, value), but the fields listed above are the most important for Analytics GDPR processing and the only ones you need to provide if you collect the IDs in some other way. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Custom Visitor ID</b> </p> </td> 
   <td colname="col2"> 
    <codeblock>
     {
     
&nbsp;&nbsp;&nbsp;&nbsp;namespace:&nbsp;"customVisitorID",
     
&nbsp;&nbsp;&nbsp;&nbsp;type:&nbsp;"analytics",
     
&nbsp;&nbsp;&nbsp;&nbsp;value:&nbsp;"&lt;ID&gt;"
     
}
    </codeblock> </td> 
   <td colname="col3"> <p>The namespace is also predefined for the custom visitor ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>IDs in Custom Variables</b> </p> </td> 
   <td colname="col2"> 
    <codeblock>
     {
     
&nbsp;&nbsp;&nbsp;&nbsp;namespace:&nbsp;"Email&nbsp;Address",
     
&nbsp;&nbsp;&nbsp;&nbsp;type:&nbsp;"analytics",
     
&nbsp;&nbsp;&nbsp;&nbsp;value:&nbsp;"john@xyz.com"
     
},
     
{
     
&nbsp;&nbsp;&nbsp;&nbsp;namespace:&nbsp;"CRM&nbsp;ID",
     
&nbsp;&nbsp;&nbsp;&nbsp;type:&nbsp;"analytics",
     
&nbsp;&nbsp;&nbsp;&nbsp;value:&nbsp;"123456-ABCD"
     
}
    </codeblock> </td> 
   <td colname="col3"> <p>For IDs in custom traffic or conversion variables (props or eVars), you should label the variable with an ID-DEVICE or ID-PERSON label and then assign your own namespace name to that type of ID. See <a href="../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7" format="dita" scope="local"> Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON</a>. </p> <p>You can also see namespaces that you have previously defined for other variables or report suites and reuse one of those, so that the same namespace can easily be used for all your report suites that store that type of ID. It is also possible to assign the same namespace to multiple variables within a report suite. For example, some customers store a CRM ID in a traffic variable and a conversion variable (depending on the page, it is sometimes in one or the other or both), and they could assign the namespace "CRM ID" to both variables. </p> <p>Note: You cannot use the friendly name of a variable (the name displayed in the reporting UI) or the variable’s number (such as eVar12) when specifying the namespace to the GDPR API, unless this is also the namespace you specified when applying the ID-DEVICE or ID-PERSON label to this variable. Using a namespace rather than a friendly name allows the same user identity block to specify the correct variable for multiple report suites in these cases: 
     <ul id="ul_37B6E2451A68456D8B94B8F601C012BA"> 
      <li id="li_EC4B0A1830FD46FA9B7CF6EDBA5A9E89">The ID is in different eVars in some of the report suites, or </li> 
      <li id="li_A006C5FF3B784B04B3D992D1E81493C6">The friendly names don’t match (such as when the friendly name has been localized for a specific report suite) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

For more information, see [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7). 
