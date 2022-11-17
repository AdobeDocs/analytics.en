---
description: Examples of Data Privacy Labels for Adobe Analytics Variables
title: Data Privacy Labels for Analytics Variables
feature: Data Governance
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
---
# Data Privacy Labels for Analytics Variables

## Why Label Your Data? {#why-label}

Many Adobe customers have legal teams that have reviewed the Data Privacy laws (GDPR, CCPA, etc.). These teams may have drawn their own conclusions about how data should be handled in order to conform with Data Privacy laws. The legal interpretations may differ across companies and the desired data handling settings may also differ across customers. Since customers have differing preferences for Data Privacy data processing and differing data sets, Adobe is enabling Adobe customers, as the data controller, to customize their desired settings for Data Privacy data processing for their unique data. This allows each unique customer to process Data Privacy requests in the way that makes most sense for their brand and their unique data set.

Adobe Analytics provides tools for labeling data according to its sensitivity and contractual restrictions. Labels are important and useful for helping: (1) identify data subjects, (2) determine which data to return as part of an access request, and (3) identify data fields that must be deleted as part of a deletion request.

Before you can figure out which labels should be applied to which variables/fields, you need to [understand the IDs](/help/admin/c-data-governance/gdpr-analytics-ids.md) that you are capturing in your Analytics data, and to decide which you will use for Data Privacy requests.

The Adobe Analytics Data Privacy implementation supports the following labels for identity data, sensitive data, and data governance.

## DULE Labels {#dule-labels}

>[!NOTE]
>
>The Data Usage Labeling & Enforcement (DULE) Framework is designed to provide a uniform way across all Adobe Solutions/Services/Platforms to capture, communicate, and use metadata about data across the Adobe Experience Cloud. The metadata helps data controllers indicate which data is personal information, which data is sensitive data, and what contract restrictions are associated with data. In this initial release, Analytics is exposing only the DULE labels that are relevant to Data Privacy. As other Adobe products implement support for DULE labels, future releases will introduce additional sensitive data labels, as well as contractual labels, which will help ensure that data shared between products is used only in legally permissible ways.

## Identity Data Labels (DULE) {#identity-data-labels}

Identity data "I" labels are used to categorize data that can identify or contact a specific person.

<table id="table_6B5368D714424E52835D5DFE189BD080"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Other Requirements </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I1 </p> </td> 
   <td colname="col2"> <p><b>Directly identifiable</b>: Data that can specifically identify or enable direct contact with an individual, such as a name or an email address. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">Cannot be set on events </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">Cannot be set on Merchandising eVars </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>Indirectly identifiable</b>: Data that can be used in combination with any other data to identify or enable direct contact with an individual or device. </p> <p>Does not allow identification of an individual by itself, but can be combined with other information (that may or may not be in your possession) to identify someone. Examples include a customer loyalty number, or an ID used by a company's CRM system that is unique for each of their customers. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">Cannot be set on events </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">Cannot be set on Merchandising eVars </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Sensitive Data Labels (DULE) {#sensitive-data-labels}

Sensitive data "S" labels are used to categorize sensitive data such as geographic data. Additional Sensitive Data labels will be introduced in the future to identify other types of sensitive information.

