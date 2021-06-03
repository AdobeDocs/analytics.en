---
description: Understand the IDs captured in your Analytics data, and decide which you will use for Data Privacy requests.
title: Labeling best practices
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
---
# Labeling best practices

>[!NOTE]
>
>Remember that Labeling needs to be reviewed each time a new report suite is created or when new variable is enabled within an existing report suite. You may also need to review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites may change the way that existing variables are used, which may also necessitate updates to labels.

## Directly vs Indirectly Identifiable IDs {#section_030799AA1397433FBA61A2BC60A7A750}

Before you can figure out which labels should be applied to which variables/fields, it is first necessary to understand the IDs that you are capturing in your Analytics data, and to decide which you will use for Data Privacy requests. Data Privacy expands the scope of what can be considered to be an ID. IDs fall into two broad classes: directly identifiable (identity label: I1) and indirectly identifiable (identity label: I2).

* **A directly identifiable ID (I1)**: Either names the person or provides a direct method of contacting them. Examples would include someone's name (even a common name like John Smith that may be shared by hundreds of people), any of their email addresses or phone numbers, etc. A mailing address without a name might be considered directly identifiable, even though it may only identify a household or business rather than a specific person within that household or business.
* **An indirectly identifiable ID (I2)**: Does not allow identification of an individual by itself, but can be combined with other information (that may or may not be in your possession), to identify someone. Examples would include a customer loyalty number, or an ID used by a company's CRM system that is unique for each of their customers. Under Data Privacy, the anonymous IDs stored in the tracking cookies used by Analytics may be deemed to be indirectly identifying, even though they can only identify a device rather than an individual; on a shared device, these cookies cannot distinguish between different users of the system. For example, while the cookie cannot be used to find a computer containing the cookie, if someone has access to the computer and locates the cookie, they can then tie the Analytics cookie data back to the computer.

  An IP address is also considered to be indirectly identifiable, because at any given instance in time, it might only be assigned to a single device. However, ISPs can and often do change the IP addresses for most users regularly, so over time an IP address may have been used by any of their users. It is also not uncommon for many customers of an ISP or multiple employees within a business on the same intranet to share the same external IP address. Because of this, Adobe will not support using an IP address as the ID for a [Data Privacy request.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) However, when an ID that we accept is used as part of a delete request, we will clear the IP addresses that occurred with that ID as well. You must decide if there exist other IDs that you collect that may fall into this category, of I1 or I2, but not suitable for use as a distinguishing ID for Data Privacy requests.

Even if your company collects many different IDs within your Analytics data, you may elect to use only a subset of these IDs for Data Privacy requests. Reasons for this might include:

* Within your own systems, you can map one of the IDs (for example, email address) to a different ID (such as CRM ID). Then, for consistency, you decide to only use the CRM ID for Data Privacy requests in your Data Privacy processing.
* You do not have a method of validating that someone is actually the person associated with the ID. For example, it can be very difficult to validate that an IP address was only ever used by a single person and that the person submitting the request is actually that person.
* Some IDs may correspond to multiple people and you don't want to risk returning information about one person to someone else with that same ID. For example, even if you can verify that someone's name is John Smith, you may not want to return all data about all John Smiths in your system.
* Another example is a device ID, such as the Analytics Cookie ID. If the ID occurs on a cell phone app, you may decide that all interactions using that ID should be available to the owner of the cell phone. However, if it occurs on a shared device, such as a home computer or one in a library or internet cafe, you may decide that you cannot distinguish between users of that device and the risk of returning data for a different user is too great to allow using this type of ID.

