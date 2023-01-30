---
description: The IDs you submit do not always cover all of the hit data that Analytics can associate with the data subject. Analytics can create an expanded set of IDs to include this associated data into the Data Privacy requests. You can request this option with an optional parameter to each Data Privacy request you submit, added to the JSON request 
title: ID Expansion
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
---
# ID Expansion

The IDs you submit do not always cover all of the hit data that Analytics can associate with the data subject. Analytics can create an expanded set of IDs to include this associated data into the Data Privacy requests. You can request this option with an optional parameter to each Data Privacy request you submit, added to the JSON request:

```
"expandIds": true
```

For more details, refer to the [Privacy Service API documentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html).

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Considerations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID Expansion </p> </td> 
   <td colname="col2"> <p>Many Analytics customers originally used the (Legacy) <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html"> Analytics Cookie </a>, but are now using the <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html"> Identity Service (ECID) </a>, previously known as the Marketing Cloud ID Service (MCID). For their website visitors who first visited after the transition, only the ECID exists. However, for those who first visited when only the Legacy Cookie was available, but have since visited: some of their data will have both cookies, but the older data will only have the Analytics Cookie, and in rare cases, the newest data may only have an ECID. </p> <p>You want to make sure that you find all the data for a visitor identified via an Analytics (Visitor ID) Cookie or ECID. Therefore, if you currently use the ECID and previously used the Analytics Cookie, whenever you submit a request using either type of ID, you should include both IDs in the request, or specify the expandIds option. When you specify expandIds, Adobe will check for other ECIDs or Analytics Cookies that corresponds to any cookie IDs you provide. The request will be automatically expanded to include these newly identified cookie IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom ID to Cookie ID Expansion </p> </td> 
   <td colname="col2"> <p>On e-commerce web sites, it is not uncommon for a visitor to browse around the site, add things to their cart and then start the checkout process before they log in to the site. If the ID used to identify users for a Data Privacy request is stored in a custom variable only when the user is logged in, then this pre-login activity will not be associated with the ID. Utilizing the Analytics cookie ID, customers can choose to associate the browsing that was performed prior to login with the purchase after login, since the cookie ID persists across the login. </p> <p>Let's suppose your implementation stores a login ID (CRM ID, user name, loyalty number, email address, etc., or a hash of any of these values) in a custom variable (prop or eVar) or custom visitor ID, and then uses this ID for a Data Privacy access request. The data subject might be surprised that info about all their browsing is not returned as part of an access request, especially if you have promoted to them items viewed but not yet purchased. </p> <p>Analytics Data Privacy processing therefore supports ID Expansion, where Analytics finds all cookie IDs that occur in the same hit as any custom ID and then expands the request to include those IDs as well. </p> <p>When expandIDs is specified along with any namespace other than a cookie namespace, the request will be expanded to include any cookie IDs (ECID or Analytics Cookie), found in hits containing any of the specified IDs. Cookie ID expansion, as described above, will then be performed on any newly found cookie IDs. </p> <p>When the expandIDs option is used for an access request and the specified ID has a label of ID-PERSON, then two sets of files will be returned. The first set (the person set) will contain data only from hits where the specified ID was found. The second set (the device set) will contain data only from hits from the expanded IDs, where the specified ID was not present. </p> </td> 
  </tr> 
 </tbody> 
</table>

During the first few months after Data Privacy went live, the vast majority of Analytics Data Privacy requests did not request ID expansion, but determining the appropriate value for your organization is up to you. You should consult with your legal team about whether ID expansion is required for your data with the IDs that you use and the data you collect within Adobe Analytics. A primary consideration should be that on a shared device, from which multiple users have visited your site, using ID expansion will include data from hits from other users of the device in data returned by access requests (in the device file). Even if you have followed best practices in labeling, such that no private data is included in the device file, such as pages visited, the device file will contain the number of pages visited and the times of each of those visits. Is it OK if you share this information with someone who may not have been the visitor?

For a delete request, where ID expansion is not used, if you use a non-cookie ID (any ID other than the ECID or Analytics cookie) to identify hits that should be deleted, and that ID has an ID-DEVICE label, then unique visitor counts in reports will change, because only some instances of the cookie IDs will be anonymized, while others will be left unchanged. If you are not specifying ID expansion, then it is recommended that you either use a cookie ID for requests, or use IDs with an ID-PERSON label.

When Adobe performs ID expansion, it can require an additional full data scan, which will increase the time that it takes Adobe to complete the request, often adding a week to the processing time.

## Other Data Privacy request flags

In addition to the "expandIDs" flag, Analytics supports two other flags that can be passed as part of a Data Privacy request. These flags with their default values are:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

In the future, the "analyticsDeleteMethod" may support a value of "purge" in addition to the default value of "anonymize". When supported, it will cause the entire hit to be delete rather than simply updating the values of hit fields that have DEL labels.

In addition to its default value, the priority field also supports a value of "low". You should specify this value for requests that are not a result of a data subject request and thus do not have a legal requirement to be completed within 30 days. Note that Adobe discourages the use of the Privacy Service API for reasons other than data subject initiated requests. The Privacy Service API is not an appropriate tool for data cleansing or repairs and will have unintended consequences.

>[!NOTE]
>
>The [Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) has been provided to help you fulfill Data Privacy requests, which are time sensitive. Using this API for other purposes is not supported by Adobe and may impact Adobe's ability to provide timely turn-around of high priority, user-initiated Data Privacy requests for other Adobe customers. We ask that you do not use the Privacy Service API for other purposes such as clearing out data that was accidentally submitted across large groups of visitors.

You should also be aware that any visitor who has a hit deleted (updated or anonymized) as a result of a Data Privacy deletion request will have their state information reset. The next time the visitor returns to your website, they will be a new visitor. All eVar attribution will start again, as will information such as visit numbers, referrers, first page visited, etc. This side effect is undesirable for situations where you want to clear out data fields, and highlights one reason why the Privacy Service API is inappropriate for this use.

Please contact your Account Manager (CSM) to coordinate with our Engineering Architect consulting team to further review & provide level of effort to remove any PII or data issues.