<table id="table_A778A508620545CCB37830E5CF1C75B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>S1 </p> </td> 
   <td colname="col2"> <p> Precise geo-location data related to latitude and longitude that can be used to determine the exact location of a device (within 100 meters or less). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> Geo-location data that can be used to determine a broadly defined geo-fence area. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Data Governance Labels (Data Privacy) {#data-governance-labels}

Data Governance labels provide users the ability to classify data that reflects privacy-related considerations and contractual conditions to be compliant with regulations and corporate policies.

### Data Privacy Access Labels

<table id="table_663EFF43A454498386F7F3E60875E0F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Other Requirements </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>None </p> </td> 
   <td colname="col2"> <p>Select this option if this variable does not contain data that must be included in data returned to the data subject as part of a Data Privacy access request. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-ALL </p> </td> 
   <td colname="col2"> <p>Values in this field should be included in <u>all</u> Data Privacy access requests. </p> <p>If this hit came from a device shared by multiple individuals, by applying this label, you, as the data controller, are indicating that it is acceptable to share the data in this field with any individual who had access to the shared device. </p> </td> 
   <td colname="col3"> <p>Fields with this label will be returned for all Data Privacy requests. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-PERSON </p> </td> 
   <td colname="col2"> <p> Values in this field should be included only for Data Privacy access requests when we are reasonably certain that the hit was from the data subject, as determined by a Data Privacy request ID matching an ID-PERSON field's value. </p> </td> 
   <td colname="col3"> <p>You must also have an ID-PERSON label set on some variable within this report suite, and submit requests using that ID, or this label will never apply. </p> </td> 
  </tr> 
 </tbody> 
</table>

While few variables will receive any of the other labels, it is expected that access labels will be applied to many of your variables. However, it is up to you, in consultation with your Legal team, to decide which data you have collected should be shared with data subjects.

### Data Privacy Delete Labels

<table id="table_59DFCE4D90214CB5972BDDE5B7391B4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Other Requirements </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Unlike the other labels, these Delete labels are not mutually exclusive. You can select either, both or none. A separate None label is not necessary, because None is indicated simply by not checking either of the Delete options. </p> </td> 
   <td colname="col3"> <p>A delete label is required only for fields that contain a value that would allow a hit to be associated with the data subject (i.e. that would allow identification of the data subject). </p> <p> Other personal information (favorites, browsing/purchase history, health conditions, etc.) does not need to be deleted since the association with the data subject will be severed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-DEVICE </p> </td> 
   <td colname="col2"> <p>For Data Privacy delete requests, values in this field should be anonymized only for requests where a specified ID-DEVICE is present in the hit. </p> <p>If the same value occurs on other hits, which are not being deleted, then those other instances will not be changed. This will result in the counts changing for reports which compute unique counts on this field. On shared devices, this may remove identifiers for other individuals, beyond just the data subject. </p> <p>Counts do not change if this field also has an ID-DEVICE label and the value in this field was used as an ID for the Data Privacy request. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">Also requires I1 or I2 or S1 label </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">Cannot be set on events </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">Cannot be set on Merchandising eVars </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">Cannot be set on Classifications </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">You must submit requests using an ID-DEVICE or set expandIDs to true, or this label will never apply. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>For Data Privacy delete requests, values in this field should be anonymized only for requests where a specified ID-PERSON is present in the hit. </p> <p>If the same value occurs on other hits, which are not being deleted, then those other values will not be changed. This will result in the counts changing for reports which compute unique counts on this field. Counts will not change if this field also has an ID-PERSON label and the value in this field was used as an ID for the Data Privacy request. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">Also requires I1 or I2 or S1 label </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">Cannot be set on events </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">Cannot be set on Merchandising eVars </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">Cannot be set on Classifications </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">You must also have an ID-PERSON label set on some variable within this report suite and submit requests using that ID, or this label will never apply. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Data Privacy Identity Labels

<table id="table_F6BBC868457443A19A7B693BD6C55B4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Other Requirements </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>None </p> </td> 
   <td colname="col2"> <p>This variable does not contain an ID that will be used for Data Privacy requests. </p> </td> 
   <td colname="col3"> <p>You need to set one of these other labels only if this field contains an ID that you will use when submitting access or delete requests through the [Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) or UI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-DEVICE </p> </td> 
   <td colname="col2"> <p>This field contains an ID that can be used to identify a device for a Data Privacy request , but cannot distinguish between different users of a shared device. </p> <p>You do not need to specify this label for all variables that contain IDs (that is what the I1/I2 labels are for). Use this label if you submit Data Privacy requests using IDs stored in this variable and want to search this variable for the specified ID. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_618019CB8FCA4A5C94C47636240197B2"> 
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">Also requires I1 or I2 label </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">Cannot be set on events </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">Cannot be set on Merchandising eVars </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">Cannot be set on Classifications </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSON </p> </td> 
   <td colname="col2"> <p>This field contains an ID that can be used to identify an authenticated user (a specific person) for a Data Privacy request. </p> <p>You do not need to specify this label for all variables that contain IDs (that is what the I1/I2 labels are for). Use this label if you will submit Data Privacy requests using IDs stored in this variable and want to search this variable for the specified ID. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">Also requires I1 or I2 label </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">Cannot be set on events </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">Cannot be set on Merchandising eVars </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">Cannot be set on Classifications </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

| Label | Definition | Other Requirements |
| --- | --- | --- |
| None | This variable does not contain an ID that will be used for Data Privacy requests.|You need to set one of these other labels only if this field contains an ID that you will use when submitting access or delete requests through the [Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) or UI.|
| ID-DEVICE | This field contains an ID that can be used to identify a device for a Data Privacy request , but cannot distinguish between different users of a shared device.  You do not need to specify this label for all variables that contain IDs (that is what the I1/I2 labels are for). Use this label if you submit Data Privacy requests using IDs stored in this variable and want to search this variable for the specified ID.|Also requires I1 or I2 label.<ul><li>Cannot be set on events</li><li>Cannot be set on Merchandising eVars</li><li>Cannot be set on Classifications</li></ul> |
| ID-PERSON | This field contains an ID that can be used to identify an authenticated user (a specific person) for a Data Privacy request.  You do not need to specify this label for all variables that contain IDs (that is what the I1/I2 labels are for). Use this label if you will submit Data Privacy requests using IDs stored in this variable and want to search this variable for the specified ID. | Also requires I1 or I2 label.<ul><li>Cannot be set on events</li><li>Cannot be set on Merchandising eVars</li><li>Cannot be set on Classifications</li></ul> |

## Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

When you label a variable as ID-DEVICE or ID-PERSON, you are prompted to provide a namespace. You can either use a previously defined namespace or define a new one.

### Use a Previously Defined Namespace

If you have previously assigned an ID label to other variables in any of the report suites in your login company, you can select one of these existing namespaces. You should reuse the namespace if this variable contains the same type of IDs as other variables that are already labeled with this namespace and you want to search all of them when submitting a request.

1. Click **[!UICONTROL Select Namespace]** and select one of the existing namespaces.
1. Click **[!UICONTROL Apply]**.

![](assets/namespace.png)

### Define a New Namespace

You can also define a new namespace. We recommend that namespace strings be limited to alphanumeric characters, plus the characters underscore, dash and space. They will be converted to all lower case.

1. Click **[!UICONTROL Select Namespace]** and type in the namespace title.

   ![](assets/namespace2.png)

1. Press **[!UICONTROL Enter]** to add this namespace. Only now will the Apply button be activated.
1. Click **[!UICONTROL Apply]**.

The string you specify as the namespace is the same string you should use when submitting requests through the Data Privacy API as the value of the "namespace" parameter. The request will then cause Adobe Analytics to search all variables in all of your report suites that share this namespace for the ID you specified with the request.

You do not need to specify the ID-DEVICE or ID-PERSON labels on all variables that contain IDs (that is what the I1/I2 labels are for). Use this label if you will be submitting Data Privacy requests using IDs stored in this variable and want to search this variable for the specified ID. As an example, if eVar1 can contain an email address, and eVar2 can contain a login user name, but you will only ever submit requests using the user name, then you might label eVar1 as I1, ACC-PERSON, DEL-PERSON, but eVar2 as I2, ACC-PERSON, DEL-PERSON, ID-PERSON with namespace "user name". You can then submit a request with a user section JSON block such as:

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}