## Best Practices for IDs Supported by Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Use this table to determine the types of IDs that you will use when submitting Data Privacy requests to Analytics. Once you know this information, it will be easier to determine the other labels you should use for your variables.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID Type </th> 
   <th colname="col2" class="entry"> Recommendations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie IDs </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/ core-services/interface/ec-cookies/cookies-privacy.html"> (Legacy) Analytics Cookie </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/ id-service/using/home.html"> Identity Service cookie </a> (ECID), previously known as the Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>These cookies identify a device or, more specifically, a browser for a user of a device. For a shared device where a common login is used, this ID could apply to any/all users of the device. Adobe has created some <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm"> unified JavaScript </a> that you can place on your website to collect these cookies if you want to allow them to be used for Data Privacy requests. </p> <p>Users of the Adobe Analytics Mobile SDK also have an Experience Cloud ID (ECID). There are API calls within the SDK to read this ID, so you can enhance your app to collect it for a Data Privacy request. </p> <p>Many companies consider the browser cookie IDs to be shared device IDs. As a result, in consultation with their legal teams, they may elect not to support using them as acceptable IDs for Data Privacy requests, or they may elect to return only a very limited amount of data when these IDs are used or they may only accept them for delete requests. </p> <p>These cookies have an ID-DEVICE label that cannot be changed (as well as I2 and DEL-DEVICE labels). The default Adobe Analytics configuration will return only generic information about the device, such as device type, OS, browser, etc. plus the time/dates that your website was visited when using these IDs. However, if you choose to support these IDs for Data Privacy requests, as discussed below, you can add or remove ACC-ALL labels to configure the exact set of fields you desire be returned for a Data Privacy access request. </p> <p>Especially if the report suite corresponds to a mobile app, and your mobile app requires a login, you may decide that the Experience Cloud ID for the device does correspond to a specific user and you will therefore want to label more of the fields with the ACC-ALL label, including the names of pages visited, products viewed, etc. </p> <p>Note:  If you specify the "expandIds" option in your Data Privacy request, then your requests will always include Cookie IDs, in addition to any other IDs you specify. See <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> ID Expansion </a> for more details. In these instances, hits that have only a cookie ID, but not another ID, will only return data labeled ACC-ALL as part of the access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IDs in Custom Variables </p> </td> 
   <td colname="col2"> <p>Some customers place IDs in <a href="https://experienceleague.adobe.com/docs/ analytics/implementation/vars/page-vars/evar.html"> custom traffic variables (props) or custom conversion variables (eVars) </a>. While the most common is a CRM ID, others include email addresses, user login names, customer loyalty numbers or hashes of these values . </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">If you want to use one of these IDs for Data Privacy requests, you should give the field containing it an ID-PERSON label. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Much less common) If an ID in one of these custom variables only identifies a device that may be shared by multiple people, then you can instead use an ID-DEVICE label. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">These fields also require I1 or I2 labels, and should include a DEL-PERSON or DEL-DEVICE label. Typically, the PERSON/DEVICE option of the DEL label will match the PERSON/DEVICE option of the ID label. </li> 
    </ul> <p> It is rare for a report suite to have more than one or two custom variables containing IDs that you would want to use to identify data subjects for Data Privacy requests. You may have multiple variables that are assigned I1 or I2 labels, but typically only one or two of these would also have ID-PERSON or ID-DEVICE labels. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Visitor ID </p> </td> 
   <td colname="col2"> <p>Even though this is not widely used, Analytics also supports an implementation where a custom visitor ID can be provided, which if present is used in place of the Legacy Analytics Tracking Cookie. This field has the labels I2, ID-PERSON and DEL-PERSON. </p> <p>Many implementations derive this ID from a CRM ID so it is only present while someone is logged into their site. This allows the same Custom Visitor ID to be used across devices. One technical drawback is that tracking that happens before the user logs in cannot be tied to tracking collected after they are logged in. If, instead, you use the custom visitor ID to simply identify a device, you should change the ID-PERSON and DEL- PERSON labels to ID-DEVICE and DEL- DEVICE, respectively. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices for Setting Delete Labels {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]
>
>Props are always case insensitive. eVars are case insensitive by default, but can be configured through Adobe Customer Care to be case sensitive. If you have a case-sensitive eVar that contains an ID, it is your responsibility to use the proper case when submitting a Data Privacy request so that the case used in the request matches the case used in hits containing these IDs.

The delete labels DEL-DEVICE and DEL-PERSON should be used sparingly. When applied to a variable that does not contain an ID that was used as part of the Data Privacy request, counts (metrics) in historical Analytics reports will almost always change.

* We recommend that one of these labels be applied to any variable that is labeled I1, I2 or S1. They cannot be applied to any variable that does is not labeled I1, I2 or S1.
* The DEL-labels will result in these variables being [anonymized](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) (the ID will be replaced with a random string prefixed with "Data Privacy-"). The same anonymized value will replace all instances of the original value in all hits that have been identified by an ID used in the request. If the original value in this field was one of those IDs, then report metrics will not change.
* Generally, if a field has the label ID-DEVICE, then you should also assign the label DEL-DEVICE.
* Similarly, if a field has the label ID-PERSON, then you should also assign the label DEL-PERSON.
* If a field does not have an ID-label, but does contain identifying information that you want anonymized, then the appropriate label (DEVICE or PERSON) depends on your implementation. If you only use cookie IDs for Data Privacy requests, then you should use DEL-DEVICE.
* If you use custom IDs on a different field with an ID-PERSON label, and you only want this cleared on rows where that ID occurs, then use DEL-PERSON.
* If you are using ID expansion, and want all the value cleared for all hits on all identified devices then use DEL-DEVICE. You can apply both the DEL-DEVICE and DEL-PERSON labels in this case if you prefer, but the DEL-PERSON label is unnecessary, because the ID Expansion means that all rows that match a person ID will also match a device ID.
* If you will not be specifying to use ID Expansion, but will use a mix of device and person IDs for different requests, then you may want to specify both DEL-DEVICE and DEL-PERSON labels for variables that should be deleted when either type of ID is used.
* Note that if a DEL-DEVICE or DEL-PERSON label is specified on any variable that is not also used as an ID for that request (including an expanded ID), then unique values in that variable will only be anonymized on hits where a specified (or expanded) ID occurs. If other hits contain the same value, it will not be updated in those other locations. This can result in counts (metrics) changing.

  For example, if you have three hits containing the value "foo" in eVar7, but only one of them also contains an ID in a different variable that is matched for a delete, then "foo" on that hit will be modified to a value like "Data Privacy-123456789", while it will remain unchanged in the other two hits. A report that shows the number of unique values for eVar7 will now show one more unique value than it did previously. A report that shows the top values for eVars may include "foo" with only two instances (rather than 3 previously), and the new value will show up as well, with a single instance.

## Best Practices for Setting Access Labels {#section_AC7E216F81C141FCA6A62F8836E06EE7}

While very few fields will have any of the other labels, it will be common for a large number of fields to have ACC labels. The appropriate access labels will depend on the IDs you are using for Data Privacy requests.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> If you use... </th> 
   <th colname="col2" class="entry"> ...use these Recommendations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Device IDs Only </p> </td> 
   <td colname="col2"> <p>If the only IDs you are using are cookie IDs or those with an ID-DEVICE label, then you should only use the ACC-ALL label. </p> <p>You will get one pair of files for each access request, one containing a row for each matching hit with all the specified ACC-ALL fields and a second containing a summary of this data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Person IDs with no ID Expansion </p> </td> 
   <td colname="col2"> <p>If you are only using custom IDs that have the ID-PERSON label and are not doing ID expansion, then you should use ACC-PERSON labels. However, you do not need to change the default ACC-ALL labels; these fields will automatically be included in the access request. </p> <p>You will get one pair of files for each access request, one containing a row for each matching hit with all the specified ACC-DEVICE and ACC-PERSON fields and a second containing a summary of this data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mixed IDs and/or ID Expansion </p> </td> 
   <td colname="col2"> <p>If you include both device and person IDs in Data Privacy requests, or if you use custom IDs (custom visitor ID or an ID in a prop or eVar), then you need to pay attention to the ACC labels you use. Each access request will return two pairs of data files, one pair containing data from hits which contained a matched person ID and a second containing data from hits that did not match a person ID, but did match a device ID. </p> <p>The "person ID" files contain data on all hits that matched the person IDs with all fields that have either an ACC-PERSON or and ACC-ALL label (one file with all matched hits and the other as a summary). </p> <p>The "device ID" file pair contains only fields that have an ACC-ALL label and contains only hits that did not contain any matching person ID. These files may contain data generated by other users of a shared device, so you will want to consider carefully the set of fields that contain the ACC-ALL label. The default labeling within Analytics only applies this label to generic information fields related to the device (device type, OS, browser, etc.) plus the date/time of each hit. </p> <p>You may elect to receive both the device and person file sets from Adobe and then only share the person files, so as not to share data potentially generated by other users of a shared device. Or you may wish to combine data from one or both sets with other information that you know about the data subject and return it in your own format. </p> </td> 
  </tr> 
 </tbody> 
</table>