```

It is acceptable to use the same namespace for different variables within the same report suite. For example, some custom implementations store a CRM-ID in both a prop and an eVar. If the CRM-ID always occurs in one of them (such as the eVar), and only occasionally occurs in the other (the prop), and never in the prop when not also in the eVar, then only the eVar requires an ID label and a namespace, as Adobe can search only in that eVar for the ID. If, however, the CRM-ID sometimes occurs in one variable and sometimes in the other, then both should have the same namespace and Adobe will search both variables for occurrences of the ID specified as part of a Data Privacy request with this namespace. You should still have DEL labels on all of these variables, so that the value is anonymized no matter where it occurs.

As another example, you might have a CRM ID that is sometimes sent in via eVar1 and sometimes sent in via prop7. You then have a processing rule that copies the value from eVar1, if it exists, into eVar3. Otherwise it copies the value from prop7 into eVar3. In this scenario, eVar3 will always contain the CRM ID if it is known, so only eVar3 requires an ID-PERSON label.

>[!CAUTION]
>
>The namespaces "visitorId" and "customVisitorId" are reserved for identifying the Analytics legacy tracking cookie and the Analytics customer visitor ID. Do not use these namespaces for custom traffic or conversion variables.

## Variable Types and the Data Privacy/DULE Labels they support {#section_CE7C3EDE1344466A98BC45E394B40762}

Data Privacy/DULE labeling affects four broad classes of Analytics variables. Not all variables support all labels. This table shows which variables support or don't support which labels.

<table id="table_95D4416B3A8A40C28B2610D0003456E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Type </th> 
   <th colname="col2" class="entry"> Supported Labels </th> 
   <th colname="col3" class="entry"> Unsupported Labels </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_0615B545A5AD43F2A6F25698A47AAD3E"> 
     <li id="li_A4B3E8E241B149C99F2A71B21227AD72">Custom Success Events </li> 
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">Merchandising eVars </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">Multi-valued variables (mvVars) </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">Hierarchy variables </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1/S2 </p> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2 </p> <p>ID-DEVICE, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Classifications </p> </td> 
   <td colname="col2"> <p>I1/I2, S1/S2 </p> <p>ACC-ALL, ACC-PERSON, </p> </td> 
   <td colname="col3"> <p>ID-DEVICE, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_1C2FD4D606664965A88F10818E1C11A9"> 
     <li id="li_590975F5C7304317B22C80B20718E914">Traffic variables (props) </li> 
     <li id="li_6E614B7036994434BFDA71A4424529A0">Commerce variables (non-merchandising eVars) </li> 
    </ul> </td> 
   <td colname="col2"> <p>All labels </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Most other variables </p> <p><i>(See table below for exceptions)</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2, S1/S2 </p> <p>ID-DEVICE, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables to which Labels other than ACC-ALL/ACC-PERSON can be assigned/modified {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Group </th> 
   <th colname="col2" class="entry"> Variables </th> 
   <th colname="col3" class="entry"> Modifiable Labels </th> 
   <th colname="col4" class="entry"> Comment </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">Conversion Dimensions </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">Custom Traffic Dimensions </li> 
    </ul> </td> 
   <td colname="col2"> <p>All, except classifications </p> </td> 
   <td colname="col3"> <p>All </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Classifications </p> </td> 
   <td colname="col3"> <p>None / I1 / I2 </p> <p>None / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conversion Events </p> </td> 
   <td colname="col2"> <p>All </p> </td> 
   <td colname="col3"> <p>None / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Solution Dimensions and Events </p> </td> 
   <td colname="col2"> <p>Activity Map Link, </p> <p>Activity Map Page </p> </td> 
   <td colname="col3"> <p>None / I1 / I2 </p> <p>None / DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Variables can contain URL parameters, which may include directly or indirectly identifiable data. If your implementation does not collect directly or indirectly identifiable data in these variables, then they don't need Identity or deletion labels. </p> <p>Note that delete clears the URL parameters, but preserves the base URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Processing Dimensions </p> </td> 
   <td colname="col2"> <p>Custom Visitor ID </p> </td> 
   <td colname="col3"> <p>ID-DEVICE/ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>You cannot remove the ID or DEL labels (set to None), but you can change them to be either the DEVICE or PERSON variants, depending on your custom ID implementation. </p> <p>If you don't use the custom visitor ID, then the setting does not matter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Standard Dimensions </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Data Processing Dimensions </li> 
    </ul> </td> 
   <td colname="col2"> <p>IP Address </p> <p>IP Address 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>You cannot remove the DEL label, but you can change it to be either DEL-DEVICE or DEL-PERSON, or both. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ClickMap Action (Legacy), </p> <p>ClickMap Context (Legacy), </p> <p>Page, </p> <p>Page URL, </p> <p>Original Entry Page URL, </p> <p>Referrer, </p> <p>Visit Start Page URL </p> </td> 
   <td colname="col3"> <p>None / I1 / I2 </p> <p>None / DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Variables can contain URL parameters, which may include directly or indirectly identifiable data. If your implementation does not collect directly or indirectly identifiable data in these variables, then they don't need Identity or deletion labels. </p> <p>Note that delete clears the URL parameters, but preserves the base URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Deletion Handling {#section_F3DEE591671A4B16A8E043F91C137ECB}

Adobe Analytics support for Data Privacy deletion requests is designed to minimize impacts to reporting. In most cases, the metrics displayed in reports should not change. A historical report that was run before Data Privacy deletion will match the same report run after deletion has been performed. This is accomplished by completely disassociating the deleted data from the data subject, while leaving non-identifiable data in place so that reported values remain consistent.

The following table describes how various variables are "deleted". This is not a complete list.

<table id="table_A329C2E2645F4685BC208826D070A5F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variables </th> 
   <th colname="col2" class="entry"> Deletion Method </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>• Traffic Variables (props) </p> <p>• Commerce Variables (eVars) </p> </td> 
   <td colname="col2"> <p>Existing value is replaced with a new value of the form "Data Privacy-356396D55C4F9C7AB3FBB2F2FA223482" where the 32-digit hexadecimal value after the "Data Privacy-" prefix is a cryptographically strong 128-bit pseudorandom number. Because it is essentially being replaced by a random string, there is no way to determine the original value from this new value, and no way to derive the new value knowing the original value. </p> <p>For a given variable, if the identical value as that being replaced occurs within other hits that are also being deleted as part of the same Data Privacy request, all instances of that value will be replaced with the same new value. </p> <p>If some instances of a value are replaced with one delete request, and a later request deletes other (new) instances of the original value, the new replacement value will be different than the original replacement value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Purchase ID </p> </td> 
   <td colname="col2"> <p>Existing value is replaced by a new value of the form "G-7588FCD8642718EC50" where the 18 hexadecimal digits after the "G-" prefix are the first 18 digits of a cryptographically strong 128-bit pseudorandom number. All comments that apply to deletion of traffic and commerce variables apply here as well. </p> <p>The Purchase ID is a transaction ID whose main purpose is to make sure that a purchase is not credited twice, such as when someone refreshes their purchase confirmation page. The ID itself may tie the purchase to a row in your own DB where the purchase is recorded. In most cases it is not necessary to delete this ID, so it is not deleted by default. If you are still able to tie the purchase back to a user after the Data Privacy delete request of your own data, then you may need to delete this field, so that the Analytics data for this visitor cannot be tied back to the purchaser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitor ID </p> </td> 
   <td colname="col2"> <p>Value is a 128-bit integer and is replaced with a cryptographically strong 128-bit pseudorandom value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• Custom Visitor ID </p> <p>• IP Address </p> <p>• IP Address 2 </p> </td> 
   <td colname="col2"> <p>Value is cleared (set to either the empty string or 0 depending on the variable's type). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• ClickMap Action (Legacy) </p> <p>• ClickMap Context (Legacy) </p> <p>• Page </p> <p>• Page URL </p> <p>• Original Entry Page URL </p> <p>• Referrer </p> <p>• Visit Start Page URL </p> </td> 
   <td colname="col2"> <p>URL parameters are cleared/removed. If the value does not look like a URL, then the value is cleared (set to the empty string). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• Latitude </p> <p>• Longitude </p> </td> 
   <td colname="col2"> <p>Precision is reduced to no better than 1 km. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables that Don't Support the Expected Delete Labels {#section_956B766EFFEC427E87E6CFF3A4217E86}

This section intends to clarify information about Analytics variables that don't support deletion. Sometimes, these variables get deleted by non-Analytics users (such as the legal team) who do not understand the type of data contained in the variable and make incorrect assumptions based on the name of the variable. Here is a list of some of these variables and why they don't require deletion, or why they don't require a specific deletion label.

<table id="table_6FECF3D654514862912D371E6BE4143B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Comments </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>New Visitor ID </p> </td> 
   <td colname="col2"> <p>New visitor id is a Boolean that is true the first time we see a given visitor ID. There is no need to delete it once the visitor ID is anonymized. After anonymization, it will correspond to the first time we have seen this anonymized ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zip Code </p> <p>Geo Zip Code </p> </td> 
   <td colname="col2"> <p>Zip codes are set only for hits originating in the USA. They are not set for hits coming from the EU. Even when set, they only provide a broad geographic area that makes re-identification of the data subject difficult. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geo Latitude </p> <p>Geo Longitude </p> </td> 
   <td colname="col2"> <p>These provide a rough location derived from the IP address. The accuracy is generally similar to that of a zip code, within a few dozen kilometers of the actual location. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User Agent </p> </td> 
   <td colname="col2"> <p>The User Agent identifies the version of the browser that was used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User ID </p> </td> 
   <td colname="col2"> <p> Specifies the Analytics report suite (as a number) containing the data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Suite ID </p> </td> 
   <td colname="col2"> <p> Specifies the name of the Analytics report suite containing the data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitor ID </p> <p>MCID / ECID </p> </td> 
   <td colname="col2"> <p> These have a DEL-DEVICE label, but the DEL-PERSON label cannot be added. If you specify <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> ID Expansion</a> with each request, then these IDs will automatically be deleted for all delete requests, even those using an ID-PERSON. </p> <p>If you do not use ID Expansion, but want these cookie IDs anonymized on hits that contain a matching ID in a prop or eVar, you can work around this labeling limitation by labeling the prop or eVar with an ID-DEVICE label, even if it really identifies a person (all DEL-PERSON labels would also need to be changed to DEL-DEVICE labels). In this case, since only some instances of the visitor ID or ECID are being anonymized, unique visitor counts will change in historical reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p> The Adobe Advertising Cloud ID is a solution variable that has an unmodifiable DEL-DEVICE label. It is populated from a cookie just as the Visitor ID and MCID are. It should be deleted from hits whenever those other IDs are deleted. See the description for those variables for more details. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Date Fields for Access Requests {#section_6678FB4FF42B481C9B78E64F61782397}

There are five standard variables that contain timestamps: 

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Time Stamp </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Hit Time UTC </p> </td> 
   <td colname="col2"> <p>The time that Adobe Analytics received the hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Hit Time UTC </p> </td> 
   <td colname="col2"> <p>Time that the hit occurred, which for some mobile apps and other implementations may be earlier than the time it was received. For example, if a network connection was not available when it occurred, the app may hold the hit and send it in when a connection becomes available. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date Time </p> </td> 
   <td colname="col2"> <p>Same value as Custom Hit Time UTC, but in the time zone of the report suite, rather than GMT.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>First Hit Time GMT </p> </td> 
   <td colname="col2"> <p>The Custom Hit Time UTC value for the first hit received for the visitor ID value for this hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visit Start Time UTC </p> </td> 
   <td colname="col2"> <p>The Custom Hit Time UTC value for the first hit received for the current visit for this visitor ID.</p> </td> 
  </tr> 
 </tbody> 
</table>

The code for generating the files returned for Data Privacy access requests requires that at least one of the first three timestamp variables be included in the access request (have an ACC label that applies to the type of request). If none of these are included, then Custom Hit Time UTC will be treated as if it has an ACC-ALL label.

The hit-level CSV file returned for Data Privacy access requests will convert the values in these fields from unix timestamps to date/time fields of the format YYYY-MM-DD HH:MM:SS (for example, 2018-05-01 13:49:22). In the summary HTML file, these timestamp values will be truncated to only include the date, YYYY-MM-DD, to reduce the number of unique values that occur for these fields.
